---
title: Implémentation d'une transaction implicite à l'aide de l'étendue de transaction
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d1706a-1e0c-4c85-9704-75c908372eb9
ms.openlocfilehash: d05e071b97c9a1f3043949a6619a187dd418f9b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120976"
---
# <a name="implementing-an-implicit-transaction-using-transaction-scope"></a>Implémentation d'une transaction implicite à l'aide de l'étendue de transaction
La classe <xref:System.Transactions.TransactionScope> offre un moyen simple pour indiquer qu'un bloc de code participe à une transaction, sans avoir à intervenir sur la transaction même. Une étendue de transaction peut sélectionner et gérer automatiquement la transaction ambiante. En raison de sa facilité d'utilisation et de son efficacité, il est recommandé d'utiliser la classe <xref:System.Transactions.TransactionScope> lors du développement d'une application de transaction.  
  
 De plus, il n'est pas nécessaire d'inscrire explicitement des ressources avec la transaction. Tout gestionnaire de ressources <xref:System.Transactions> (tel que SQL Server 2005) peut détecter l'existence d'une transaction ambiante créée par l'étendue et l'inscrire automatiquement.  
  
## <a name="creating-a-transaction-scope"></a>Création d'une étendue de transaction  
 L'exemple suivant illustre une utilisation simple de la classe <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[TransactionScope#1](../../../../samples/snippets/csharp/VS_Snippets_Remoting/TransactionScope/cs/ScopeWithSQL.cs#1)]
 [!code-vb[TransactionScope#1](../../../../samples/snippets/visualbasic/VS_Snippets_Remoting/TransactionScope/vb/ScopeWithSQL.vb#1)]  
  
 L'étendue de transaction démarre après la création d'un nouvel objet <xref:System.Transactions.TransactionScope>.  Comme illustré dans l’exemple de code, il est recommandé de créer des étendues avec un **à l’aide de** instruction. Le **à l’aide de** instruction est disponible à la fois dans C# et dans Visual Basic et fonctionne comme un **try... enfin** bloc pour garantir que l’étendue est correctement supprimé.  
  
 Lorsque vous instanciez <xref:System.Transactions.TransactionScope>, le gestionnaire de transactions détermine la transaction à laquelle participer. Une fois déterminée, la portée participe toujours à cette transaction. La décision est basée sur deux facteurs : si une transaction ambiante est présente et la valeur de la **TransactionScopeOption** paramètre dans le constructeur. La transaction ambiante est la transaction dans laquelle s'exécute votre code. Vous pouvez obtenir une référence à la transaction ambiante en appelant la propriété <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> statique de la classe <xref:System.Transactions.Transaction>. Pour plus d’informations sur l’utilisation de ce paramètre, consultez le [la gestion des flux de transaction à l’aide de TransactionScopeOption](#ManageTxFlow) section de cette rubrique.  
  
## <a name="completing-a-transaction-scope"></a>Fin d'une étendue de transaction  
 Une fois que votre application a effectué toutes les tâches nécessaires au cours d'une transaction, appelez la méthode <xref:System.Transactions.TransactionScope.Complete%2A?displayProperty=nameWIthType> (une seule fois) pour informer le gestionnaire de transactions que la transaction peut être validée. Il est vivement conseillé de placer l’appel à <xref:System.Transactions.TransactionScope.Complete%2A> en tant que la dernière instruction dans le **à l’aide de** bloc.  
  
 Ne pas appeler cette méthode d’abandonne la transaction, parce que le Gestionnaire de transactions l’interprète comme une défaillance du système, ou équivalent à une exception levée dans l’étendue de la transaction. Toutefois, l'appel à cette méthode ne garantit pas la validation de la transaction. Il s’agit simplement d’un moyen d’informer le gestionnaire de transactions de votre état. Après avoir appelé la méthode <xref:System.Transactions.TransactionScope.Complete%2A>, vous ne pouvez plus accéder à la transaction ambiante via la propriété <xref:System.Transactions.Transaction.Current%2A> sous peine de lever une exception.  
  
 Si le <xref:System.Transactions.TransactionScope> de l’objet a créé la transaction au départ, le travail réel de la validation de la transaction par le Gestionnaire de transactions se produit après la dernière ligne de code dans le **à l’aide de** bloc. S'il n'a pas créé la transaction, la validation se produit chaque fois que <xref:System.Transactions.CommittableTransaction.Commit%2A> est appelé par le propriétaire de l'objet <xref:System.Transactions.CommittableTransaction>. À ce stade le Gestionnaire de transactions appelle des gestionnaires de la ressource et les informe de commit ou rollback, selon que le <xref:System.Transactions.TransactionScope.Complete%2A> méthode a été appelée sur le <xref:System.Transactions.TransactionScope> objet.  
  
 Le **à l’aide de** instruction garantit que le <xref:System.Transactions.TransactionScope.Dispose%2A> méthode de la <xref:System.Transactions.TransactionScope> objet est appelé même si une exception se produit. La méthode <xref:System.Transactions.TransactionScope.Dispose%2A> marque la fin de l'étendue de transaction. Il est possible que les exceptions qui se produisent après l’appel à cette méthode n’affectent pas la transaction. Cette méthode restaure également la transaction ambiante à son état précédent.  
  
 Une exception <xref:System.Transactions.TransactionAbortedException> est levée si l'étendue crée la transaction et que cette transaction est abandonnée. Une exception <xref:System.Transactions.TransactionInDoubtException> est levée si le gestionnaire de transactions ne parvient pas à aboutir à une décision de validation. Aucune exception n'est levée si la transaction est validée.  
  
## <a name="rolling-back-a-transaction"></a>Restauration d'une transaction  
 Pour restaurer une transaction, n'appelez pas la méthode <xref:System.Transactions.TransactionScope.Complete%2A> dans l'étendue de transaction. Par exemple, vous pouvez lever une exception dans l'étendue. La transaction à laquelle il participe est restaurée.  
  
## <a name="ManageTxFlow"></a> La gestion des flux de transaction à l’aide de TransactionScopeOption  
 L'étendue de transaction peut être imbriquée en appelant une méthode qui utilise une <xref:System.Transactions.TransactionScope> à partir d'une méthode utilisant sa propre étendue, comme la méthode `RootMethod` de l'exemple suivant,  
  
```csharp  
void RootMethod()  
{  
     using(TransactionScope scope = new TransactionScope())  
     {  
          /* Perform transactional work here */  
          SomeMethod();  
          scope.Complete();  
     }  
}  
  
void SomeMethod()  
{  
     using(TransactionScope scope = new TransactionScope())  
     {  
          /* Perform transactional work here */  
          scope.Complete();  
     }  
}  
```  
  
 L'étendue de transaction supérieure est appelée « étendue racine ».  
  
 La classe <xref:System.Transactions.TransactionScope> fournit plusieurs constructeurs surchargés qui acceptent une énumération de type <xref:System.Transactions.TransactionScopeOption>, qui définit le comportement transactionnel de l'étendue.  
  
 Un objet <xref:System.Transactions.TransactionScope> dispose de trois options :  
  
-   Joindre la transaction ambiante ou en créer une nouvelle s'il n'en existe pas.  
  
-   Constituer une nouvelle étendue racine, c'est-à-dire démarrer une nouvelle transaction et en faire la nouvelle transaction ambiante de sa propre étendue.  
  
-   Ne participer à aucune transaction. En conséquence, il n'y a pas de transaction ambiante.  
  
 Si l'étendue est instanciée avec <xref:System.Transactions.TransactionScopeOption.Required> et qu'une transaction ambiante existe, l'étendue joint cette transaction. En revanche, s'il n'y a pas de transaction ambiante, l'étendue en crée une nouvelle et devient l'étendue racine. Valeur par défaut. Si <xref:System.Transactions.TransactionScopeOption.Required> est utilisé, le code de l'étendue n'a pas à se comporter différemment selon qu'il s'agit de la racine ou seulement de la jonction de la transaction ambiante. Il fonctionne de la même façon dans les deux cas.  
  
 Si l'étendue est instanciée avec <xref:System.Transactions.TransactionScopeOption.RequiresNew>, il s'agit toujours de l'étendue racine. Une nouvelle transaction démarre et devient la nouvelle transaction ambiante de l'étendue.  
  
 Si la portée est instanciée avec <xref:System.Transactions.TransactionScopeOption.Suppress>, elle ne prend jamais part à une transaction, qu'une transaction ambiante existe ou non. Une étendue instanciée avec cette valeur toujours avoir **null** sa transaction ambiante.  
  
 Ces options sont répertoriées dans le tableau suivant.  
  
|TransactionScopeOption|Transaction ambiante|L'étendue participe à|  
|----------------------------|-------------------------|-----------------------------|  
|Obligatoire|Non|Nouvelle transaction (future racine)|  
|Nouveau requis|Non|Nouvelle transaction (future racine)|  
|Supprimer|Non|Aucune transaction|  
|Obligatoire|Oui|Transaction ambiante|  
|Nouveau requis|Oui|Nouvelle transaction (future racine)|  
|Supprimer|Oui|Aucune transaction|  
  
 Lorsqu'un objet <xref:System.Transactions.TransactionScope> joint une transaction ambiante existante, la suppression de l'objet d'étendue peut ne pas entraîner l'arrêt de la transaction, à moins que l'étendue abandonne la transaction. Si la transaction ambiante a été créée par une étendue racine, seulement lorsque l'étendue racine est supprimée, <xref:System.Transactions.CommittableTransaction.Commit%2A> est appelé sur la transaction. Si la transaction a été créée manuellement, elle se termine lors de son abandon ou de sa validation par son créateur.  
  
 L'exemple suivant montre un objet <xref:System.Transactions.TransactionScope> qui crée trois objets d'étendue imbriqués, chacun étant instancié avec une valeur <xref:System.Transactions.TransactionScopeOption> différente.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())   
//Default is Required   
{   
     using(TransactionScope scope2 = new   
      TransactionScope(TransactionScopeOption.Required))   
     {  
     ...  
     }   
  
     using(TransactionScope scope3 = new TransactionScope(TransactionScopeOption.RequiresNew))   
     {  
     ...  
     }   
  
     using(TransactionScope scope4 = new   
        TransactionScope(TransactionScopeOption.Suppress))   
    {  
     ...  
    }   
}  
```  
  
 Cet exemple montre un bloc de code sans transaction ambiante créant une nouvelle étendue (`scope1`) avec <xref:System.Transactions.TransactionScopeOption.Required>. La portée `scope1` est une portée racine, car elle crée une transaction (Transaction A) pour en faire la transaction ambiante. `Scope1` crée ensuite trois objets de plus, chacun avec un autre <xref:System.Transactions.TransactionScopeOption> valeur. Par exemple, `scope2` est créée avec <xref:System.Transactions.TransactionScopeOption.Required> et puisqu'il s'agit d'une transaction ambiante, elle joint la première transaction créée par `scope1`. Notez que `scope3` est l'étendue racine d'une nouvelle transaction et que `scope4` ne dispose pas de transaction ambiante.  
  
 Bien que la valeur par défaut, et la plus utilisée, de <xref:System.Transactions.TransactionScopeOption> est <xref:System.Transactions.TransactionScopeOption.Required>, chacune des autres valeurs a une fonction unique.  
  
 <xref:System.Transactions.TransactionScopeOption.Suppress> est utile lorsque vous souhaitez conserver les opérations effectuées par la section de code et que vous ne souhaitez pas abandonner la transaction ambiante si les opérations échouent. Pour effectuer des opérations d'enregistrement ou d'audit par exemple, ou pour publier des événements aux abonnés, indépendamment de la validation ou de l'abandon de votre transaction ambiante. Cette valeur vous permet d'avoir une section de code non transactionnelle dans une étendue de transaction, comme illustré dans l'exemple suivant.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())  
{  
     try  
     {  
          //Start of non-transactional section   
          using(TransactionScope scope2 = new  
             TransactionScope(TransactionScopeOption.Suppress))  
          {  
               //Do non-transactional work here  
          }  
          //Restores ambient transaction here  
   }  
     catch  
     {}  
   //Rest of scope1  
}  
```  
  
### <a name="voting-inside-a-nested-scope"></a>Vote au sein d'une étendue imbriquée  
 Bien qu'une étendue imbriquée puisse joindre la transaction ambiante de l'étendue racine, appeler <xref:System.Transactions.TransactionScope.Complete%2A> dans l'étendue imbriquée n'a pas d'effet sur l'étendue racine. La transaction n'est validée que si toutes les étendues, de l'étendue racine à la dernière étendue imbriquée, votent sa validation. Si vous n'appelez pas <xref:System.Transactions.TransactionScope.Complete%2A> dans une étendue imbriquée pour affecter l'étendue racine comme transaction ambiante, l'opération échouera immédiatement.  
  
## <a name="setting-the-transactionscope-timeout"></a>Définition du délai d'attente TransactionScope  
 Certains des constructeurs surchargés de <xref:System.Transactions.TransactionScope> acceptent une valeur de type <xref:System.TimeSpan>, utilisée pour contrôler le délai d'attente de la transaction. La valeur zéro indique un délai d'attente infini. Le délai d'attente infini est particulièrement utile pour le débogage, lorsque vous voulez isoler un problème au sein de votre logique métier grâce au code, sans que la transaction que vous déboguez expire lors de la localisation du problème. Utilisez la valeur de délai d'attente infini avec précaution dans tous les autres cas, car elle substitue les dispositifs de protection par des blocages de transaction.  
  
 Le délai d'attente <xref:System.Transactions.TransactionScope> peut prendre des valeurs autres que celle par défaut dans deux cas. Le premier cas intervient lors du développement, lorsque vous voulez tester la façon dont votre application gère les transactions abandonnées. En affectant une faible valeur au délai d'attente (tel qu'une milliseconde), vous provoquez l'échec de la transaction et pouvez ainsi obtenir le code de gestion des erreurs. Le second cas pour lequel il est nécessaire de définir une valeur inférieure au délai d'attente par défaut est lorsque vous pensez que l'étendue est à l'origine de conflits de ressources, causant des blocages. Dans ce cas, abandonnez la transaction dès que possible et n'attendez pas l'expiration du délai d'attente par défaut.  
  
 Lorsqu'une étendue joint une transaction ambiante avec un délai d'attente plus court que celui de la transaction ambiante, le nouveau délai, plus court, est appliqué à l'objet <xref:System.Transactions.TransactionScope> et l'étendue doit se terminer dans le temps imbriqué spécifié, sans quoi la transaction est automatiquement abandonnée. Si le délai d'attente de l'étendue imbriquée est supérieur à celui de la transaction ambiante, il n'a aucun effet.  
  
## <a name="setting-the-transactionscope-isolation-level"></a>Définition du niveau d'isolation TransactionScope  
 Certains des constructeurs surchargés de <xref:System.Transactions.TransactionScope> acceptent une structure de type <xref:System.Transactions.TransactionOptions> pour spécifier un niveau d'isolation, en plus d'une valeur de délai d'attente. Par défaut, la transaction s'exécute avec un niveau d'isolation de valeur <xref:System.Transactions.IsolationLevel.Serializable>. On utilise habituellement un niveau d'isolation autre que <xref:System.Transactions.IsolationLevel.Serializable> pour les systèmes de lecture intensive. Cela requiert une solide compréhension de la théorie sur le traitement des transactions et de la sémantique de la transaction même, des problèmes d'accès concurrentiel ainsi que des conséquences pour la cohérence du système.  
  
 De plus, tous les gestionnaires de ressources ne supportent pas l'ensemble des niveaux d'isolation et peuvent choisir de prendre part à la transaction à un niveau supérieur à celui configuré.  
  
 Chaque niveau d'isolation, hormis <xref:System.Transactions.IsolationLevel.Serializable>, est susceptible de résulter de façon incohérente d'autres transactions accédant aux mêmes informations. La différence entre les niveaux d'isolation réside dans l'utilisation des verrous de lecture et d'écriture. Un verrou ne peut être maintenu que lorsque la transaction accède aux données du gestionnaire de ressources ou jusqu'à ce que la transaction soit validée ou abandonnée. Le premier est utilisé pour le débit et le deuxième pour la cohérence. Les deux types de verrou et les deux types d'opération (lecture/écriture) donnent quatre niveaux d'isolation de base. Pour plus d'informations, voir <xref:System.Transactions.IsolationLevel>.  
  
 En cas d'utilisation d'objets <xref:System.Transactions.TransactionScope> imbriqués, toutes les étendues imbriquées doivent être configurées pour utiliser le même niveau d'isolation pour pouvoir joindre la transaction ambiante. Si un objet <xref:System.Transactions.TransactionScope> imbriqué tente de joindre la transaction ambiante avec un niveau d'isolation différent, une exception <xref:System.ArgumentException> est levée.  
  
## <a name="interop-with-com"></a>Interopérabilité avec COM+  
 Lors de la création d'une nouvelle instance <xref:System.Transactions.TransactionScope>, vous pouvez utiliser l'énumération <xref:System.Transactions.EnterpriseServicesInteropOption> dans l'un des constructeurs pour spécifier comment interagir avec COM+. Pour plus d’informations, consultez [l’interopérabilité avec Enterprise Services et les Transactions COM +](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md).  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Transactions.Transaction.Clone%2A>
- <xref:System.Transactions.TransactionScope>

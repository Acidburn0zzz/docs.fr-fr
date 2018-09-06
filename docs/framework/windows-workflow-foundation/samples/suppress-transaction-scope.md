---
title: Étendue de transaction de suppression
ms.date: 03/30/2017
ms.assetid: 49fb6dd4-30d4-4067-925c-c5de44c8c740
ms.openlocfilehash: 44814d66a4de4b3e72bb33eb46019eb1088ab040
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43788037"
---
# <a name="suppress-transaction-scope"></a>Étendue de transaction de suppression
L'exemple montre comment créer une activité `SuppressTransactionScope` personnalisée pour supprimer la transaction runtime ambiante, si elle existe.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="sample-details"></a>Détails de l'exemple  
 L'activité personnalisée est utile pour empêcher une transaction d'être passée à un autre service si le flux de transaction est indésirable pour le scénario particulier. Le runtime du workflow dispose d'une prise en charge intégrée pour la suppression de la transaction ambiante dans la classe <xref:System.Activities.NativeActivity>, mais pour utiliser cette prise en charge, il est nécessaire de créer un <xref:System.Activities.NativeActivity> personnalisé tel que celui figurant dans cet exemple.  
  
 Le scénario est composé de trois parties. Tout d'abord, un <xref:System.Activities.Statements.TransactionScope> crée une transaction runtime qui devient ambiante. Cela est vérifié par une activité personnalisée qui imprime les identificateurs locaux et distribués de la transaction. La transaction est ensuite passée à un service distant avant de commencer la deuxième partie. Pendant la deuxième partie, le workflow entre un `SuppressTransactionScope` et répète à nouveau le processus d'impression des identificateurs de transaction et de passage de la transaction. Toutefois, l'activité personnalisée ne trouve pas de transaction ambiante et le message passé au service ne contient pas la transaction. Par conséquent, le service crée une transaction, ce qui signifie que l'ID distribué imprimé sur le client et celui imprimé sur le service ne correspondent pas. La dernière partie se produit une fois que `SuppressTransactionScope` s'arrête et que la transaction runtime redevient ambiante, comme vérifié par un autre message au service avec un identificateur distribué qui correspond à l'identificateur du premier message.  
  
 L'activité elle-même dérive de <xref:System.Activities.NativeActivity> car elle doit planifier une activité enfant et ajouter une propriété d'exécution. `SuppressTransactionScope` a un <xref:System.Activities.Variable> de type <xref:System.Activities.RuntimeTransactionHandle>, lequel doit être utilisé plutôt qu'un champ d'instance de type <xref:System.Activities.RuntimeTransactionHandle> car le handle doit être initialisé. `Variable<RuntimeTransactionHandle>` est ajouté aux métadonnées de l'activité sous la forme d'une variable d'implémentation car il est utilisé en interne uniquement.  
  
 Lorsque l'activité est exécutée, elle commence par vérifier si un corps a été spécifié, et si tel est le cas, elle définit la propriété `SuppressTransaction` sur <xref:System.Activities.RuntimeTransactionHandle>. Une fois la propriété définie, elle est ajoutée aux propriétés d'exécution et devient ambiante. Cela signifie que toute activité qui est un enfant de `SuppressTransactionScope` peut voir la propriété et, par conséquent, applique la suppression de la transaction runtime et entraîne la levée d'une exception par un <xref:System.Activities.Statements.TransactionScope> imbriqué. Une fois le handle ajouté aux propriétés d'exécution, le corps est planifié pour s'exécuter.  
  
#### <a name="to-use-this-sample"></a>Pour utiliser cet exemple  
  
1.  Ouvrez la solution SuppressTransactionScope.sln dans [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Pour générer la solution, appuyez sur CTRL + MAJ + B ou sélectionnez **générer la Solution** à partir de la **Build** menu.  
  
3.  Une fois la génération a réussi, cliquez sur la solution et sélectionnez **définir les projets de démarrage**. Dans la boîte de dialogue, sélectionnez **plusieurs projets de démarrage** et vérifiez que l’action pour les deux projets est **Démarrer**.  
  
4.  Appuyez sur F5 ou sélectionnez **démarrer le débogage** à partir de la **déboguer** menu. Ou bien, vous pouvez appuyer sur CTRL + F5 ou sélectionnez **démarrer sans débogage** à partir de la **déboguer** menu afin d’exécuter sans débogage.  
  
    > [!NOTE]
    >  Le serveur doit être en cours d'exécution avant de démarrer le client. La sortie de la fenêtre de console qui héberge le service indique le moment où il a démarré.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`
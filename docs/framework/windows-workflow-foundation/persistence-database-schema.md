---
title: Schéma de la base de données de persistance
ms.date: 03/30/2017
ms.assetid: 34f69f4c-df81-4da7-b281-a525a9397a5c
ms.openlocfilehash: 38df4b3d629840f1b5def2eafa0d074a2b2397a2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331063"
---
# <a name="persistence-database-schema"></a>Schéma de la base de données de persistance
Cette rubrique décrit les vues publiques prises en charge par le magasin d'instances de workflow SQL.  
  
## <a name="instances-view"></a>Vue Instances  
 Le **Instances** vue contient des informations générales sur toutes les Instances de flux de travail dans la base de données.  
  
|Nom de la colonne|Type de colonne|Description|  
|-----------------|-----------------|-----------------|  
|InstanceId|UniqueIdentifier|ID d'une instance de workflow.|  
|PendingTimer|DateTime|Indique que le workflow est bloqué sur une activité Delay et reprendra lorsque le minuteur aura expiré. Cette valeur peut être Null si le workflow n'est pas bloqué dans l'attente de l'expiration du minuteur.|  
|CreationTime|DateTime|Indique le moment de création du workflow.|  
|LastUpdatedTime|DateTime|Indique la dernière fois que le workflow a été rendu persistant dans la base de données.|  
|ServiceDeploymentId|BigInt|Joue le rôle de clé étrangère pour la vue [ServiceDeployments]. Si l'instance de workflow actuelle est une instance d'un service hébergé sur le Web, cette colonne a une valeur ; sinon, elle a la valeur NULL.|  
|SuspensionExceptionName|Nvarchar(450)|Indique le type d'exception (par exemple, InvalidOperationException) qui a provoqué l'interruption du workflow.|  
|SuspensionReason|Nvarchar(max)|Indique la raison de l'interruption de l'instance de workflow. Si une exception a provoqué l'interruption de l'instance, cette colonne contient le message associé à l'exception.<br /><br /> Si l'instance a été interrompue manuellement, cette colonne contient la raison, spécifiée par l'utilisateur, de l'interruption de l'instance.|  
|ActiveBookmarks|Nvarchar(max)|Si l'instance de workflow est inactive, cette propriété indique sur quels signets l'instance est bloquée. Si l'instance n'est pas inactive, cette colonne contient la valeur NULL.|  
|CurrentMachine|Nvarchar(128)|Indique le nom de l'ordinateur ayant actuellement l'instance de workflow chargée en mémoire.|  
|LastMachine|Nvarchar(450)|Indique le dernier ordinateur qui a chargé l'instance de workflow.|  
|ExecutionStatus|Nvarchar(450)|Indique l'état d'exécution actuel du workflow. États possibles sont notamment **lors de l’exécution**, **Idle**, **fermé**.|  
|IsInitialized|Bit|Indique si l'instance de workflow a été initialisée. Une instance de workflow initialisée est une instance de workflow rendue persistante au moins une fois.|  
|IsSuspended|Bit|Indique si l'instance de workflow a été interrompue.|  
|IsCompleted|Bit|Indique si l'exécution de l'instance de workflow est terminée. **Remarque :**  IIf le **InstanceCompletionAction** propriété est définie sur **DeleteAll**, les instances sont supprimées de la vue à l’achèvement.|  
|EncodingOption|TinyInt|Décrit l'encodage utilisé pour sérialiser les propriétés de données.<br /><br /> -0 – aucun encodage<br />-   1 – GzipStream|  
|ReadWritePrimitiveDataProperties|Varbinary(max)|Contient les propriétés de données d'instance sérialisée qui seront retournées au runtime de workflow lors du chargement de l'instance.<br /><br /> Chaque propriété primitive est un type CLR natif, ce qui signifie qu'aucun assembly particulier n'est requis pour désérialiser l'objet blob.|  
|WriteOnlyPrimitiveDataProperties|Varbinary(max)|Contient les propriétés de données d'instance sérialisée qui ne sont pas retournées au runtime de workflow lors du chargement de l'instance.<br /><br /> Chaque propriété primitive est un type CLR natif, ce qui signifie qu'aucun assembly particulier n'est requis pour désérialiser l'objet blob.|  
|ReadWriteComplexDataProperties|Varbinary(max)|Contient les propriétés de données d'instance sérialisée qui seront retournées au runtime de workflow lors du chargement de l'instance.<br /><br /> Un désérialiseur nécessiterait une connaissance de tous les types d'objets stockés dans cet objet blob.|  
|WriteOnlyComplexDataProperties|Varbinary(max)|Contient les propriétés de données d'instance sérialisée qui ne sont pas retournées au runtime de workflow lors du chargement de l'instance.<br /><br /> Un désérialiseur nécessiterait une connaissance de tous les types d'objets stockés dans cet objet blob.|  
|IdentityName|Nvarchar(max)|Nom de la définition de workflow.|  
|IdentityPackage|Nvarchar(max)|Informations sur le package fournies lors de la création du workflow (comme le nom de l'assembly).|  
|Build|BigInt|Numéro de la build pour la version de workflow.|  
|Majeur|BigInt|Numéro de la version majeure du workflow.|  
|Mineur|BigInt|Numéro de la version mineure du workflow.|  
|Revision|BigInt|Numéro de révision de la version du workflow.|  
  
> [!CAUTION]
>  Le **Instances** vue contient également un déclencheur Delete. Les utilisateurs disposant des autorisations appropriées peuvent exécuter, sur cette vue, des instructions de suppression qui supprimeront de force des instances de workflow de la base de données. Il est recommandé de n'effectuer une suppression directe dans la vue qu'en dernier recours, car la suppression d'une instance sous le runtime de workflow peut avoir des conséquences inattendues. Utilisez plutôt le point de terminaison de gestion de l'instance de workflow pour que le runtime de workflow arrête l'instance. Si vous voulez supprimer un grand nombre d'instances de la vue, assurez-vous qu'il n'y aucun runtime actif susceptible d'être en train d'utiliser ces instances.  
  
## <a name="servicedeployments-view"></a>Vue ServiceDeployments  
 Le **ServiceDeployments** vue contient des informations de déploiement pour toutes les applications Web (IIS / WAS) des services de workflow hébergés. Chaque instance de workflow est hébergé sur le Web contiendra un **ServiceDeploymentId** qui fait référence à une ligne dans cette vue.  
  
|Nom de la colonne|Type de colonne|Description|  
|-----------------|-----------------|-----------------|  
|ServiceDeploymentId|BigInt|Clé primaire pour cette vue.|  
|SiteName|Nvarchar(max)|Représente le nom du site qui contient le service de flux de travail (par exemple, **Site Web par défaut**).|  
|RelativeServicePath|Nvarchar(max)|Représente le chemin d’accès virtuel relatif au site qui pointe vers le service de workflow. (par exemple)  **/app1/PurchaseOrderService.svc**).|  
|RelativeApplicationPath|Nvarchar(max)|Représente le chemin d’accès virtuel relatif au site qui pointe vers une application contenant le service de workflow. (par exemple, **/app1**).|  
|ServiceName|Nvarchar(max)|Représente le nom du service de workflow. (par exemple, **PurchaseOrderService**).|  
|ServiceNamespace|Nvarchar(max)|Représente l'espace de noms du service de workflow. (par exemple, **MyCompany**).|  
  
 La Vue ServiceDeployments contient également un déclencheur DELETE. Les utilisateurs disposant des autorisations appropriées peuvent exécuter, sur cette vue, des instructions de suppression pour supprimer des entrées ServiceDeployment de la base de données. Prenez note de ce qui suit :  
  
1. La suppression d'entrées de cette vue est coûteuse, car l'intégralité de la base de données doit être verrouillée avant d'effectuer cette opération. Cela est nécessaire pour éviter le scénario où une instance de workflow pourrait faire référence à une entrée ServiceDeployment inexistante. Effectuez les suppressions dans cette vue uniquement pendant les temps d'inactivité/périodes de maintenance.  
  
2. Toute tentative supprimer une ligne ServiceDeployment référencée par des entrées dans le **Instances** vue entraîne une absence d’opération. Vous ne pouvez supprimer que les lignes ServiceDeployment sans références.  
  
## <a name="instancepromotedproperties-view"></a>Vue InstancePromotedProperties  
 Le **InstancePromotedProperties** vue contient des informations pour toutes les propriétés promues sont spécifiées par l’utilisateur. Une propriété promue fonctionne comme une propriété de première classe, qu'un utilisateur peut utiliser dans des requêtes pour récupérer des instances.  Par exemple, un utilisateur peut ajouter une promotion PurchaseOrder qui stocke toujours le coût d’une commande dans le **Value1** colonne. Cela permettrait à un utilisateur de rechercher toutes les commandes fournisseur dont le coût dépasse une certaine valeur.  
  
|Type de colonne|Type de colonne|Description|  
|-|-|-|  
|InstanceId|UniqueIdentifier|ID de l'instance de workflow.|  
|EncodingOption|TinyInt|Décrit l'encodage utilisé pour sérialiser les propriétés binaires promues.<br /><br /> -0 – aucun encodage<br />-   1 – GZipStream|  
|PromotionName|Nvarchar(400)|Nom de la promotion associée à cette instance. Le PromotionName est requis pour ajouter un contexte aux colonnes génériques dans cette ligne.<br /><br /> Par exemple, le PromotionName « PurchaseOrder » pourrait indiquer que Value1 contient le coût de la commande, que Value2 contient le nom du client qui a passé la commande, que Value3 contient l'adresse du client, etc.|  
|Value[1-32]|SqlVariant|Value[1-32] contient des valeurs qui peuvent être stockées dans une colonne SqlVariant. Une promotion unique ne peut pas contenir plus de 32 SqlVariants.|  
|Value[33-64]|Varbinary(max)|Value[33-64] contient des valeurs sérialisées. Par exemple, Value33 pourrait contenir une image JPEG d'un élément acheté. Une promotion unique ne peut pas contenir plus de 32 propriétés binaires.|  
  
 La vue InstancePromotedProperties est liée à un schéma, ce qui signifie que les utilisateurs peuvent ajouter des index sur une ou plusieurs colonnes afin d'optimiser les requêtes sur cette vue.  
  
> [!NOTE]
>  Une vue indexée requiert plus de stockage et ajoute une charge de traitement supplémentaire. Reportez-vous à [Improving Performance with SQL Server 2008 Indexed Views](https://go.microsoft.com/fwlink/?LinkId=179529) pour plus d’informations.

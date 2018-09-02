---
title: Confirmation
ms.date: 03/30/2017
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
ms.openlocfilehash: caa712aa52da01ce44335a361fd6c9f5215316bf
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419488"
---
# <a name="confirmation"></a>Confirmation
Cet exemple présente quatre scénarios courants se rapportant à l'utilisation de <xref:System.Activities.Statements.CompensableActivity> et à la confirmation. L'exemple exécute quatre workflows pour illustrer la confirmation. Cet exemple est disponible dans les versions déclarative et impérative.  
  
## <a name="confirm-a-compensable-activity"></a>Confirmer une activité compensable  
 Le premier workflow, qui est composé d'une séquence de deux instances <xref:System.Activities.Statements.CompensableActivity>, montre comment confirmer une activité compensable. Après l'achèvement du deuxième <xref:System.Activities.Statements.CompensableActivity>, une activité de confirmation confirme la première activité. Lorsque le workflow se termine correctement, toutes les instances <xref:System.Activities.Statements.CompensableActivity> qui n'ont pas été confirmées ou compensées sont automatiquement confirmées dans l'ordre par défaut. Sans la confirmation, le deuxième <xref:System.Activities.Statements.CompensableActivity> aurait été confirmé en premier.  
  
## <a name="explicit-compensation"></a>Compensation explicite  
 Le deuxième scénario présente l'effet sur la confirmation par défaut lorsqu'un <xref:System.Activities.Statements.CompensableActivity> est compensé de manière explicite. Le workflow est composé d'une séquence de deux activités <xref:System.Activities.Statements.CompensableActivity>. Une fois la deuxième terminée, la première est compensée de manière explicite. Par conséquent, lorsque le workflow se termine, seul le deuxième <xref:System.Activities.Statements.CompensableActivity> est confirmé.  
  
## <a name="controlling-the-order-of-confirmation-for-nested-compensableactivity-activities"></a>Contrôle de l'ordre de confirmation pour les activités CompensableActivity imbriquées  
 Le troisième scénario montre comment contrôler l'ordre de confirmation pour des <xref:System.Activities.Statements.CompensableActivity> imbriqués. Le scénario est composé d'un <xref:System.Activities.Statements.CompensableActivity> comme racine du workflow. Le corps du <xref:System.Activities.Statements.CompensableActivity> racine est une séquence de trois <xref:System.Activities.Statements.CompensableActivity>. Le <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> pour le <xref:System.Activities.Statements.CompensableActivity> racine est une séquence qui spécifie le premier <xref:System.Activities.Statements.CompensableActivity> imbriqué doit être confirmé, puis le deuxième. Lorsque le workflow se termine, il confirme le <xref:System.Activities.Statements.CompensableActivity> racine, qui confirme ensuite le premier, le deuxième et le troisième <xref:System.Activities.Statements.CompensableActivity> imbriqués, dans cet ordre. Par conséquent, l'ordre de confirmation par défaut est fondamentalement inversé. Étant donné que le troisième <xref:System.Activities.Statements.CompensableActivity> n'a pas été explicitement confirmé dans le cadre du <xref:System.Activities.Statements.CompensableActivity> racine par <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>, il est confirmé d'après l'ordre par défaut. Toutefois, étant donné qu'il est le seul <xref:System.Activities.Statements.CompensableActivity> non confirmé, cela signifies simplement qu'il est confirmé.  
  
## <a name="scoping-of-variables"></a>Étendue des variables  
 Le quatrième scénario montre comment la durée de vie des variables définies pour un <xref:System.Activities.Statements.CompensableActivity> ou l'un de ses parents se trouve toujours dans l'étendue lorsque les gestionnaires <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> ou <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> sont exécutés, même si l'activité ou le workflow sont terminés. Le workflow est composé d'une séquence de deux <xref:System.Activities.Statements.CompensableActivity>. Dans le corps du premier, la valeur de la variable `mySum` est la somme de 5 et de 10, et le résultat est imprimé. Dans le corps du deuxième <xref:System.Activities.Statements.CompensableActivity>, la valeur de la somme est la somme existante à laquelle est ajoutée la valeur 7, et le résultat est imprimé. Un gestionnaire de confirmation personnalisé est défini pour le premier <xref:System.Activities.Statements.CompensableActivity>, qui imprime la somme, soustrait 7, et imprime à nouveau la somme. En inspectant les sommes imprimées, il est clair que la variable se trouve dans l'étendue non seulement pour les corps des deux <xref:System.Activities.Statements.CompensableActivity>, mais également pour <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.  
  
#### <a name="to-run-the-sample"></a>Pour exécuter l'exemple  
  
1.  Chargez la solution dans [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Exécutez l'application ConfirmationSample.exe.  
  
3.  Observez la sortie suivante :  
  
 **Confirmation explicite : début de workflowCompensableActivity1 : BodyCompensableActivity2 : BodyCompensableActivity1 : HandlerEnd de Confirmation de workflowCompensableActivity2 : Confirmation HandlerExplicit compensation : début de workflowCompensableActivity1 : BodyCompensableActivity2 : BodyCompensableActivity1 : HandlerEnd de Compensation de workflowCompensableActivity2 : Confirmation HandlerCustom confirmation : début de gestionnaire de workflowCompensableActivity1 : BodyCompensableActivity2 : BodyCompensableActivity3 : BodyEnd de workflowCompensableActivity1 : Confirmation HandlerCompensableActivity2 : Confirmation HandlerCompensableActivity3 : accès HandlerVariable de Confirmation dans un gestionnaire de confirmation : Début de workflowCompensableActivity1 : BodyCompensableActivity1 : la somme est : 15CompensableActivity2 : BodyCompensableActivity2 : ajout de 7 à le sumCompensableActivity2 : la somme est désormais : 22End de workflowCompensableActivity2 : Confirmation HandlerCompensableActivity1 : Confirmation HandlerCompensableActivity2 : la somme est : 22CompensableActivity2 : après soustraction de 12, la somme est maintenant : entrée 10Press pour quitter.**  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`
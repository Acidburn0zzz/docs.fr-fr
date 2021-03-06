---
title: Création et exécution d'une instance de workflow
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: f2bdfce0b311da6dd20aac5e0fe4f5fbcd14f68a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210093"
---
# <a name="creating-and-running-a-workflow-instance"></a>Création et exécution d'une instance de workflow
Cet exemple montre comment exécuter une instance de workflow. Il indique comment l’exécuter de façon synchrone et de façon asynchrone.  
  
## <a name="demonstrates"></a>Démonstrations  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Discussion  
 La première partie de l'exemple utilise <xref:System.Activities.WorkflowInvoker.Invoke%2A>. Il s'agit de la façon la plus simple d'exécuter un workflow. Les workflows exécutés avec <xref:System.Activities.WorkflowInvoker.Invoke%2A> s’exécutent de façon synchrone.  
  
 La deuxième partie de l'exemple utilise la classe <xref:System.Activities.WorkflowApplication>. <xref:System.Activities.WorkflowApplication> vous permet d’avoir davantage de contrôle sur chaque instance, notamment la possibilité d’interagir avec le flux de travail en cours d’exécution et d’exécuter de façon asynchrone le flux de travail.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>Voir aussi

- [Utilisation de WorkflowInvoker et WorkflowApplication](../using-workflowinvoker-and-workflowapplication.md)

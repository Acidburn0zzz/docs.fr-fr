---
title: Délai durable en XAMLX
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8fa5a9e4287bcbcb490754b84a8b5060d321f779
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="durable-delay-in-xamlx"></a>Délai durable en XAMLX
Cet exemple montre comment utiliser un délai durable, qui est un délai rendant le workflow persistant sur un périphérique durable pendant le délai.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à la page [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les exemples [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a>Discussion  
 L'exemple de workflow contient deux messages sur un fichier local qui sont séparés par un délai. Lorsque le délai est déclenché, le workflow est déchargé, et attend 5 secondes dans le magasin d'instances de workflow avant d'être rechargé en mémoire.  
  
 Le fichier .xamlx est un service de workflow qui est hébergé dans Visual Studio. Visual Studio utilise Cassini qui utilise un service de workflow hôte pour héberger le flux de travail.  
  
 En plus d'héberger le workflow, l'hôte de service de workflow gère les instances de workflow en les chargeant et en les déchargeant. Pour démarrer une instance de la définition de Windows Workflow Foundation (WF) (sur l’hôte de service de flux de travail), définissez un client qui envoie un message à la <xref:System.ServiceModel.Activities.Receive> activité dans le flux de travail. Ce <xref:System.ServiceModel.Activities.Receive> a sa propriété <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> qui a la valeur `true`, ce qui lui permet de créer une instance du workflow une fois qu'il reçoit un message.  
  
 Pendant l'initialisation, un comportement de déchargement d'instance est ajouté au fichier de configuration qui spécifie l'hôte de service de workflow sous lequel il doit décharger une instance dans le magasin de persistance (base de données). Pour cet exemple, il décharge l'instance immédiatement après le passage du workflow à l'état inactif (lorsque le délai est déclenché).  
  
#### <a name="to-use-this-sample"></a>Pour utiliser cet exemple  
  
1.  Ouvrez une invite de commandes [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Naviguez jusqu'au dossier DurableDelayXamlx\CS.  
  
3.  Exécutez Setup.cmd.  
  
4.  Exécutez [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] en tant qu'administrateur.  
  
5.  Ouvrez le fichier solution DurableDelayXamlx.sln.  
  
6.  Dans **l’Explorateur de solutions**, avec le bouton droit de la solution et sélectionnez **propriétés**.  
  
7.  Sélectionnez **plusieurs projets de démarrage** et les deux projets la valeur **Démarrer**.  
  
8.  Pour générer la solution, appuyez sur Ctrl+Maj+B.  
  
9. Pour exécuter la solution, appuyez sur Ctrl+F5.  
  
#### <a name="to-uninstall-this-sample"></a>Pour désinstaller cet exemple  
  
1.  Ouvrez une invite de commandes [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Naviguez jusqu'au dossier DurableDelayXamlx\CS.  
  
3.  Exécutez Cleanup.cmd.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à la page [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les exemples [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`

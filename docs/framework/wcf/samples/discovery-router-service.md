---
title: Discovery Router Service
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 166f6b9d1055e36f987e6b9a81fe69dc8bd548b9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318765"
---
# <a name="discovery-router-service"></a>Discovery Router Service
Cet exemple montre comment transférer des messages de découverte à un autre point de terminaison.  
  
## <a name="demonstrates"></a>Démonstrations  
 Routage de découverte  
  
## <a name="discussion"></a>Discussion  
 Le routage de découverte est utile dans un scénario où un client recherche un service à l'aide d'un proxy et que le proxy ne connaît pas ce service, mais connaît l'existence d'un autre proxy. Ce proxy peut transférer le paquet de découverte de ce client au deuxième proxy. Le deuxième proxy peut rechercher le service et retourner les réponses au client d'origine.  
  
 Dans cet exemple, un client envoie un message à un composant de routage de découverte. Ce message est envoyé à un point de terminaison spécifique situé sur le routeur de découverte. Le routeur transfère alors le message à un point de terminaison de multidiffusion UDP. Le message Probe rejoint le point de terminaison de multidiffusion et un service à l'écoute d'une adresse de multidiffusion UDP répond à ce routeur de découverte. Le routeur de découverte collecte les réponses et les renvoie au client.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Pour configurer, générer et exécuter l'exemple  
  
1. Créez un exemple.  
  
2. Exécutez le fichier exécutable DiscoveryRouter.  
  
3. Exécutez le fichier exécutable du service à partir du répertoire de build.  
  
4. Exécutez le fichier exécutable du client. Notez que le client trouve le service.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`

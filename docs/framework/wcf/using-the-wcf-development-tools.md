---
title: Utilisation des outils de développement WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e315c9e77eace9bdb0e66abed203452e5d7f9bb
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="using-the-wcf-development-tools"></a>Utilisation des outils de développement WCF
Cette section décrit les outils de développement Visual Studio qui peuvent vous aider à développer votre [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.  
  
 Vous pouvez utiliser les modèles Visual Studio comme base pour rapidement générer votre propre service, puis utilisez [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hôte de Service et [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client Test pour déboguer et tester votre service. Ces outils offrent un cycle de débogage et de test rapide et transparent tout en supprimant l’obligation de se limiter à un modèle d’hébergement à un stade précoce.  
  
## <a name="the-wcf-developer-tools"></a>Outils WCF Developer  
 [Modèles Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Vous pouvez utiliser les modèles de projet et d’élément prédéfinis de Visual Studio dans Visual Studio pour générer rapidement [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services et applications s’y rapportant.  
  
 [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 Le [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hôte de Service (WcfSvcHost.exe) vous permet de lancer le débogueur Visual Studio (F5) pour héberger et tester un service que vous avez implémenté automatiquement. Vous pouvez ensuite tester le service à l'aide du client test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) ou de votre propre client, afin de rechercher et de résoudre les erreurs potentielles.  
  
 [Client test WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Le client test [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) est un outil GUI qui permet d'entrer des paramètres de types arbitraires, d'envoyer ces entrées au service et d'afficher la réponse que le service renvoie. Il offre des conditions de test de service transparentes lorsqu'il est associé à l'Hôte de service [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 [Génération de classes de type de données à partir de XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 Les données XML stockées dans le presse-papiers peuvent être collées dans une page de codes. Les classes définies dans les données sont converties en types de codes.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilisation des outils sans privilège d'administrateur  
 Pour permettre aux utilisateurs sans privilèges d’administrateur de développer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, une liste ACL (Access Control List) est créée pour l’espace de noms «http://+:8731/Design_Time_Addresses» lors de l’installation de Visual Studio. La liste ACL a la valeur (UI), qui inclut tous les utilisateurs interactifs ayant ouvert une session sur l'ordinateur. Les administrateurs peuvent ajouter ou supprimer des utilisateurs de cette liste ACL ou ouvrir des ports supplémentaires. Cette liste ACL permet aux modèles WCF ou WF d'envoyer et de recevoir des données dans leur configuration par défaut. Elle permet également aux utilisateurs d'utiliser l'Hôte de service [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) sans leur accorder de privilèges d'administrateur.  
  
 Vous pouvez modifier l'accès à l'aide de l'outil Netsh.exe dans [!INCLUDE[wv](../../../includes/wv-md.md)] par le biais du compte d'administrateur supérieur. L'utilisation de Netsh.exe est illustrée dans l'exemple suivant.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] Netsh.exe, consultez [comment utiliser l’outil Netsh.exe et les commutateurs de ligne de commande](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [Client test WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)

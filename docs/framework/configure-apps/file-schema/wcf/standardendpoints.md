---
title: <standardEndpoints>
ms.date: 03/30/2017
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
ms.openlocfilehash: 66b86647689ea2ca39ae2f569d275aff1f48cba5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190273"
---
# <a name="standardendpoints"></a>\<standardEndpoints>
Cette section de configuration vous permet de définir une collection de points de terminaison standard, qui sont des points de terminaison préconfigurés et réutilisables. Un point de terminaison standard possède un ou plusieurs attributs d’adresse, de liaison et de contrat ayant une valeur fixe. Par exemple, dans le point de terminaison de découverte, le contrat est fixe. Vous pouvez également utiliser des points de terminaison standard pour étendre le point de terminaison de service avec de nouvelles propriétés, ce qui revient à définir des liaisons personnalisées.  
  
 \<system.ServiceModel>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
 Aucun.  
  
### <a name="child-elements"></a>Éléments enfants  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|Définit un point de terminaison standard avec un contrat d'annonce fixe. Un service peut éventuellement annoncer sa disponibilité en envoyant un message d'annonce en ligne ou hors connexion selon qu'il est respectivement ouvert ou fermé. Un service Windows Communication Foundation (WCF) spécifie les points de terminaison d’annonce dans le [ \<serviceDiscovery >](servicediscovery.md) élément et utilise AnnouncementClient pour effectuer les annonces. Un client souhaite écouter pour l’annonce provenant d’un autre service joue en fait un service WCF ; Par conséquent, vous devez configurer les points de terminaison d’annonce pour ce client dans le [ \<services >](services.md) section.|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|Définit un point de terminaison standard avec un contrat de découverte fixe. Lorsqu'il est ajouté à la configuration du service, il spécifie où écouter les messages de découverte. Lorsqu'il est ajouté à la configuration client, il spécifie où envoyer les requêtes de découverte.|  
|[\<dynamicEndpoint>](dynamicendpoint.md)|Cet élément de configuration définit un point de terminaison standard qui contient des informations pour permettre à une application de fonctionner en tant que programme client qui peut rechercher l'adresse du point de terminaison de manière dynamique au moment de l'exécution.|  
|[\<mexEndpoint>](mexendpoint.md)|Définit un point de terminaison standard avec un contrat IMetadataExchange fixe. Puisque tous les points de terminaison d'échange de métadonnées ont comme contrat IMetadataExchange, vous pouvez utiliser ce point standard au lieu d'en définir un à votre intention.|  
|[\<udpAnnouncementEndpoint>](udpannouncementendpoint.md)|Définit un point de terminaison standard qui permet aux services d’envoyer des messages d’annonce via une liaison UDP. Il a un contrat fixe et prend en charge deux versions de découverte. De plus, il possède une liaison UDP fixe et une valeur d'adresse par défaut indiquée dans les spécifications WS-Discovery (WS-Discovery Avril 2005 ou WS-Discovery version 1.1). Vous pouvez spécifier l'adresse de multidiffusion à utiliser pour l'envoi et la réception de messages d'annonce.|  
|[\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md)|Définit un point de terminaison standard, préconfiguré pour les opérations de découverte sur une liaison de multidiffusion UDP. Ce point de terminaison a un contrat fixe et prend en charge deux versions de protocole WS-Discovery. De plus, il a une liaison UDP fixe et une valeur d’adresse par défaut indiquée dans les spécifications WS-Discovery (WS-Discovery Avril 2005 ou WS-Discovery V1.1).|  
|[\<webHttpEndpoint>](webhttpendpoint.md)|Définit un point de terminaison standard avec fixe [ \<webHttpBinding >](webhttpbinding.md) automatiquement une liaison qui ajoute le [ \<webHttp >](webhttp.md) comportement. Utilisez ce point de terminaison lors de l'écriture d'un service REST.|  
|[\<webScriptEndpoint>](webscriptendpoint.md)|Définit un point de terminaison standard avec fixe [ \<webHttpBinding >](webhttpbinding.md) automatiquement une liaison qui ajoute le [ \<enableWebScript >](enablewebscript.md) comportement. Utilisez ce point de terminaison lorsque vous écrivez un service appelé à partir d'une application ASP.NET AJAX.|  
|[\<workflowControlEndpoint>](workflowcontrolendpoint.md)|Définit un point de terminaison standard permettant de contrôler l'exécution d'instances de flux de travail (créer, exécuter, interrompre, arrêter, etc.).|  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|\<system.ServiceModel>|Élément racine de tous les éléments de configuration WCF.|  
  
## <a name="see-also"></a>Voir aussi

- [Points de terminaison standard](../../../../../docs/framework/wcf/feature-details/standard-endpoints.md)

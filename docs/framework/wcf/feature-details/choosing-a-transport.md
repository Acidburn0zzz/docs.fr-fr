---
title: Choix d'un transport
ms.date: 03/30/2017
helpviewer_keywords:
- choosing transports [WCF]
ms.assetid: b169462b-f7b6-4cf4-9fca-d306909ee8bf
ms.openlocfilehash: 4d5fe4c92f0d456942219bc3f7014f09a005aa5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107846"
---
# <a name="choosing-a-transport"></a>Choix d'un transport
Cette rubrique traite des critères permettant de choisir parmi les trois principaux transports inclus dans Windows Communication Foundation (WCF) : HTTP, TCP et canaux nommés. WCF inclut également un message queuing (également appelé MSMQ) de transport, mais ce document ne couvre pas de message queuing.  
  
 Le modèle de programmation WCF sépare les opérations de point de terminaison (comme cela est exprimé dans un contrat de service) à partir du mécanisme de transport qui connecte deux points de terminaison. Vous pouvez ainsi décider du mode d'exposition de vos services sur le réseau.  
  
 Dans WCF, vous spécifiez comment transférer des données sur un réseau entre les points de terminaison à l’aide un *liaison*, qui se compose d’une séquence de *éléments de liaison*. Un transport est représenté par un élément de liaison de transport qui fait partie de la liaison. Une liaison inclut des éléments de liaison de protocole facultatifs (la sécurité par exemple), un élément de liaison d’encodeur de message requis et un élément de liaison de transport requis. Un transport envoie ou reçoit la forme sérialisée d'un message depuis ou vers une autre application.  
  
 Si vous devez vous connecter à un client ou un serveur existant, vous n'aurez peut-être pas le choix d'utiliser un transport particulier. Toutefois, les services WCF peuvent être accessibles via plusieurs points de terminaison, chacun avec un transport différent. Lorsqu'un transport unique ne couvre pas l'audience prévue pour votre service, vous pouvez exposer le service sur plusieurs points de terminaison. Les applications clientes peuvent utiliser ensuite le point de terminaison le mieux adapté.  
  
 Après avoir choisi un transport, vous devez sélectionner une liaison qui l’utilise. Vous pouvez choisir une liaison fournie par le système (consultez [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md)), ou vous pouvez générer votre propre liaison personnalisée (consultez [liaisons personnalisées](../../../../docs/framework/wcf/extending/custom-bindings.md)). Vous pouvez également créer votre propre liaison. Pour plus d’informations, consultez [Creating liaisons](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).  
  
## <a name="advantages-of-each-transport"></a>Avantages de chaque transport  
 Cette section décrit les raisons principales motivant le choix d'un des trois principaux transports, ainsi qu'un tableau de prise de décision détaillé pour effectuer ce choix.  
  
### <a name="when-to-use-http-transport"></a>Quand utiliser le transport HTTP  
 HTTP est un protocole de demande/réponse entre clients et serveurs. L'application la plus courante se compose de clients de navigateur Web qui communiquent avec un serveur Web. Le client envoie une demande à un serveur qui écoute les messages de demande du client. Lorsque le serveur reçoit une demande, il renvoie une réponse qui contient l'état de la demande. Si cette demande aboutit, des données facultatives, telles qu’une page web, un message d’erreur ou autres informations, sont retournées. Pour plus d’informations sur le protocole HTTP, consultez [HTTP - Hypertext Transfer Protocol](https://go.microsoft.com/fwlink/?LinkId=94858).  
  
 Le protocole HTTP n'est pas basé sur une connexion ; une fois la réponse envoyée, aucun état n'est maintenu. Pour gérer des transactions de plusieurs pages, l’application doit rendre persistant tout état nécessaire.  
  
 Dans WCF, le transport HTTP liaison est optimisée pour l’interopérabilité avec les systèmes hérités non-WCF. Si toutes les parties communicantes sont à l’aide de WCF, les liaisons de basée sur des canaux nommés ou basé sur TCP sont plus rapides. Pour plus d’informations, consultez <xref:System.ServiceModel.NetTcpBinding> et <xref:System.ServiceModel.NetNamedPipeBinding>.  
  
### <a name="when-to-use-the-tcp-transport"></a>Quand utiliser le transport TCP  
 TCP est un service de remise basé sur une connexion, orienté flux qui permet la détection et la correction d'erreurs de bout en bout. *Par connexion* signifie qu’une session de communication entre les ordinateurs hôtes est établie avant l’échange de données. Un hôte est un périphérique sur un réseau TCP/IP identifié par une adresse IP logique.  
  
 TCP permet une remise fiable des données tout en étant simple d'utilisation. En particulier, TCP notifie l'expéditeur de la remise de paquets, s'assure que les paquets sont remis dans le même ordre dans lequel ils sont envoyés, retransmet les paquets perdus et garantit que les paquets de données ne sont pas dupliqués. Notez que cette remise fiable s’applique entre deux nœuds TCP/IP et n’est pas la même chose que *WS-ReliableMessaging*, auquel s’applique entre les points de terminaison, quel que soit le nombre de nœuds intermédiaires, elles peuvent inclure.  
  
 Le transport TCP de WCF est optimisé pour le scénario où les deux extrémités de la communication sont à l’aide de WCF. Cette liaison est la liaison WCF le plus rapide pour les scénarios qui impliquent des communications entre des ordinateurs différents. Les échanges de messages utilisent le <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> pour le transfert de messages optimisé. TCP fournit une communication duplex et peut être ainsi utilisé pour implémenter des contrats duplex, même si le client est placé derrière une traduction d'adresses réseau (NAT).  
  
### <a name="when-to-use-the-named-pipe-transport"></a>Quand utiliser le transport de canal nommé  
 Un canal nommé est un objet dans le noyau du système d'exploitation Windows, tel qu'une portion de mémoire partagée utilisée par les processus pour la communication. Un canal nommé possède un nom et peut être utilisé pour la communication unidirectionnelle ou duplex entre des processus sur un ordinateur unique.  
  
 Lorsque la communication est requise entre les différentes applications WCF sur un seul ordinateur, et que vous souhaitez empêcher toute communication provenant d’un autre ordinateur, puis utiliser le transport de canaux nommés. Une restriction supplémentaire est que les processus qui s'exécutent du Bureau à distance Windows peuvent être limités à la même session de Bureau à distance Windows sauf s'ils possèdent des privilèges élevés.  
  
> [!WARNING]
>  Lorsque vous utilisez le transport de canal nommé avec une réservation d’URL WeakWildcard sur plusieurs sites hébergés dans IIS, l’erreur suivante peut se produire : Une erreur s’est produite dans le Service d’Activation « NetPipeActivator » du protocole « net.pipe » lors de la tentative d’écoute pour le site « 2 », par conséquent, le protocole est temporairement désactivé pour le site. Consultez le message d’exception pour plus d’informations. URL : WeakWildcard:net.pipe:/\<nom_machine > / état : ConflictingRegistration Exception :  Nom du processus : ID de processus de SMSvcHost : 1076\  
  
## <a name="decision-points-for-choosing-a-transport"></a>Points de décision permettant de choisir un transport  
 Le tableau suivant décrit les points de décision courants permettant de choisir un transport. Vous devez considérer tous les attributs et les transports supplémentaires qui s'appliquent à votre application. Identifiez les attributs qui sont importants pour votre application, les transports qui s'associent le mieux à chacun de vos attributs, puis sélectionnez les transports qui fonctionnent le mieux avec votre jeu d'attributs.  
  
|Attribut|Description|Transports préconisés|  
|---------------|-----------------|------------------------|  
|Diagnostics|Les diagnostics vous permettent de détecter automatiquement les problèmes de connectivité de transport. Tous les transports prennent en charge la possibilité de renvoyer des informations de panne qui décrivent la connectivité. Cependant, WCF n’inclut pas les outils de diagnostic pour l’examen des problèmes de réseau.|Aucun.|  
|Hébergement|Tous les points de terminaison WCF doivent être hébergés dans une application. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] antérieure prise en charge et que l’hébergement des applications qui utilisent le transport HTTP. Sur [!INCLUDE[wv](../../../../includes/wv-md.md)], prise en charge est ajoutée pour héberger tous les transports WCF, y compris TCP et canaux nommé. Pour plus d’informations, consultez [hébergement dans Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md) et [hébergement dans Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).|HTTP|  
|Inspection|L'inspection est la capacité d'extraire et de traiter les informations des messages au cours de la transmission. Le protocole HTTP effectue le tri entre les informations de routage et de contrôle, et les données, ce qui simplifie la création d'outils chargés d'inspecter et d'analyser des messages. Les transports qui sont faciles à inspecter peuvent également nécessiter une puissance de traitement moindre dans les appareils de réseau. Le niveau de sécurité utilisé détermine la possibilité d'inspecter ou non les messages.|HTTP|  
|Latence|La latence est la durée minimale requise pour procéder à un échange de messages. Toutes les opérations de réseau offrent plus ou moins de latence selon le choix de transport. L’utilisation de la communication en duplex ou unidirectionnelle avec un transport dont le modèle d’échange de messages natif est demande/réponse (HTTP, par exemple) peut provoquer une latence supplémentaire en raison de la corrélation forcée des messages. Dans ce cas, vous pouvez utiliser un transport dont le modèle d’échange de messages natif est duplex, tel que TCP.|TCP, Canal<br /><br /> nommé|  
|Portée|La portée d'un transport décrit la capacité de connexion de ce transport avec d'autres systèmes. Le transport de canal nommé a une portée très réduite ; il peut se connecter uniquement aux services qui s'exécutent sur le même ordinateur. Les transports TCP et HTTP ont une portée excellente et peuvent pénétrer des configurations NAT et de pare-feu. Pour plus d’informations, consultez [utilisation des NAT et pare-feu](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md).|HTTP, TCP|  
|Sécurité|La sécurité est la capacité à protéger des messages au cours du transfert en fournissant la confidentialité, l'intégrité ou l'authentification. La confidentialité empêche l'analyse d'un message, l'intégrité empêche sa modification et l'authentification garantit l'expéditeur ou le destinataire du message.<br /><br /> WCF prend en charge la sécurité de transfert à la fois au niveau de message et au niveau du transport. La sécurité du message compose avec un transport si le transport prend en charge un mode de transfert mis en mémoire tampon. La prise en charge de la sécurité du transport varie selon le choix du transport. Les transports HTTP, TCP et de canal nommé gèrent de manière similaire la prise en charge de la sécurité du transport.|Tous|  
|Débit|Le débit mesure la quantité de données qui peuvent être transmises et traitées dans une période spécifiée. Comme pour la latence, le choix du transport peut affecter le débit pour les opérations de service. Pour augmenter le débit pour un transport, il est nécessaire de réduire à la fois les charges mémoire de transmission du contenu et la durée d'attente pour les échanges de messages. Les transports TCP et de canaux nommés ajoutent peu de charges mémoire au corps du message et prennent en charge une forme duplex native qui réduit le temps de réponse des messages.|TCP, canal nommé|  
|Outillage|L'outillage correspond à la prise en charge par des applications tierces d'un protocole pour le développement, le diagnostic, l'hébergement et autres activités. Le développement d'outils et de logiciels compatibles avec le protocole HTTP implique un investissement particulièrement important.|HTTP|  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- [Liaisons](../../../../docs/framework/wcf/feature-details/bindings.md)
- [Liaisons fournies par le système](../../../../docs/framework/wcf/system-provided-bindings.md)
- [Création de liaisons définies par l’utilisateur](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)

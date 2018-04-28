---
title: Sécurité Overview1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, security
- WCF, security
ms.assetid: f478c80d-792d-4e7a-96bd-a2ff0b6f65f9
caps.latest.revision: 37
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: a50b3d3ec2a99d53bc7d5817f3ed530ef92d474b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="security-overview"></a>Vue d'ensemble de la sécurité
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] est une plateforme de programmation distribuée basée sur les messages SOAP, et la sécurisation des messages entre les clients et les services est essentielle à la protection des données. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fournit une plateforme souple et interopérable pour échanger des messages sécurisés qui reposent sur l'infrastructure de sécurité existante et les normes de sécurité reconnues pour les messages SOAP.  
  
> [!NOTE]
>  Pour obtenir un guide complet sur la sécurité WCF, consultez [Guide de sécurité WCF](http://go.microsoft.com/fwlink/?LinkID=158912).  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilise des concepts qui sont familiers si vous avez construit des applications distribuées sécurisées avec les technologies existantes telles que HTTPS, la sécurité intégrée de Windows ou des noms d'utilisateur et des mots de passe pour authentifier des utilisateurs. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] s'intègre non seulement aux infrastructures de sécurité existantes, mais étend aussi la sécurité distribuée au delà des domaines propres à Windows en utilisant des messages SOAP sécurisés. Prenons l'exemple de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] qui offre une implémentation de mécanismes de sécurité existants et l'avantage majeur d'utiliser SOAP comme protocole en plus des protocoles existants. Par exemple, les informations d'identification qui identifient un client ou un service, telles que le nom d'utilisateur et le mot de passe ou les certificats X.509, ont des profils SOAP basés sur du XML interopérable. À l'aide de ces profils, les messages sont échangés en toute sécurité et tirent parti des spécifications ouvertes telles que les signatures numériques XML et le chiffrement XML. Pour obtenir la liste de spécifications, consultez [Web Services protocoles pris en charge par les liaisons d’interopérabilité fournies par](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
 Un autre parallèle est le modèle COM (Component Object Model) sur la plateforme Windows qui active des applications distribuées et sécurisées. COM offre un mécanisme de sécurité complet qui permet la transmission du contexte de sécurité entre des composants ; ce mécanisme met en vigueur l'intégrité, la confidentialité et l'authentification. Cependant, COM ne permet pas la messagerie multiplateforme, sécurisée comme le permet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. À l'aide de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vous pouvez générer des services et des clients qui couvrent les domaines Windows jusqu'à Internet. Les messages interopérables de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sont essentiels pour générer des services dynamiques orientés vers les affaires qui inspirent la confiance dans la sécurité de vos informations.  
  
## <a name="windows-communication-foundation-security-benefits"></a>Avantages de la sécurité dans Windows Communication Foundation  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] est une plateforme de programmation distribuée basée sur les messages SOAP. À l'aide de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vous pouvez créer des applications qui fonctionnent comme des services et des clients de service pour créer et traiter des messages issus d'un nombre illimité d'autres services et clients. Dans ce type d'application distribuée, les messages peuvent circuler d'un nœud à l'autre, à travers des pare-feu, sur Internet, et par l'intermédiaire de nombreux intermédiaires SOAP. Ces possibilités introduisent plusieurs menaces pour la sécurité des messages. Les exemples suivants illustrent certaines menaces courantes que la sécurité [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] peut aider à atténuer lorsque des entités échangent des messages :  
  
-   Observation du trafic réseau pour obtenir des informations sensibles. Par exemple, dans un scénario de transactions bancaires, un client effectue une demande de transfert de fonds d'un compte à un autre. Un utilisateur malveillant intercepte le message et, s'il dispose du numéro de compte et du mot de passe, effectue un transfert de fonds à partir du compte compromis.  
  
-   Entités malveillantes agissant en tant que services à l'insu du client. Dans ce scénario, un utilisateur malveillant (l'escroc) agit comme un service en ligne et intercepte des messages du client pour obtenir des informations sensibles. Puis, l'escroc utilise les données volées pour transférer des fonds du compte compromis. Cette attaque s’appelle également un *hameçonnage*.  
  
-   Modification de messages en vue d'obtenir un résultat différent de celui souhaité par l'appelant. Par exemple, modifier le numéro de compte dans lequel est effectué un dépôt permet aux fonds d'être détourné au profit d'un compte malveillant.  
  
-   Piratage informatique où le pirate informatique relit le même bon de commande. Par exemple, une librairie en ligne reçoit des centaines de commandes et envoie les ouvrages à un client qui ne les a pas commandés.  
  
-   Incapacité d'un service à authentifier un client. Dans ce cas, le service ne peut pas garantir que la personne appropriée a effectué la transaction.  
  
 En résumé, la sécurité de transfert fournit les garanties suivantes :  
  
-   Authentification du point de terminaison (répondant) du service.  
  
-   Authentification principale (initiateur) du client.  
  
-   Intégrité des messages.  
  
-   Confidentialité des messages.  
  
-   Détection des relectures.  
  
### <a name="integration-with-existing-security-infrastructures"></a>Intégration avec les infrastructures de sécurité existantes  
 Souvent, les déploiements de service Web contiennent des solutions de sécurité existantes, par exemple, le protocole SSL (Secure Sockets Layer) ou Kerberos. Certains tirent parti d'une infrastructure de sécurité qui a déjà été déployée, telle que les domaines Windows qui utilisent Active Directory. Il est souvent nécessaire d'intégrer ces technologies existantes tout en évaluant et en adoptant les nouvelles.  
  
 La sécurité [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] s'intègre aux modèles de sécurité de transport existants et peut tirer parti de l'infrastructure existante pour les modèles de sécurité de transfert plus récents basés sur la sécurité des messages SOAP.  
  
### <a name="integration-with-existing-authentication-models"></a>Intégration avec les modèles d'authentification existants  
 Un élément important de tout modèle de sécurité de communication réside dans sa capacité à identifier et authentifier des entités dans la communication. Ces entités dans la communication font appel à des « identités numériques », ou des informations d'identification, pour s'authentifier auprès des correspondants homologues. Au fur et à mesure de l'évolution des plateformes de communication distribuées, divers modèles d'authentification d'informations d'identification et de sécurité apparentés ont été implémentés. Par exemple, sur Internet, l'utilisation d'un nom d'utilisateur et d'un mot de passe pour identifier les utilisateurs est courante. Sur un intranet, l'utilisation d'un contrôleur de domaine Kerberos pour sauvegarder l'authentification de l'utilisateur et du service est une pratique de plus en plus courante. Dans certains scénarios, comme entre deux associés, des certificats peuvent être utilisés pour authentifier les partenaires mutuellement.  
  
 Ainsi, dans le monde des services Web, où le même service peut être exposé à des clients d'entreprise internes aussi bien qu'aux partenaires externes ou à des clients Internet, il est important que l'infrastructure fournisse l'intégration avec les modèles d'authentification de sécurité existants. La sécurité [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] prend en charge un large éventail de types d'informations d'identification (modèles d'identification), notamment :  
  
-   Appelant anonyme.  
  
-   Informations d'identification du client de nom d'utilisateur.  
  
-   Informations d'identification du client de certificat.  
  
-   Windows (protocoles Kerberos et NT LanMan [NTLM]).  
  
### <a name="standards-and-interoperability"></a>Normes et interopérabilité  
 Dans un monde où évoluent des grands déploiements, l'homogénéité est rare. Les plateformes de traitement/communications distribuées doivent interagir avec les technologies offertes par les différents fournisseurs. De même, la sécurité doit aussi être interopérable.  
  
 Pour permettre l'utilisation des systèmes de sécurité interopérables, les entreprises actives dans l'industrie des services Web ont créé diverses normes. Dans le domaine spécifique de la sécurité, certaines normes importantes ont été proposées : WS-Security : la sécurité des messages SOAP (acceptée par l'organisme de normalisation OASIS, anciennement WS-Security), WS-Trust, WS-SecureConversation et WS-SecurityPolicy.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] prend en charge une large gamme de scénarios d'interopérabilité. La classe <xref:System.ServiceModel.BasicHttpBinding> est concernée par BSP (Basic Security Profile) et la classe <xref:System.ServiceModel.WSHttpBinding> est concernée par les normes de sécurité les plus récentes, telles que WS-Security 1.1 et WS-SecureConversation. En adhérant à ces normes, la sécurité [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] peut interagir et s'intégrer aux services Web hébergés sur les systèmes d'exploitation et les plateformes autres que Microsoft Windows.  
  
## <a name="wcf-security-functional-areas"></a>Zones fonctionnelles de sécurité WCF  
 La sécurité [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] est divisée en trois zones fonctionnelles : la sécurité de transfert, le contrôle d'accès et l'audit. Les sections suivantes traitent brièvement de ces zones et fournissent des liens vers des informations supplémentaires.  
  
### <a name="transfer-security"></a>Sécurité de transfert  
 La sécurité de transfert comprend trois fonctions de sécurité majeures : l'intégrité, la confidentialité et l'authentification. *Intégrité* est la possibilité de détecter si un message a été falsifié. *Confidentialité* est la possibilité de rendre un message illisible par une autre personne que le destinataire souhaité ; cela est possible au chiffrement. *Authentification* est la possibilité de vérifier une identité déclarée. Ensemble, cette trois fonctions permettent de garantir que les messages arrivent de manière sécurisée d'un point à un autre.  
  
#### <a name="transport-and-message-security-modes"></a>Modes de sécurité du transport et du message  
 Deux mécanismes principaux sont utilisés pour implémenter la sécurité de transfert dans [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]: *transport* mode de sécurité et *message* mode de sécurité.  
  
-   *Mode de sécurité de transport* utilise un protocole au niveau du transport, tel que HTTPS, pour garantir la sécurité de transfert. Le mode de transport a l'avantage d'être adopté largement, d'être disponible sur de nombreuses plateformes, et de présenter un traitement moins complexe. Toutefois, il a l'inconvénient de ne permettre que la sécurisation des messages de point à point.  
  
-   *Mode de sécurité de message*, en revanche, utilise WS-Security (et autres spécifications) pour implémenter la sécurité de transfert. Étant donné que la sécurité de message est appliquée directement aux messages SOAP et qu'elle est contenue à l'intérieur des enveloppes SOAP, ainsi que les données d'application, elle a l'avantage d'être indépendante du protocole de transport, d'être plus extensible, et de garantir la sécurité de bout en bout (au lieu de point à point) ; son inconvénient est d'être nettement plus lente que le mode de sécurité du transport parce qu'elle doit traiter la nature XML des messages SOAP.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Ces différences, consultez [sécurisation des Services et les Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).  
  
 Un troisième mode de sécurité utilise les deux modes précédents en offrant leurs avantages. Ce mode est appelé `TransportWithMessageCredential`. Dans ce mode, la sécurité de message est utilisée pour authentifier le client et la sécurité de transport est utilisée pour authentifier le serveur et fournir la confidentialité et l'intégrité des messages. Grâce à ces fonctions, le mode de sécurité `TransportWithMessageCredential` est presque aussi rapide que le mode de sécurité de transport et permet l'extensibilité de l'authentification du client de la même manière que la sécurité de message. Toutefois, il ne permet pas la sécurité complète de bout en bout contrairement au mode de sécurité de message.  
  
### <a name="access-control"></a>Contrôle d'accès  
 *Contrôle d’accès* est également connu sous le nom de l’autorisation. *Autorisation* permet à différents utilisateurs d’avoir des privilèges différents pour afficher les données. Par exemple, étant donné que les fichiers des ressources humaines d'une entreprise contiennent des données sensibles sur les employés, seuls les responsables sont autorisés à consulter ces données. De plus, les responsables peuvent consulter uniquement les données se rapportant à leurs collaborateurs directs. Dans ce cas, le contrôle d'accès est basé sur le rôle (« responsable ») ainsi que l'identité spécifique du responsable (pour empêcher un responsable de consulter les informations relatives aux employés d'un autre responsable).  
  
 Dans [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], fonctionnalités de contrôle d’accès sont fournies via l’intégration avec le common language runtime (CLR) <xref:System.Security.Permissions.PrincipalPermissionAttribute> et d’un jeu d’API identifié comme le *modèle d’identité*. Pour plus d’informations sur le contrôle d’accès et d’autorisation basée sur les revendications, consultez [extension de sécurité](../../../../docs/framework/wcf/extending/extending-security.md).  
  
### <a name="auditing"></a>Audit  
 *L’audit* est la journalisation des événements de sécurité dans le journal des événements Windows. Vous pouvez enregistrer des événements relatifs à la sécurité, tels que les échecs (ou les succès) d'authentification. Pour plus d’informations, consultez [audit](../../../../docs/framework/wcf/feature-details/auditing-security-events.md). Pour plus d’informations de programmation, consultez [Comment : auditer les événements de sécurité](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [Sécurisation de services](../../../../docs/framework/wcf/securing-services.md)  
 [Scénarios de sécurité courants](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 [Liaisons et sécurité](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [Sécurisation des services et des clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Authentification](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 [Autorisation](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Fédération et jetons émis](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Audit](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [Aide sur la sécurité et bonnes pratiques](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [Configuration des services à l’aide de fichiers de configuration](../../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [Liaisons fournies par le système](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [Vue d’ensemble de la création de points de terminaison](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Extension de la sécurité](../../../../docs/framework/wcf/extending/extending-security.md)  
 [Modèle de sécurité pour Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)

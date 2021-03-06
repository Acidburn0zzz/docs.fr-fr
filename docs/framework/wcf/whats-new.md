---
title: Nouveautés dans Windows Communication Foundation 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], what's new
- Windows Communication Foundation [WCF], what's new
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
ms.openlocfilehash: eb506680f370e3571f1c38276d4e5d5890887a63
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492736"
---
# <a name="whats-new-in-windows-communication-foundation-45"></a>Nouveautés dans Windows Communication Foundation 4.5

Cette rubrique traite des fonctionnalités de nouveau à la version 4.5 de Windows Communication Foundation (WCF).

## <a name="wcf-simplification-features"></a>Fonctionnalités de simplification de WCF

Beaucoup de travail a été effectué pour faciliter le développement et la gestion des applications WCF 4.5. Pour plus d’informations, consultez [les fonctionnalités de Simplification de WCF](../../../docs/framework/wcf/wcf-simplification-features.md).

### <a name="task-based-async-support"></a>Prise en charge du modèle asynchrone basé sur les tâches

Par défaut, la fonctionnalité Ajouter une référence de service génère des méthodes d’opération de service asynchrone retournant des tâches. Cette opération est effectuée pour les méthodes synchrones et asynchrones. Cela vous permet d’appeler les opérations de service de façon asynchrone à l’aide du modèle de programmation asynchrone basé sur les tâches. Lorsque vous appelez la méthode de proxy générée, WCF construit un objet Tâche pour représenter l’opération asynchrone et retourne cette tâche. La tâche se termine lorsque l’opération se termine. Lors de l’implémentation d’une opération asynchrone, vous pouvez l’implémenter en tant qu’une opération asynchrone basé sur des tâches. Pour plus d’informations, consultez [synchrone et opérations asynchrones](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).

### <a name="simplified-generated-configuration-files"></a>Fichiers de configuration générés simplifiés

Lorsque vous ajoutez une référence de service dans Visual Studio ou utilisez l'outil SvcUtil.exe, un fichier de configuration client est généré. Dans les versions antérieures de WCF, ces fichiers de configuration contenaient la valeur de chaque propriété de liaison et ce, même si sa valeur était la valeur par défaut. Dans WCF 4.5, les fichiers de configuration générés contiennent uniquement les propriétés de liaison qui ont une valeur non définie par défaut.

Pour plus d’informations, consultez [fonctionnalités de Simplification de WCF](../../../docs/framework/wcf/wcf-simplification-features.md)

### <a name="contract-first-development"></a>Développement Contrat en premier

WCF prend désormais en charge le développement Contrat en premier. Svcutil.exe a un commutateur /serviceContract qui vous permet de générer des contrats de service et des données à partir d’un document WSDL.

### <a name="add-service-reference-from-a-portable-subset-project"></a>Ajouter une référence de service d'un projet de sous-ensemble portable

Les projets portables du sous-ensemble permettent aux programmeurs d'assembly .NET de maintenir une arborescence source unique et le système de génération tout en prenant en charge plusieurs plateformes .NET (de bureau, Silverlight, Windows Phone et XBOX). Projets portables du sous-ensemble référencent uniquement des bibliothèques portables .NET qui sont un assemblage .NET framework qui peut être utilisé sur n’importe quelle plateforme .NET. L'expérience du développeur est identique à celle de l'ajout d'une référence de service dans une autre application cliente WCF. Pour plus d’informations, consultez [ajouter une référence de Service dans un projet de sous-ensemble Portable](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).

### <a name="aspnet-compatibility-mode-default-changed"></a>Modification de la valeur par défaut pour le mode de compatibilité ASP.NET

WCF fournit le mode de compatibilité ASP.NET pour accorder aux développeurs l'accès total aux fonctionnalités dans le pipeline HTTP ASP.NET lors de l'écriture des services WCF. Pour utiliser ce mode, vous devez définir le `aspNetCompatibilityEnabled` attribut sur true dans le [ \<serviceHostingEnvironment >](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) section du fichier web.config. De plus, la propriété `RequirementsMode` de tout service dans cet appDomain sur son <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> doit avoir la valeur <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> ou <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>. Par défaut <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> a maintenant la valeur <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>. Pour plus d’informations, consultez [What ' s New in Windows Communication Foundation](../../../docs/framework/wcf/whats-new.md) et [Services WCF et ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).

### <a name="new-transport-default-values"></a>Valeurs par défaut pour le nouveau transport

Afin de simplifier la configuration, plusieurs valeurs de propriété de transport par défaut ont été modifiées. Pour plus d’informations, consultez [les fonctionnalités de Simplification de WCF](../../../docs/framework/wcf/wcf-simplification-features.md).

### <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

<xref:System.Xml.XmlDictionaryReaderQuotas> contient des valeurs de quota configurables pour les lecteurs du dictionnaire XML qui limitent la quantité de mémoire utilisée par un encodeur lors de la création d'un message. Bien que ces quotas soient configurables, les valeurs par défaut ont changé pour réduire le risque qu'un développeur doivent les définir explicitement. Pour plus d’informations, consultez [les fonctionnalités de Simplification de WCF](../../../docs/framework/wcf/wcf-simplification-features.md).

### <a name="wcf-configuration-validation"></a>Validation de configuration WCF

Dans le cadre du processus de génération dans Visual Studio, les fichiers de configuration WCF sont maintenant validés pour les attributs définis dans le projet. Une liste d'erreurs ou d'avertissements de validation s'affiche dans Visual Studio si la validation échoue.

### <a name="xml-editor-tooltips"></a>Info-bulles de l'éditeur XML

Pour aider les développeurs de services WCF nouveaux et existants à configurer leurs services, l'Éditeur XML de Visual Studio fournit maintenant des info-bulles pour chaque élément de configuration et ses propriétés qui fait partie du fichier de configuration du service.

## <a name="streaming-improvements"></a>Améliorations de la diffusion en continu

Ajout de la prise en charge de la diffusion en continu asynchrone là où le côté expéditeur ne bloque pas les threads si le côté destinataire ne lit pas ou n'est pas lent dans la lecture, ce qui accroît l'extensibilité. Suppression de la limitation de mise en mémoire tampon des messages lorsqu'un client envoie un message transmis en continu à un service WCF hébergé par IIS. Pour plus d’informations, consultez [les fonctionnalités de Simplification de WCF](../../../docs/framework/wcf/wcf-simplification-features.md).

## <a name="simplifying-exposing-an-endpoint-over-https-with-iis"></a>Simplifier l'exposition d'un point de terminaison sur HTTPS avec IIS

Un mappage de protocole HTTPS a été ajouté pour simplifier l'exposition d'un point de terminaison sur HTTPS. Pour activer un point de terminaison HTTPS, assurez-vous que votre site web dispose d’une liaison HTTPS et d’un certificat SSL configurés, puis activez HTTPS pour le répertoire virtuel qui héberge le service. Si les métadonnées sont activées pour le service, elles seront également exposées via HTTPS.

## <a name="generating-a-single-wsdl-document"></a>Génération d'un seul document WSDL

Certaines piles de traitement WSDL tierces ne peuvent pas traiter les documents WSDL qui dépendent d'autres documents via un xsd:import. WCF vous permet maintenant de spécifier que toutes les informations WSDL doivent être retournées dans un document unique. Pour demander un document WSDL unique, ajoutez « ? singleWSDL » à l’URI lors de la demande de métadonnées à partir du service.

## <a name="websocket-support"></a>Prise en charge de WebSocket

WebSockets est une technologie qui fournit la véritable communication bidirectionnelle sur les ports 80 et 443 avec des caractéristiques de performances semblables à TCP. Deux nouvelles liaisons ont été ajoutées pour prendre en charge les communications via un transport WebSocket. Voir <xref:System.ServiceModel.NetHttpBinding> et <xref:System.ServiceModel.NetHttpsBinding>. Pour plus d'informations, consultez : [Liaisons fournies par le système](../../../docs/framework/wcf/system-provided-bindings.md).

## <a name="new-transport-default-values"></a>Valeurs par défaut pour le nouveau transport

Le tableau suivant décrit les paramètres qui ont changé et où trouver des informations supplémentaires.

|Propriété|Activé|Nouvelle valeur par défaut|Pour plus d'informations, consultez|
|--------------|--------|-----------------|------------------------------|
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 secondes|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 * nombre de processeurs|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * nombre de processeurs pour le transport<br /><br /> 4 \* nombre de processeurs pour SMSvcHost.exe|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [Configuration du Service de partage de ports Net.TCP](../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)|
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * nombre de processeurs|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|
|receiveTimeout|SMSvcHost.exe|30 secondes|[Configuration du service de partage de ports Net.TCP](../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)|

## <a name="xml-editor-tooltips"></a>Info-bulles de l'éditeur XML

Pour aider les développeurs de services WCF nouveaux et existants à configurer leurs services, l'Éditeur XML de Visual Studio fournit maintenant des info-bulles pour chaque élément de configuration et ses propriétés qui fait partie du fichier de configuration du service.

## <a name="configuring-wcf-services-in-code"></a>Configuration de services WCF dans le code

Windows Communication Foundation (WCF) permet aux développeurs de configurer les services à l’aide de fichiers de configuration ou de code. Les fichiers de configuration sont utiles lorsqu'un service doit être configuré après avoir été déployé. Lorsqu'il utilise des fichiers de configuration, un professionnel de l'informatique doit uniquement mettre à jour le fichier de configuration, aucune recompilation n'est nécessaire. Les fichiers de configuration, toutefois, peuvent être complexes et difficiles à gérer. Il n'existe aucune prise en charge du débogage de fichiers de configuration et les éléments de configuration sont référencés par des noms. La création de fichiers de configuration est donc susceptible d'engendrer des erreurs et difficile. WCF vous permet également de configurer les services dans le code. Dans les versions antérieures de configuration des services WCF (4.0 et versions antérieures) dans le code était simple dans les scénarios auto-hébergés, la <xref:System.ServiceModel.ServiceHost> classe autorisés vous permettent de configurer des points de terminaison et les comportements avant d’appeler ServiceHost.Open. Dans les scénarios hébergés sur le Web, toutefois, vous n'avez pas accès à la classe <xref:System.ServiceModel.ServiceHost>. Pour configurer un service hébergé sur le Web vous deviez créer un `System.ServiceModel.ServiceHostFactory` qui créait le <xref:System.ServiceModel.Activation.ServiceHostFactory> et effectuait la configuration nécessaire. À compter de .NET 4.5, WCF offre un moyen plus simple pour configurer les deux auto-hébergé et services dans le code hébergé sur le web. Pour plus d’informations, consultez [configuration des Services WCF dans le Code](../../../docs/framework/wcf/configuring-wcf-services-in-code.md).

## <a name="channelfactory-caching"></a>Mise en cache de ChannelFactory

Les applications clientes WCF utilisent la classe <xref:System.ServiceModel.ChannelFactory%601> pour créer un canal de communication avec un service WCF. La création d'instances <xref:System.ServiceModel.ChannelFactory%601> entraîne une certaine charge, car elle comporte les opérations suivantes :

1. Construction de l’arborescence <xref:System.ServiceModel.Description.ContractDescription>

2. Refléter tous les types CLR requis

3. Construction de la pile de canaux

4. Suppression de ressources

Pour réduire cette surcharge, WCF peut mettre en cache les fabriques de canaux lorsque vous utilisez un proxy du client WCF. Pour plus d’informations, consultez [fabrique de canaux et de mise en cache](../../../docs/framework/wcf/feature-details/channel-factory-and-caching.md).

## <a name="compression-and-the-binary-encoder"></a>Compression et encodeur binaire

Depuis WCF 4.5, l'encodeur binaire WCF ajoute la prise en charge de la compression. Le type de compression est configuré avec la propriété <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>. Le client et le service doivent configurer la propriété <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>. La compression fonctionnera pour les protocoles HTTP, HTTPS et TCP. Si un client détermine l'utilisation de la compression, mais le service ne la prend pas en charge, une exception de protocole est levée indiquant une incompatibilité de protocole. Pour plus d’informations, consultez [en choisissant un encodeur de Message](../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)

## <a name="udp"></a>UDP

Prise en charge a été ajoutée pour un transport UDP qui permet aux développeurs d’écrire des services qui utilisent des « fire and forget » de messagerie. Un client envoie un message à un service et n'attend aucune réponse de ce dernier.

## <a name="multiple-authentication-support"></a>Prise en charge de plusieurs authentifications

La prise en charge a été ajoutée pour prendre en charge plusieurs modes d'authentification, tels que pris en charge par IIS, sur un point de terminaison unique WCF lorsque vous utilisez le transport et la sécurité de transport HTTP. IIS vous permet d'activer plusieurs modes d'authentification sur un répertoire virtuel, cette fonctionnalité permet à un seul point de terminaison WCF de prendre en charge plusieurs modes d'authentification activés pour le répertoire virtuel où le service WCF est hébergé.

## <a name="idn-support"></a>Prise en charge IDN

La prise en charge a été ajoutée pour tenir compte des services WCF avec des noms IDN (Internationalized Domain Names). Pour plus d’informations, consultez [WCF et noms de domaine internationaux](../../../docs/framework/wcf/feature-details/wcf-and-internationalized-domain-names.md).

## <a name="httpclient"></a>HttpClient

Une nouvelle classe appelée <xref:System.Net.Http.HttpClient> a été ajoutée pour faciliter l'utilisation des requêtes HTTP. Pour plus d’informations, consultez [la création d’applications sociales et associées à des services HTTP](https://go.microsoft.com/fwlink/?LinkId=231886) et [exemple de Client HTTP](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).

## <a name="configuration-intellisense"></a>Configuration Intellisense

Les valeurs d'attribut dans les fichiers de configuration des attributs personnalisés définis dans le projet prennent désormais en charge Intellisense pour une utilisation rapide et correcte des configurations.

## <a name="configuration-tooltips"></a>Info-bulles de configuration

Attributs et éléments de WCF maintenant ont les info-bulles dans l’éditeur XML, plus facilement et identifient précisément l’objectif de l’élément ou attribut.

## <a name="paste-data-as-classes"></a>Coller les données sous forme de classes

Dans un projet WCF, les types de données définis en XML (tels que ceux exposés dans un service) peuvent être collés directement dans une page de codes. Le type XML sera collé comme type CLR. Consultez [générer des Classes de Type de données à partir de XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md) pour plus d’informations.

## <a name="webservicehost-and-default-endpoints"></a>WebServiceHost et points de terminaison par défaut

Dans Visual Studio 2010, WebServiceHost a automatiquement créé un point de terminaison par défaut, que vous ayez ou non spécifié explicitement un point de terminaison. Dans Visual Studio 2012 et versions ultérieures, WebServiceHost crée uniquement un point de terminaison par défaut si aucun point de terminaison n’est ajoutés explicitement. Si votre client attend le point de terminaison par défaut, vous pouvez explicitement ajouter un point de terminaison et pointez le client. Sinon, indiquez à WCF de rétablir le comportement précédent en ajoutant le paramètre suivant au fichier de configuration de l'application

```xml
<appSettings>
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>
  </appSettings>
```

## <a name="ihttpcookiecontainermanager"></a>IHttpCookieContainerManager

Cette interface, exposée par <xref:System.ServiceModel.Channels.IChannelFactory%601>, facilite l'utilisation des cookies côté client. Lorsque AllowCookies a la valeur True sur la liaison, accédez aux cookies à l’aide du code suivant :

```csharp
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();
System.Net.CookieContainer container = cookieManager.CookieContainer;
```

Vous pouvez ensuite récupérer ou définir les cookies à partir de <xref:System.Net.CookieContainer>. Lorsque AllowCookies a la valeur False, vous pouvez extraire manuellement les cookies à l'aide de <xref:System.ServiceModel.OperationContext> et les envoyer dans d'autres requêtes à l'aide d'un autre <xref:System.ServiceModel.OperationContext> ou d'un inspecteur de message. L'interface IHttpCookieContainerManager vous permet d'authentifier un utilisateur avec un service et d'utiliser le cookie d'authentification retourné par ce service pour l'authentifier auprès d'autres services.

---
title: "Vue d'ensemble de l'architecture de métadonnées"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metadata [WCF], overview
ms.assetid: 1d37645e-086d-4d68-a358-f3c5b6e8205e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8890cc05ec6b0b889dafcb787e216b50a681876
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="metadata-architecture-overview"></a>Vue d'ensemble de l'architecture de métadonnées
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] fournit une infrastructure riche pour exporter, publier, récupérer et importer les métadonnées de service. Les services [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilisent les métadonnées pour décrire l'interaction avec les points de terminaison d'un service afin que les outils tels que Svcutil.exe puissent générer automatiquement le code client pour accéder au service.  
  
 La plupart des types qui composent l'infrastructure des métadonnées [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] réside dans l'espace de noms <xref:System.ServiceModel.Description>.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilise la classe <xref:System.ServiceModel.Description.ServiceEndpoint> pour décrire des points de terminaison dans un service. Vous pouvez utiliser [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pour générer les métadonnées pour les points de terminaison de service ou importer les métadonnées de service pour générer des instances <xref:System.ServiceModel.Description.ServiceEndpoint>.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] représente les métadonnées pour un service sous la forme d'une instance du type <xref:System.ServiceModel.Description.MetadataSet> dont la structure est fortement liée au format de la sérialisation des métadonnées définies dans WS-MetadataExchange. Le type <xref:System.ServiceModel.Description.MetadataSet> regroupe les métadonnées de service réelles, telles que les documents WSDL (Web Services Description Language), les documents de schéma XML ou les expressions WS-Policy, sous la forme d'une collection d'instances <xref:System.ServiceModel.Description.MetadataSection>. Chaque instance <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> contient un dialecte de métadonnées spécifique et un identificateur. Un <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> peut contenir les éléments suivants dans sa propriété <xref:System.ServiceModel.Description.MetadataSection.Metadata%2A?displayProperty=nameWithType> :  
  
-   Métadonnées brutes.  
  
-   Instance de <xref:System.ServiceModel.Description.MetadataReference>.  
  
-   Instance de <xref:System.ServiceModel.Description.MetadataLocation>.  
  
 Les instances <xref:System.ServiceModel.Description.MetadataReference?displayProperty=nameWithType> pointent vers un autre point de terminaison d'échanges de métadonnées (MEX) et les instances <xref:System.ServiceModel.Description.MetadataLocation?displayProperty=nameWithType> pointent vers un document de métadonnées à l'aide d'une URL HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] prend en charge l'utilisation de documents WSDL pour décrire des points de terminaison de service, des contrats de service, des liaisons, des modèles d'échange de messages, des messages et des messages d'erreur implémentés par un service. Les types de données utilisés par le service sont décrits dans les documents WSDL à l'aide du schéma XML. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Importation de schéma et d’exportation](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md). Vous pouvez utiliser [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pour exporter et importer des extensions WSDL pour le comportement de service, les comportements de contrat et les éléments de liaison qui étendent les fonctionnalités d'un service. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Exportation de métadonnées personnalisées pour une Extension WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-service-metadata"></a>Exportation des métadonnées de service  
 Dans [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], *exportation de métadonnées* consiste à décrire des points de terminaison de service et à les projeter dans une représentation parallèle standardisée qui les clients peuvent utiliser pour apprendre à utiliser le service. Pour exporter des métadonnées à partir des instances <xref:System.ServiceModel.Description.ServiceEndpoint>, utilisez une implémentation de la classe abstraite <xref:System.ServiceModel.Description.MetadataExporter>. Une implémentation <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> génère des métadonnées encapsulée dans une instance <xref:System.ServiceModel.Description.MetadataSet>.  
  
 La classe <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> fournit une infrastructure pour générer des expressions de stratégie qui décrivent les fonctions et les spécifications d'une liaison de point de terminaison et ses opérations, messages et erreurs associés. Ces expressions de stratégie sont capturées dans une instance <xref:System.ServiceModel.Description.PolicyConversionContext>. Une implémentation <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> peut ensuite attacher ces expressions de stratégie aux métadonnées qu'elle génère.  
  
 <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> appelle chaque <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> qui implémente l'interface <xref:System.ServiceModel.Description.IPolicyExportExtension> dans la liaison d'un <xref:System.ServiceModel.Description.ServiceEndpoint> lors de la génération d'un objet <xref:System.ServiceModel.Description.PolicyConversionContext> devant être utilisé par l'implémentation <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>. Vous pouvez exporter de nouvelles assertions de stratégie en implémentant l'interface <xref:System.ServiceModel.Description.IPolicyExportExtension> sur vos implémentations personnalisées du type <xref:System.ServiceModel.Channels.BindingElement>.  
  
 Le type <xref:System.ServiceModel.Description.WsdlExporter> est l'implémentation de la classe abstraite <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> fournie avec [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Le type <xref:System.ServiceModel.Description.WsdlExporter> génère les métadonnées WSDL avec les expressions de stratégie jointes.  
  
 Pour exporter des métadonnées WSDL ou des extensions WSDL personnalisées pour les comportements de point de terminaison, les comportements de contrat ou les éléments de liaison dans un point de terminaison de service, vous pouvez implémenter l'interface <xref:System.ServiceModel.Description.IWsdlExportExtension>. Le <xref:System.ServiceModel.Description.WsdlExporter> recherche dans une instance <xref:System.ServiceModel.Description.ServiceEndpoint> des éléments de liaison, des comportements d'opération, des comportements de contrat et des comportements de point de terminaison qui implémentent l'interface <xref:System.ServiceModel.Description.IWsdlExportExtension> lors de la génération du document WSDL.  
  
## <a name="publishing-service-metadata"></a>Publication des métadonnées de service  
 Les services [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] publient les métadonnées en exposant un ou plusieurs points de terminaison de métadonnées. La publication des métadonnées de service rend les métadonnées de service disponibles à l'aide de protocoles standardisés, tels que les demandes MEX et HTTP/GET. Les points de terminaison de métadonnées sont semblables à d'autres points de terminaison de service en ce sens qu'ils ont une adresse, une liaison et un contrat. Vous pouvez ajouter des points de terminaison de métadonnées à un hôte de service dans la configuration ou dans le code.  
  
 Pour publier des points de terminaison de métadonnées pour un service [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vous devez d'abord ajouter une instance du comportement de service <xref:System.ServiceModel.Description.ServiceMetadataBehavior> au service. L'ajout d'une instance <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> à votre service augmente votre service en rendant possible la publication des métadonnées en exposant un ou plusieurs points de terminaison de métadonnées. Après avoir ajouté le comportement de service <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, vous pouvez ensuite exposer les points de terminaison de métadonnées qui prennent en charge le protocole MEX ou les points de terminaison de métadonnées qui répondent aux demandes HTTP/GET.  
  
 Pour ajouter des points de terminaison de métadonnées qui utilisent le protocole MEX, ajoutez des points de terminaison de service à votre hôte de service qui utilisent le contrat de service nommé IMetadataExchange.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] définit le <xref:System.ServiceModel.Description.IMetadataExchange> interface portant ce nom de contrat de service. Les points de terminaison WS-MetadataExchange (ou points de terminaison MEX) peuvent utiliser l'une des quatre liaisons par défaut que les méthodes de fabrique statiques exposent sur la classe <xref:System.ServiceModel.Description.MetadataExchangeBindings> afin d'établir une correspondance avec les liaisons par défaut utilisées par les outils [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tels que Svcutil.exe. Vous pouvez également configurer des points de terminaison de métadonnées MEX à l’aide d’une liaison personnalisée.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> utilise <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType> pour exporter les métadonnées de tous les points de terminaison de service de votre service. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]exportation de métadonnées à partir d’un service, consultez [exportation et importation de métadonnées](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 Le <xref:System.ServiceModel.Description.ServiceMetadataBehavior> augmente votre hôte de service en ajoutant une instance <xref:System.ServiceModel.Description.ServiceMetadataExtension> sous la forme d'une extension à votre hôte de service. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> fournit l'implémentation pour les protocoles de publication de métadonnées. Vous pouvez également utiliser <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> pour obtenir les métadonnées de service au moment de l'exécution en accédant à la propriété <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A>.  
  
> [!CAUTION]
>  Si vous ajoutez un point de terminaison MEX dans votre fichier de configuration de l'application, puis tentez d'ajouter <xref:System.ServiceModel.Description.ServiceMetadataBehavior> à votre hôte de service dans le code, vous obtenez l'exception suivante :  
>   
>  System.InvalidOperationException : Nom de contrat « IMetadataExchange » introuvable dans la liste des contrats implémentés par le service Service1. Ajoutez un ServiceMetadataBehavior au fichier de configuration ou directement à ServiceHost pour activer la prise en charge de ce contrat.  
>   
>  Vous pouvez remédier à ce problème en ajoutant <xref:System.ServiceModel.Description.ServiceMetadataBehavior> dans le fichier de configuration, ou en ajoutant à la fois le point de terminaison et <xref:System.ServiceModel.Description.ServiceMetadataBehavior> dans le code.  
>   
>  Pour obtenir un exemple d’ajout de <xref:System.ServiceModel.Description.ServiceMetadataBehavior> dans un fichier de configuration d’application, consultez la [mise en route](../../../../docs/framework/wcf/samples/getting-started-sample.md). Pour obtenir un exemple d’ajout de <xref:System.ServiceModel.Description.ServiceMetadataBehavior> dans le code, consultez la [auto-hébergement](../../../../docs/framework/wcf/samples/self-host.md) exemple.  
  
> [!CAUTION]
>  Lors de la publication de métadonnées pour un service qui expose deux contrats de service différents où chacun contient une opération du même nom, une exception est levée. Par exemple, si vous disposez d'un service qui expose un contrat de service appelé ICarService comportant une opération Get(Voiture c) et que le même service expose un contrat de service appelé IBookService comportant une opération Get(Livre b), une exception est levée ou un message d'erreur est affiché lors de la génération des métadonnées du service. Pour remédier à ce problème, effectuez l'une des opérations suivantes :  
>   
>  -   Renommez l'une des opérations.  
> -   Affectez au <xref:System.ServiceModel.OperationContractAttribute.Name%2A> un nom différent.  
> -   Affectez à l'un des espaces de noms des opérations un espace de noms différent à l'aide de la propriété <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
## <a name="retrieving-service-metadata"></a>Récupération des métadonnées de service  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] récupère des métadonnées de service à l'aide des protocoles standardisés tels que WS-MetadataExchange et les requêtes HTTP. Ces deux protocoles sont pris en charge par le type <xref:System.ServiceModel.Description.MetadataExchangeClient>. Vous récupérez les métadonnées de service à l'aide du type <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> en fournissant une adresse et une liaison facultative. La liaison utilisée par une instance <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> peut être l'une des liaisons par défaut de la classe statique <xref:System.ServiceModel.Description.MetadataExchangeBindings>, une liaison fournie par l'utilisateur ou une liaison chargée à partir d'une configuration de point de terminaison pour le contrat `IMetadataExchange`. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> peut également résoudre des références d'URL HTTP aux métadonnées à l'aide du type <xref:System.Net.HttpWebRequest>.  
  
 Par défaut, une instance <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> est attachée à une instance <xref:System.ServiceModel.Channels.ChannelFactoryBase> unique. Vous pouvez modifier ou remplacer l'instance <xref:System.ServiceModel.Channels.ChannelFactoryBase> utilisée par <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> en substituant la méthode virtuelle <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>. De la même façon, vous pouvez modifier ou remplacer l'instance <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> utilisée par <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> pour effectuer des requêtes HTTP/GET en substituant la méthode virtuelle <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>.  
  
 Vous pouvez récupérer les métadonnées de service à l’aide de demandes WS-MetadataExchange ou HTTP/GET à l’aide de l’outil Svcutil.exe et en passant le **/target:metadata** commutateur et une adresse. Svcutil.exe télécharge les métadonnées à l'adresse spécifiée et enregistre les fichiers sur disque. Svcutil.exe utilise une instance <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> en interne et charge, à partir du fichier de configuration de l'application, une configuration de point de terminaison MEX dont le nom correspond au schéma de l'adresse passée à Svcutil.exe, s'il en existe une. Sinon, Svcutil.exe utilise par défaut une des liaisons définies par le type de fabrique statique <xref:System.ServiceModel.Description.MetadataExchangeBindings>.  
  
## <a name="importing-service-metadata"></a>Importation des métadonnées de service  
 Dans [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], l'importation de métadonnées est le processus de génération d'une représentation abstraite d'un service ou de ses composants à partir de ses métadonnées. Par exemple, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] peut importer des instances <xref:System.ServiceModel.Description.ServiceEndpoint>, des instances <xref:System.ServiceModel.Channels.Binding> ou des instances <xref:System.ServiceModel.Description.ContractDescription> à partir d'un document WSDL pour un service. Pour importer des métadonnées de service dans [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilisez une implémentation de la classe abstraite <xref:System.ServiceModel.Description.MetadataImporter>. Les types qui dérivent de la classe <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> implémentent la prise en charge de l'importation des formats de métadonnées qui tirent parti de la logique d'importation WS-Policy dans [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Une implémentation <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> recueille les expressions de stratégie attachées aux métadonnées de service dans un objet <xref:System.ServiceModel.Description.PolicyConversionContext>. Le <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> traite ensuite les stratégies dans le cadre de l'importation des métadonnées en appelant les implémentations de l'interface <xref:System.ServiceModel.Description.IPolicyImportExtension> dans la propriété <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>.  
  
 Vous pouvez ajouter la prise en charge pour importer de nouvelles assertions de stratégie vers un <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> en ajoutant votre propre implémentation de l'interface <xref:System.ServiceModel.Description.IPolicyImportExtension> à la collection <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> sur une instance <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType>. Vous pouvez également enregistrer votre extension de l'importation de la stratégie dans votre fichier de configuration de l'application cliente.  
  
 Le type <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> est l'implémentation de la classe abstraite <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> fournie avec [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Le type <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> importe des métadonnées WSDL avec les stratégies attachées fournies dans un objet <xref:System.ServiceModel.Description.MetadataSet>.  
  
 Vous pouvez ajouter la prise en charge pour importer des extensions WSDL en implémentant l'interface <xref:System.ServiceModel.Description.IWsdlImportExtension> et en ajoutant ensuite votre implémentation à la propriété <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A> sur votre instance <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>. Le <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> peut également charger des implémentations de l'interface <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> inscrite dans votre fichier de configuration de l'application cliente.  
  
## <a name="dynamic-bindings"></a>Liaisons dynamiques  
 Vous pouvez mettre à jour dynamiquement la liaison que vous utilisez pour créer un canal vers un point de terminaison de service au cas où la liaison pour le point de terminaison change ou si vous souhaitez créer un canal vers un point de terminaison qui utilise le même contrat mais possède une liaison différente. Vous pouvez utiliser la classe statique <xref:System.ServiceModel.Description.MetadataResolver> pour récupérer et importer les métadonnées au moment de l'exécution pour les points de terminaison de service qui implémentent un contrat spécifique. Vous pouvez utiliser ensuite les objets <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> importés pour créer une fabrique de client ou de canaux au point de terminaison souhaité.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.ServiceModel.Description>  
 [Formats de métadonnées](../../../../docs/framework/wcf/feature-details/metadata-formats.md)  
 [Exportation et importation de métadonnées](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)  
 [Publication de métadonnées](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)  
 [Récupération de métadonnées](../../../../docs/framework/wcf/feature-details/retrieving-metadata.md)  
 [Utilisation des métadonnées](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [Considérations sur la sécurité des métadonnées](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)  
 [Extension du système de métadonnées](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)

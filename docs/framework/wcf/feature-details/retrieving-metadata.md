---
title: Récupération de métadonnées
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], retrieving
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
ms.openlocfilehash: bb415d88c2bae75cb16aa137bdf867eb463afa63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152397"
---
# <a name="retrieving-metadata"></a>Récupération de métadonnées
Le processus de récupération de métadonnées consiste à demander et à récupérer les métadonnées d'un point de terminaison de métadonnées, tel que WS-MetadataExchange (MEX) ou HTTP/GET.  
  
## <a name="retrieving-metadata-from-the-command-line-using-svcutilexe"></a>Récupération de métadonnées à partir de la ligne de commande à l'aide de Svcutil.exe  
 Vous pouvez récupérer les métadonnées de service à l’aide de requêtes WS-MetadataExchange ou HTTP/GET à l’aide de la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) outil et en passant le `/target:metadata` commutateur et une adresse. Svcutil.exe télécharge les métadonnées à l'adresse spécifiée et enregistre le fichier sur disque. Svcutil.exe utilise une instance <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> en interne et charge, à partir de la configuration, la configuration de point de terminaison <xref:System.ServiceModel.Description.IMetadataExchange> dont le nom correspond au schéma de l'adresse passée à Svcutil.exe en tant qu'entrée.  
  
## <a name="retrieving-metadata-programmatically-using-the-metadataexchangeclient"></a>Récupération de métadonnées par programme à l'aide de MetadataExchangeClient  
 Windows Communication Foundation (WCF) peut récupérer les métadonnées de service à l’aide de protocoles standardisés tels que WS-MetadataExchange et les requêtes HTTP/GET. Ces deux protocoles sont pris en charge par le type <xref:System.ServiceModel.Description.MetadataExchangeClient>. Vous récupérez les métadonnées de service à l’aide du type <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> en fournissant une adresse au point de terminaison de métadonnées et une liaison facultative. La liaison utilisée par une instance <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> peut être l'une des liaisons par défaut de la classe statique <xref:System.ServiceModel.Description.MetadataExchangeBindings>, une liaison fournie par l'utilisateur ou une liaison chargée à partir d'une configuration de point de terminaison pour le contrat `IMetadataExchange`. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> peut également résoudre des références d'URL HTTP aux métadonnées à l'aide du type <xref:System.Net.HttpWebRequest>.  
  
 Par défaut, une instance <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> est attachée à une instance <xref:System.ServiceModel.ChannelFactory> unique. Vous pouvez modifier ou remplacer l'instance <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> utilisée par <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> en substituant la méthode virtuelle <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>. De la même façon, vous pouvez modifier ou remplacer l'instance <xref:System.Net.HttpWebRequest> utilisée par <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> pour effectuer des requêtes HTTP/GET en substituant la méthode virtuelle <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Procédure : utiliser Svcutil.exe pour télécharger des documents de métadonnées](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Indique comment utiliser Svcutil.exe pour télécharger des documents de métadonnées.  
  
 [Procédure : utiliser MetadataResolver pour obtenir des métadonnées de liaison de manière dynamique](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Indique comment utiliser <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> pour obtenir dynamiquement des métadonnées de liaison pendant l'exécution.  
  
 [Procédure : utiliser MetadataExchangeClient pour récupérer des métadonnées](../../../../docs/framework/wcf/feature-details/how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Indique comment utiliser la classe <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> pour télécharger des fichiers de métadonnées dans un objet <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType> qui contient des objets <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> à écrire dans des fichiers ou destinés à d'autres fins.  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.ServiceModel.Description.MetadataExchangeClient>

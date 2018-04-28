---
title: 'Comment : importer des métadonnées dans des points de terminaison de service'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b86f31217812767b0fbbd785a0f3ff96c2948854
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-import-metadata-into-service-endpoints"></a><span data-ttu-id="a251b-102">Comment : importer des métadonnées dans des points de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="a251b-102">How to: Import Metadata into Service Endpoints</span></span>
<span data-ttu-id="a251b-103">Cette rubrique explique comment importer des métadonnées dans une collection de points de terminaison de service et d’utiliser le service défini dans le [mise en route](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="a251b-103">This topic explains how to import metadata into a collection of service endpoints and use the service defined in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="a251b-104">Cette rubrique montre comment créer une application cliente qui importe les métadonnées à partir du service, puis appelle la méthode `Add` sur le service.</span><span class="sxs-lookup"><span data-stu-id="a251b-104">This topic show how to create a client application that imports metadata from the service and then calls the `Add` method on the service.</span></span>  
  
### <a name="to-import-metadata-into-service-endpoints"></a><span data-ttu-id="a251b-105">Pour importer des métadonnées dans des points de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="a251b-105">To import metadata into service endpoints</span></span>  
  
1.  <span data-ttu-id="a251b-106">Déclarez un objet <xref:System.ServiceModel.EndpointAddress> et initialisez-le avec l'URI (Uniform Resource Identifier) de l'adresse d'échange de métadonnées (MEX) du service.</span><span class="sxs-lookup"><span data-stu-id="a251b-106">Declare an <xref:System.ServiceModel.EndpointAddress> object and initialize it with the Uniform Resource Identifier (URI) for the metadata exchange (MEX) address of the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2.  <span data-ttu-id="a251b-107">Créez un <xref:System.ServiceModel.Description.MetadataExchangeClient> en passant l'adresse MEX, puis appelez <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="a251b-107">Create a <xref:System.ServiceModel.Description.MetadataExchangeClient>, passing in the MEX address, and call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span></span> <span data-ttu-id="a251b-108">Cette opération récupère les métadonnées du service.</span><span class="sxs-lookup"><span data-stu-id="a251b-108">This retrieves the metadata from the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3.  <span data-ttu-id="a251b-109">Créez un <xref:System.ServiceModel.Description.WsdlImporter> en passant les métadonnées précédemment récupérées, puis appelez <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span><span class="sxs-lookup"><span data-stu-id="a251b-109">Create a <xref:System.ServiceModel.Description.WsdlImporter>, passing in the metadata previously retrieved, and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span></span> <span data-ttu-id="a251b-110">Cette opération génère une collection d'objets <xref:System.ServiceModel.Description.ContractDescription>.</span><span class="sxs-lookup"><span data-stu-id="a251b-110">This generates a collection of <xref:System.ServiceModel.Description.ContractDescription> objects.</span></span> <span data-ttu-id="a251b-111">Vous pouvez aussi appeler <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> ou <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a251b-111">You could also call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> or <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, depending upon your needs.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    >  <span data-ttu-id="a251b-112">Après avoir importé les métadonnées, vous ne pourrez pas créer un canal client ou exporter les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="a251b-112">After you have imported the metadata, you will not be able to create a client channel or export the metadata.</span></span> <span data-ttu-id="a251b-113">En effet, aucune information de type n'est disponible à ce stade.</span><span class="sxs-lookup"><span data-stu-id="a251b-113">This is because no type information is available at this point.</span></span> <span data-ttu-id="a251b-114">Les informations de type sont requises pour interagir concrètement avec le service ou exporter les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="a251b-114">Type information is required to actually interact with the service or export metadata.</span></span> <span data-ttu-id="a251b-115">Pour générer les informations de type, vous devez générer le code (comme indiqué aux étapes 4 et 5).</span><span class="sxs-lookup"><span data-stu-id="a251b-115">To generate the type information, you need to generate code, shown in steps 4 and 5.</span></span> <span data-ttu-id="a251b-116">Vous pouvez également utiliser la classe d'assistance <xref:System.ServiceModel.Description.MetadataResolver>.</span><span class="sxs-lookup"><span data-stu-id="a251b-116">Alternatively, you could use the <xref:System.ServiceModel.Description.MetadataResolver> helper class.</span></span> <span data-ttu-id="a251b-117">Pour plus d’informations, consultez [Comment : utiliser des MetadataResolver pour obtenir les métadonnées de liaison dynamique](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="a251b-117">For more information, see [How to: Use MetadataResolver to Obtain Binding Metadata Dynamically](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span></span>  
  
4.  <span data-ttu-id="a251b-118">Générez des informations de type pour chaque contrat.</span><span class="sxs-lookup"><span data-stu-id="a251b-118">Generate type information for each contract.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5.  <span data-ttu-id="a251b-119">Vous pouvez désormais utiliser ces informations.</span><span class="sxs-lookup"><span data-stu-id="a251b-119">Now you can use this information.</span></span> <span data-ttu-id="a251b-120">L'exemple suivant génère un code source C#.</span><span class="sxs-lookup"><span data-stu-id="a251b-120">The following sample generates C# source code.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="a251b-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a251b-121">See Also</span></span>  
 [<span data-ttu-id="a251b-122">Métadonnées</span><span class="sxs-lookup"><span data-stu-id="a251b-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="a251b-123">Prise en main</span><span class="sxs-lookup"><span data-stu-id="a251b-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)

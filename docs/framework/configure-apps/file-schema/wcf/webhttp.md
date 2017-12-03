---
title: '&lt;webHttp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b5388a680816bca6051525f5130308a3c7c2dc5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2017
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="2bca1-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="2bca1-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="2bca1-103">Cet élément spécifie le <xref:System.ServiceModel.Description.WebHttpBehavior> d'un point de terminaison via la configuration.</span><span class="sxs-lookup"><span data-stu-id="2bca1-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="2bca1-104">Ce comportement est utilisé conjointement avec la [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) permet à une liaison standard, le modèle de programmation Web pour un [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span><span class="sxs-lookup"><span data-stu-id="2bca1-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>  
  
 <span data-ttu-id="2bca1-105">\<système. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2bca1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2bca1-106">\<comportements ></span><span class="sxs-lookup"><span data-stu-id="2bca1-106">\<behaviors></span></span>  
<span data-ttu-id="2bca1-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2bca1-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="2bca1-108">\<comportement ></span><span class="sxs-lookup"><span data-stu-id="2bca1-108">\<behavior></span></span>  
<span data-ttu-id="2bca1-109">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="2bca1-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bca1-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2bca1-110">Syntax</span></span>  
  
```xml  
<webHttp />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2bca1-111">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="2bca1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2bca1-112">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="2bca1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2bca1-113">Attributs</span><span class="sxs-lookup"><span data-stu-id="2bca1-113">Attributes</span></span>  
  
|<span data-ttu-id="2bca1-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="2bca1-114">Attribute</span></span>|<span data-ttu-id="2bca1-115">Description</span><span class="sxs-lookup"><span data-stu-id="2bca1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2bca1-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="2bca1-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="2bca1-117">Lorsque cette propriété a la valeur `true`, l'infrastructure WCF détermine le meilleur format à utiliser.</span><span class="sxs-lookup"><span data-stu-id="2bca1-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="2bca1-118">La sélection automatique du format est désactivée par défaut à des fins de compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="2bca1-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="2bca1-119">La sélection automatique du format peut être activée par programme ou par configuration.</span><span class="sxs-lookup"><span data-stu-id="2bca1-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="2bca1-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="2bca1-120">defaultBodyStyle</span></span>|<span data-ttu-id="2bca1-121">Spécifie le style du corps par défaut des messages retournés.</span><span class="sxs-lookup"><span data-stu-id="2bca1-121">Specifies the default body style of returned messages.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="2bca1-122"><xref:System.ServiceModel.Web.WebMessageBodyStyle> et [mise en forme de HTTP Web WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2bca1-122"> <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="2bca1-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="2bca1-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="2bca1-124">Spécifie le format de réponse sortante par défaut des messages.</span><span class="sxs-lookup"><span data-stu-id="2bca1-124">Specifies the default outgoing response format for messages.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="2bca1-125">[Mise en forme de HTTP Web WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="2bca1-125"> [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="2bca1-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="2bca1-126">faultExceptionEnabled</span></span>|<span data-ttu-id="2bca1-127">Obtient ou définit l'indicateur qui spécifie si FaultException est généré lorsqu'une erreur de serveur interne (code d'état HTTP: 500) se produit.</span><span class="sxs-lookup"><span data-stu-id="2bca1-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="2bca1-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="2bca1-128">helpEnabled</span></span>|<span data-ttu-id="2bca1-129">Obtient ou définit une valeur qui détermine si la page d'aide est activée.</span><span class="sxs-lookup"><span data-stu-id="2bca1-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2bca1-130">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="2bca1-130">Child Elements</span></span>  
 <span data-ttu-id="2bca1-131">Aucun.</span><span class="sxs-lookup"><span data-stu-id="2bca1-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2bca1-132">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="2bca1-132">Parent Elements</span></span>  
  
|<span data-ttu-id="2bca1-133">Élément</span><span class="sxs-lookup"><span data-stu-id="2bca1-133">Element</span></span>|<span data-ttu-id="2bca1-134">Description</span><span class="sxs-lookup"><span data-stu-id="2bca1-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2bca1-135">\<comportement ></span><span class="sxs-lookup"><span data-stu-id="2bca1-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2bca1-136">Spécifie le jeu de comportements du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2bca1-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2bca1-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2bca1-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="2bca1-138">Intégration d’AJAX et prise en charge JSON</span><span class="sxs-lookup"><span data-stu-id="2bca1-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="2bca1-139">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="2bca1-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)

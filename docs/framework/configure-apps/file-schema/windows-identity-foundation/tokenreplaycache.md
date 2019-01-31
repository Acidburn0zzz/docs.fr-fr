---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: dfa6c0d84582d55595f00f149adfdcaa9d554d6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271948"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="ac9f5-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="ac9f5-101">\<tokenReplayCache></span></span>
<span data-ttu-id="ac9f5-102">Inscrit un cache de relecture de jetons avec un service ou une collection de gestionnaires de jetons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ac9f5-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="ac9f5-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ac9f5-103">\<system.identityModel></span></span>  
<span data-ttu-id="ac9f5-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ac9f5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ac9f5-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="ac9f5-105">\<caches></span></span>  
<span data-ttu-id="ac9f5-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="ac9f5-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9f5-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ac9f5-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac9f5-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="ac9f5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ac9f5-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="ac9f5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac9f5-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="ac9f5-110">Attributes</span></span>  
  
|<span data-ttu-id="ac9f5-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ac9f5-111">Attribute</span></span>|<span data-ttu-id="ac9f5-112">Description</span><span class="sxs-lookup"><span data-stu-id="ac9f5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac9f5-113">type</span><span class="sxs-lookup"><span data-stu-id="ac9f5-113">type</span></span>|<span data-ttu-id="ac9f5-114">Un type qui dérive de la <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="ac9f5-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="ac9f5-115">Pour plus d’informations sur la façon de spécifier une personnalisée `type`, consultez [références de Type personnalisé].</span><span class="sxs-lookup"><span data-stu-id="ac9f5-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ac9f5-116">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="ac9f5-116">Child Elements</span></span>  
 <span data-ttu-id="ac9f5-117">Aucun.</span><span class="sxs-lookup"><span data-stu-id="ac9f5-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac9f5-118">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="ac9f5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ac9f5-119">Élément</span><span class="sxs-lookup"><span data-stu-id="ac9f5-119">Element</span></span>|<span data-ttu-id="ac9f5-120">Description</span><span class="sxs-lookup"><span data-stu-id="ac9f5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac9f5-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="ac9f5-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="ac9f5-122">Inscrit le met en cache utilisé par un service ou une collection de gestionnaires de jetons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ac9f5-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac9f5-123">Notes</span><span class="sxs-lookup"><span data-stu-id="ac9f5-123">Remarks</span></span>  
 <span data-ttu-id="ac9f5-124">Le cache de relecture de jetons est utilisé pour détecter les jetons relus.</span><span class="sxs-lookup"><span data-stu-id="ac9f5-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="ac9f5-125">Détection de relecture de jetons est activée par le [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) élément, qui spécifie également l’heure d’expiration maximal pour les jetons.</span><span class="sxs-lookup"><span data-stu-id="ac9f5-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac9f5-126">Exemple</span><span class="sxs-lookup"><span data-stu-id="ac9f5-126">Example</span></span>  
 <span data-ttu-id="ac9f5-127">Le code XML suivant illustre la configuration d’un cache personnalisé pour détecter les jetons relus.</span><span class="sxs-lookup"><span data-stu-id="ac9f5-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac9f5-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac9f5-128">See also</span></span>
- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="ac9f5-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="ac9f5-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)

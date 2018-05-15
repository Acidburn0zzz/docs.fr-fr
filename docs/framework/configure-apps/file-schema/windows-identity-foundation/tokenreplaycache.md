---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 79022319944c4042c6f62a7521784b826b90d4ce
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="3f322-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="3f322-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="3f322-103">Inscrit un cache de relecture de jetons avec un service ou d’une collection de gestionnaire de jetons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="3f322-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="3f322-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3f322-104">\<system.identityModel></span></span>  
<span data-ttu-id="3f322-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3f322-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3f322-106">\<met en cache ></span><span class="sxs-lookup"><span data-stu-id="3f322-106">\<caches></span></span>  
<span data-ttu-id="3f322-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="3f322-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f322-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3f322-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f322-109">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="3f322-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3f322-110">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="3f322-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f322-111">Attributs</span><span class="sxs-lookup"><span data-stu-id="3f322-111">Attributes</span></span>  
  
|<span data-ttu-id="3f322-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="3f322-112">Attribute</span></span>|<span data-ttu-id="3f322-113">Description</span><span class="sxs-lookup"><span data-stu-id="3f322-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f322-114">type</span><span class="sxs-lookup"><span data-stu-id="3f322-114">type</span></span>|<span data-ttu-id="3f322-115">Un type qui dérive de la <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="3f322-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="3f322-116">Pour plus d’informations sur la façon de spécifier une personnalisée `type`, voir [références de Type personnalisé].</span><span class="sxs-lookup"><span data-stu-id="3f322-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="3f322-117">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="3f322-117">Child Elements</span></span>  
 <span data-ttu-id="3f322-118">Aucun</span><span class="sxs-lookup"><span data-stu-id="3f322-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f322-119">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="3f322-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3f322-120">Élément</span><span class="sxs-lookup"><span data-stu-id="3f322-120">Element</span></span>|<span data-ttu-id="3f322-121">Description</span><span class="sxs-lookup"><span data-stu-id="3f322-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f322-122">\<met en cache ></span><span class="sxs-lookup"><span data-stu-id="3f322-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="3f322-123">Inscrit le met en cache utilisé par un service ou une collection de gestionnaire de jetons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="3f322-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f322-124">Notes</span><span class="sxs-lookup"><span data-stu-id="3f322-124">Remarks</span></span>  
 <span data-ttu-id="3f322-125">Le cache de relecture de jetons est utilisé pour détecter les jetons relus.</span><span class="sxs-lookup"><span data-stu-id="3f322-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="3f322-126">Détection de relecture de jetons est activée par le [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) élément, qui spécifie également l’heure d’expiration maximal pour les jetons.</span><span class="sxs-lookup"><span data-stu-id="3f322-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f322-127">Exemple</span><span class="sxs-lookup"><span data-stu-id="3f322-127">Example</span></span>  
 <span data-ttu-id="3f322-128">Le code XML suivant illustre la configuration d’un cache personnalisé pour la détection des jetons relus.</span><span class="sxs-lookup"><span data-stu-id="3f322-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f322-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f322-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="3f322-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="3f322-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)

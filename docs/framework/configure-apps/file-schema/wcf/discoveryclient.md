---
title: '&lt;DiscoveryClient&gt;'
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 9aef599ebf8068a383fd093b126a6bde1670b291
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151395"
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="1fe23-102">&lt;DiscoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="1fe23-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="1fe23-103">Élément de configuration qui crée une liaison personnalisée permettant à une application cliente de rechercher automatiquement un service détectable et de trouver son adresse au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="1fe23-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="1fe23-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1fe23-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1fe23-105">\<liaisons ></span><span class="sxs-lookup"><span data-stu-id="1fe23-105">\<bindings></span></span>  
<span data-ttu-id="1fe23-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1fe23-106">\<customBinding></span></span>  
<span data-ttu-id="1fe23-107">\<liaison ></span><span class="sxs-lookup"><span data-stu-id="1fe23-107">\<binding></span></span>  
<span data-ttu-id="1fe23-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="1fe23-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fe23-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1fe23-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fe23-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="1fe23-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1fe23-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="1fe23-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fe23-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="1fe23-112">Attributes</span></span>  
  
|<span data-ttu-id="1fe23-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="1fe23-113">Attribute</span></span>|<span data-ttu-id="1fe23-114">Description</span><span class="sxs-lookup"><span data-stu-id="1fe23-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1fe23-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="1fe23-115">discoveryEndpoint</span></span>|<span data-ttu-id="1fe23-116">Chaîne qui contient le nom du point de terminaison de découverte permettant à une application cliente de rechercher automatiquement un service détectable et de trouver son adresse au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="1fe23-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fe23-117">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="1fe23-117">Child Elements</span></span>  
  
|<span data-ttu-id="1fe23-118">Élément</span><span class="sxs-lookup"><span data-stu-id="1fe23-118">Element</span></span>|<span data-ttu-id="1fe23-119">Description</span><span class="sxs-lookup"><span data-stu-id="1fe23-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fe23-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="1fe23-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="1fe23-121">Élément de configuration qui fournit un jeu de critères utilisé par une application cliente pour rechercher un service de découverte.</span><span class="sxs-lookup"><span data-stu-id="1fe23-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="1fe23-122">Critères peuvent être regroupées en critères de recherche (spécifiant les services que vous recherchez) et recherchez les critères d’arrêt (la durée pendant laquelle la recherche doit durer).</span><span class="sxs-lookup"><span data-stu-id="1fe23-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fe23-123">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="1fe23-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1fe23-124">Élément</span><span class="sxs-lookup"><span data-stu-id="1fe23-124">Element</span></span>|<span data-ttu-id="1fe23-125">Description</span><span class="sxs-lookup"><span data-stu-id="1fe23-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fe23-126">\<liaison ></span><span class="sxs-lookup"><span data-stu-id="1fe23-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1fe23-127">Définit toutes les fonctions de liaison d’une liaison personnalisée.</span><span class="sxs-lookup"><span data-stu-id="1fe23-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fe23-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fe23-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>

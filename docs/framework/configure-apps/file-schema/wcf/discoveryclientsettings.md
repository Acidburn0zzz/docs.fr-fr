---
title: '&lt;discoveryClientSettings&gt;'
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: e9723aed1aa8fbcbf5c4e84080c0ba991ea3fd60
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746005"
---
# <a name="ltdiscoveryclientsettingsgt"></a><span data-ttu-id="e92ac-102">&lt;discoveryClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="e92ac-102">&lt;discoveryClientSettings&gt;</span></span>
<span data-ttu-id="e92ac-103">Contient les paramètres requis par une application pour participer au processus de découverte de service en tant que client.</span><span class="sxs-lookup"><span data-stu-id="e92ac-103">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="e92ac-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e92ac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e92ac-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e92ac-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e92ac-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e92ac-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" 
                        maxResults="Integer" 
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e92ac-107">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="e92ac-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e92ac-108">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="e92ac-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e92ac-109">Attributs</span><span class="sxs-lookup"><span data-stu-id="e92ac-109">Attributes</span></span>  
  
|<span data-ttu-id="e92ac-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="e92ac-110">Attribute</span></span>|<span data-ttu-id="e92ac-111">Description</span><span class="sxs-lookup"><span data-stu-id="e92ac-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e92ac-112">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="e92ac-112">discoveryEndpoint</span></span>|<span data-ttu-id="e92ac-113">Chaîne qui contient le nom du point de terminaison de découverte permettant à une application cliente de rechercher automatiquement un service détectable et de trouver son adresse au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e92ac-113">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e92ac-114">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="e92ac-114">Child Elements</span></span>  
  
|<span data-ttu-id="e92ac-115">Élément</span><span class="sxs-lookup"><span data-stu-id="e92ac-115">Element</span></span>|<span data-ttu-id="e92ac-116">Description</span><span class="sxs-lookup"><span data-stu-id="e92ac-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e92ac-117">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e92ac-117">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e92ac-118">Élément de configuration qui fournit un jeu de critères utilisé par une application cliente pour rechercher un service de découverte.</span><span class="sxs-lookup"><span data-stu-id="e92ac-118">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="e92ac-119">Critères peuvent être regroupés en critères de recherche (spécifiant les services que vous recherchez) et recherchez les critères d’arrêt (la durée pendant laquelle la recherche).</span><span class="sxs-lookup"><span data-stu-id="e92ac-119">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e92ac-120">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="e92ac-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e92ac-121">Élément</span><span class="sxs-lookup"><span data-stu-id="e92ac-121">Element</span></span>|<span data-ttu-id="e92ac-122">Description</span><span class="sxs-lookup"><span data-stu-id="e92ac-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e92ac-123">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e92ac-123">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e92ac-124">Définit un point de terminaison standard qui contient des informations pour permettre à une application de fonctionner en tant que programme client qui peut rechercher l'adresse du point de terminaison de manière dynamique au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e92ac-124">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e92ac-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e92ac-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>

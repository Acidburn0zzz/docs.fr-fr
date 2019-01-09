---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f790e294b832f43a595d0636c60a8a67da5ad56a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147887"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="a5642-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="a5642-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="a5642-103">Représente une table de routage qui contient une liste de filtres pour évaluer des messages et router les messages vers le point de terminaison client si le filtre a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="a5642-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="a5642-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a5642-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a5642-105">\<routage ></span><span class="sxs-lookup"><span data-stu-id="a5642-105">\<routing></span></span>  
<span data-ttu-id="a5642-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="a5642-106">\<routingTables></span></span>  
<span data-ttu-id="a5642-107">\<table ></span><span class="sxs-lookup"><span data-stu-id="a5642-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5642-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a5642-108">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5642-109">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="a5642-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a5642-110">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="a5642-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5642-111">Attributs</span><span class="sxs-lookup"><span data-stu-id="a5642-111">Attributes</span></span>  
  
|<span data-ttu-id="a5642-112">Élément</span><span class="sxs-lookup"><span data-stu-id="a5642-112">Element</span></span>|<span data-ttu-id="a5642-113">Description</span><span class="sxs-lookup"><span data-stu-id="a5642-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5642-114">name</span><span class="sxs-lookup"><span data-stu-id="a5642-114">name</span></span>|<span data-ttu-id="a5642-115">Chaîne qui contient le nom unique de cet élément de configuration.</span><span class="sxs-lookup"><span data-stu-id="a5642-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5642-116">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="a5642-116">Child Elements</span></span>  
  
|<span data-ttu-id="a5642-117">Élément</span><span class="sxs-lookup"><span data-stu-id="a5642-117">Element</span></span>|<span data-ttu-id="a5642-118">Description</span><span class="sxs-lookup"><span data-stu-id="a5642-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5642-119">\<filtres></span><span class="sxs-lookup"><span data-stu-id="a5642-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="a5642-120">Mappages entre les filtres de routage et les points de terminaison cibles auxquels envoyer des messages lorsque le filtre correspond.</span><span class="sxs-lookup"><span data-stu-id="a5642-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5642-121">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="a5642-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a5642-122">Élément</span><span class="sxs-lookup"><span data-stu-id="a5642-122">Element</span></span>|<span data-ttu-id="a5642-123">Description</span><span class="sxs-lookup"><span data-stu-id="a5642-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5642-124">\<routage ></span><span class="sxs-lookup"><span data-stu-id="a5642-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="a5642-125">Section de configuration qui contient des tables de routage.</span><span class="sxs-lookup"><span data-stu-id="a5642-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5642-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5642-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    

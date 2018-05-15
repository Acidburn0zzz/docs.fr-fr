---
title: '&lt;customTrackingQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: aa1e7ff4d53cbd40b168c3cc800a23dbcddc28f5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="88cfa-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="88cfa-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="88cfa-103">Représente une collection de requêtes permettant d’effectuer le suivi des événements que vous définissez dans vos activités de code.</span><span class="sxs-lookup"><span data-stu-id="88cfa-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="88cfa-104">La requête est nécessaire pour qu'un participant au suivi puisse s'abonner à des enregistrements de suivi personnalisés.</span><span class="sxs-lookup"><span data-stu-id="88cfa-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="88cfa-105">Pour plus d’informations sur les requêtes de modèle de suivi, consultez [modèles de suivi](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="88cfa-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="88cfa-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="88cfa-106">\<system.serviceModel></span></span>  
<span data-ttu-id="88cfa-107">\<suivi ></span><span class="sxs-lookup"><span data-stu-id="88cfa-107">\<tracking></span></span>  
<span data-ttu-id="88cfa-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="88cfa-108">\<trackingProfile></span></span>  
<span data-ttu-id="88cfa-109">\<flux de travail ></span><span class="sxs-lookup"><span data-stu-id="88cfa-109">\<workflow></span></span>  
<span data-ttu-id="88cfa-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="88cfa-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88cfa-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="88cfa-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88cfa-112">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="88cfa-112">Attributes and Elements</span></span>  
 <span data-ttu-id="88cfa-113">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="88cfa-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88cfa-114">Attributs</span><span class="sxs-lookup"><span data-stu-id="88cfa-114">Attributes</span></span>  
 <span data-ttu-id="88cfa-115">Aucun.</span><span class="sxs-lookup"><span data-stu-id="88cfa-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="88cfa-116">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="88cfa-116">Child Elements</span></span>  
  
|<span data-ttu-id="88cfa-117">Élément</span><span class="sxs-lookup"><span data-stu-id="88cfa-117">Element</span></span>|<span data-ttu-id="88cfa-118">Description</span><span class="sxs-lookup"><span data-stu-id="88cfa-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88cfa-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="88cfa-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="88cfa-120">Requête qui permet d'effectuer le suivi des événements que vous définissez dans vos activités de code.</span><span class="sxs-lookup"><span data-stu-id="88cfa-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88cfa-121">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="88cfa-121">Parent Elements</span></span>  
  
|<span data-ttu-id="88cfa-122">Élément</span><span class="sxs-lookup"><span data-stu-id="88cfa-122">Element</span></span>|<span data-ttu-id="88cfa-123">Description</span><span class="sxs-lookup"><span data-stu-id="88cfa-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88cfa-124">\<flux de travail ></span><span class="sxs-lookup"><span data-stu-id="88cfa-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="88cfa-125">Un élément de configuration qui contient toutes les requêtes pour un flux de travail spécifique identifié par le **activityDefinitionId** propriété.</span><span class="sxs-lookup"><span data-stu-id="88cfa-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88cfa-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88cfa-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="88cfa-127">Suivi et traçage de workflow</span><span class="sxs-lookup"><span data-stu-id="88cfa-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="88cfa-128">Profils de suivi</span><span class="sxs-lookup"><span data-stu-id="88cfa-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

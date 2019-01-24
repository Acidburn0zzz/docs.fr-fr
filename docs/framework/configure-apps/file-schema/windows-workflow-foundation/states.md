---
title: '&lt;states&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: d1ec35b1c434b8188fde7b546e2dee42a93f5c91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550576"
---
# <a name="ltstatesgt"></a><span data-ttu-id="eef2c-102">&lt;states&gt;</span><span class="sxs-lookup"><span data-stu-id="eef2c-102">&lt;states&gt;</span></span>
<span data-ttu-id="eef2c-103">Représente une collection d’états faisant l’objet d’un abonnement dans l’instance de flux de travail suivie lors de la création des enregistrements de suivi.</span><span class="sxs-lookup"><span data-stu-id="eef2c-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="eef2c-104">Pour plus d’informations sur les requêtes de modèle de suivi, consultez [modèles de suivi](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="eef2c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="eef2c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eef2c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="eef2c-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="eef2c-106">\<tracking></span></span>  
<span data-ttu-id="eef2c-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="eef2c-107">\<trackingProfile></span></span>  
<span data-ttu-id="eef2c-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="eef2c-108">\<workflow></span></span>  
<span data-ttu-id="eef2c-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="eef2c-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="eef2c-110">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="eef2c-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="eef2c-111">\<states></span><span class="sxs-lookup"><span data-stu-id="eef2c-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef2c-112">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="eef2c-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eef2c-113">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="eef2c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="eef2c-114">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="eef2c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eef2c-115">Attributs</span><span class="sxs-lookup"><span data-stu-id="eef2c-115">Attributes</span></span>  
 <span data-ttu-id="eef2c-116">Aucun.</span><span class="sxs-lookup"><span data-stu-id="eef2c-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eef2c-117">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="eef2c-117">Child Elements</span></span>  
  
|<span data-ttu-id="eef2c-118">Élément</span><span class="sxs-lookup"><span data-stu-id="eef2c-118">Element</span></span>|<span data-ttu-id="eef2c-119">Description</span><span class="sxs-lookup"><span data-stu-id="eef2c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eef2c-120">\<state></span><span class="sxs-lookup"><span data-stu-id="eef2c-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="eef2c-121">État faisant l'objet d'un abonnement de l'instance de flux de travail suivie lors de la création de l'enregistrement de suivi.</span><span class="sxs-lookup"><span data-stu-id="eef2c-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eef2c-122">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="eef2c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="eef2c-123">Élément</span><span class="sxs-lookup"><span data-stu-id="eef2c-123">Element</span></span>|<span data-ttu-id="eef2c-124">Description</span><span class="sxs-lookup"><span data-stu-id="eef2c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eef2c-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="eef2c-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="eef2c-126">Requête qui effectue le suivi des changements dans le cycle de vie d'une instance de flux de travail, tels que le début ou la fin d'un événement.</span><span class="sxs-lookup"><span data-stu-id="eef2c-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eef2c-127">Notes</span><span class="sxs-lookup"><span data-stu-id="eef2c-127">Remarks</span></span>  
 <span data-ttu-id="eef2c-128">Les enregistrements retournés sont filtrés par états dans cette collection.</span><span class="sxs-lookup"><span data-stu-id="eef2c-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="eef2c-129">Les valeurs d'état possibles sont décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="eef2c-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="eef2c-130">État</span><span class="sxs-lookup"><span data-stu-id="eef2c-130">State</span></span>|<span data-ttu-id="eef2c-131">Description</span><span class="sxs-lookup"><span data-stu-id="eef2c-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eef2c-132">Abandonné</span><span class="sxs-lookup"><span data-stu-id="eef2c-132">Aborted</span></span>|<span data-ttu-id="eef2c-133">L'instance de flux de travail est abandonnée.</span><span class="sxs-lookup"><span data-stu-id="eef2c-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="eef2c-134">Terminé</span><span class="sxs-lookup"><span data-stu-id="eef2c-134">Completed</span></span>|<span data-ttu-id="eef2c-135">L'instance de flux de travail est terminée.</span><span class="sxs-lookup"><span data-stu-id="eef2c-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="eef2c-136">Supprimé</span><span class="sxs-lookup"><span data-stu-id="eef2c-136">Deleted</span></span>|<span data-ttu-id="eef2c-137">L'instance de flux de travail est supprimée.</span><span class="sxs-lookup"><span data-stu-id="eef2c-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="eef2c-138">Inactif</span><span class="sxs-lookup"><span data-stu-id="eef2c-138">Idle</span></span>|<span data-ttu-id="eef2c-139">L'instance de workflow est inactive.</span><span class="sxs-lookup"><span data-stu-id="eef2c-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="eef2c-140">Persistant</span><span class="sxs-lookup"><span data-stu-id="eef2c-140">Persisted</span></span>|<span data-ttu-id="eef2c-141">L'instance de flux de travail est persistante.</span><span class="sxs-lookup"><span data-stu-id="eef2c-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="eef2c-142">Repris</span><span class="sxs-lookup"><span data-stu-id="eef2c-142">Resumed</span></span>|<span data-ttu-id="eef2c-143">L'instance de flux de travail est reprise.</span><span class="sxs-lookup"><span data-stu-id="eef2c-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="eef2c-144">Démarré</span><span class="sxs-lookup"><span data-stu-id="eef2c-144">Started</span></span>|<span data-ttu-id="eef2c-145">L'instance de flux de travail est démarrée.</span><span class="sxs-lookup"><span data-stu-id="eef2c-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="eef2c-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="eef2c-146">UnhandledException</span></span>|<span data-ttu-id="eef2c-147">L'instance de flux de travail a rencontré une exception non gérée.</span><span class="sxs-lookup"><span data-stu-id="eef2c-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="eef2c-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="eef2c-148">Unloaded</span></span>|<span data-ttu-id="eef2c-149">L'instance de flux de travail est déchargée.</span><span class="sxs-lookup"><span data-stu-id="eef2c-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="eef2c-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="eef2c-150">Canceled</span></span>|<span data-ttu-id="eef2c-151">L'instance de flux de travail est annulée.</span><span class="sxs-lookup"><span data-stu-id="eef2c-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="eef2c-152">Interrompu</span><span class="sxs-lookup"><span data-stu-id="eef2c-152">Suspended</span></span>|<span data-ttu-id="eef2c-153">L'instance de workflow est interrompue.</span><span class="sxs-lookup"><span data-stu-id="eef2c-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="eef2c-154">Arrêté</span><span class="sxs-lookup"><span data-stu-id="eef2c-154">Terminated</span></span>|<span data-ttu-id="eef2c-155">L'instance de flux de travail est arrêtée.</span><span class="sxs-lookup"><span data-stu-id="eef2c-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="eef2c-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="eef2c-156">Unsuspended</span></span>|<span data-ttu-id="eef2c-157">L'instance de flux de travail est non interrompue.</span><span class="sxs-lookup"><span data-stu-id="eef2c-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eef2c-158">Exemple</span><span class="sxs-lookup"><span data-stu-id="eef2c-158">Example</span></span>  
 <span data-ttu-id="eef2c-159">La configuration suivante permet de s'abonner aux enregistrements de suivi au niveau de l'instance de flux de travail pour l'état de l'instance `Started` à l'aide de cette requête.</span><span class="sxs-lookup"><span data-stu-id="eef2c-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eef2c-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eef2c-160">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eef2c-161">Suivi et traçage de workflow</span><span class="sxs-lookup"><span data-stu-id="eef2c-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eef2c-162">Profils de suivi</span><span class="sxs-lookup"><span data-stu-id="eef2c-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

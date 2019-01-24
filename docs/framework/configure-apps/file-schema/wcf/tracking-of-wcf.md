---
title: '&lt;tracking&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: 52efc1b5284c2a64eae30ea18995e5ee761dc2e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582602"
---
# <a name="lttrackinggt-of-wcf"></a><span data-ttu-id="8b390-102">&lt;tracking&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="8b390-102">&lt;tracking&gt; of WCF</span></span>
<span data-ttu-id="8b390-103">Représente une section de configuration permettant de définir les paramètres de suivi d'un service de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="8b390-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="8b390-104">Pour plus d’informations de suivi de workflow et sa configuration, consultez [suivi et traçage de Workflow](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) et [configuration du suivi d’un flux de travail](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8b390-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="8b390-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8b390-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8b390-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="8b390-106">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b390-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8b390-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String"
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String"
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b390-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="8b390-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8b390-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="8b390-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b390-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="8b390-110">Attributes</span></span>  
 <span data-ttu-id="8b390-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="8b390-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8b390-112">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="8b390-112">Child Elements</span></span>  
  
|<span data-ttu-id="8b390-113">Élément</span><span class="sxs-lookup"><span data-stu-id="8b390-113">Element</span></span>|<span data-ttu-id="8b390-114">Description</span><span class="sxs-lookup"><span data-stu-id="8b390-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b390-115">\<participants></span><span class="sxs-lookup"><span data-stu-id="8b390-115">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="8b390-116">Une collection d’éléments de configuration définissent des participants qui s’abonner aux enregistrements de suivi.</span><span class="sxs-lookup"><span data-stu-id="8b390-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="8b390-117">Les participants de suivi contiennent la logique nécessaire pour traiter la charge utile des enregistrements de suivi (par exemple, ils peuvent choisir d'écrire dans un fichier).</span><span class="sxs-lookup"><span data-stu-id="8b390-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="8b390-118">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8b390-118">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="8b390-119">Modèle de suivi permettant de filtrer les enregistrements de suivi émis d'une instance de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="8b390-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b390-120">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="8b390-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8b390-121">Élément</span><span class="sxs-lookup"><span data-stu-id="8b390-121">Element</span></span>|<span data-ttu-id="8b390-122">Description</span><span class="sxs-lookup"><span data-stu-id="8b390-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b390-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8b390-123">system.ServiceModel</span></span>|<span data-ttu-id="8b390-124">Élément racine de tous les éléments de configuration de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="8b390-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b390-125">Notes</span><span class="sxs-lookup"><span data-stu-id="8b390-125">Remarks</span></span>  
 <span data-ttu-id="8b390-126">Le suivi vous fournit la capacité d'examiner l'exécution d'un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="8b390-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="8b390-127">L'infrastructure de suivi de flux de travail instrumente un flux de travail pour émettre des enregistrements qui reflètent les principaux événements pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="8b390-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="8b390-128">Par exemple, lorsqu'une instance de flux de travail démarre ou se termine, des enregistrements de suivi sont émis.</span><span class="sxs-lookup"><span data-stu-id="8b390-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="8b390-129">Le suivi peut également extraire des données métier pertinentes associées aux variables de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="8b390-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="8b390-130">Par exemple, si le flux de travail représente un système de traitement des commandes, l'ID de commande peut être extrait avec l'enregistrement de suivi.</span><span class="sxs-lookup"><span data-stu-id="8b390-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="8b390-131">En général, l'activation du suivi WF facilite les diagnostics ou les analyses d'entreprise à partir d'une exécution de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="8b390-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b390-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b390-132">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="8b390-133">Suivi et traçage de workflow</span><span class="sxs-lookup"><span data-stu-id="8b390-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)

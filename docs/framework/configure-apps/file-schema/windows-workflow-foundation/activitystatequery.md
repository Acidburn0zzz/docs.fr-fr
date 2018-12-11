---
title: '&lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 3c6243e6b8e1d2b32dc830609a5d4df474f48e61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151171"
---
# <a name="ltactivitystatequerygt"></a><span data-ttu-id="0d345-102">&lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0d345-102">&lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="0d345-103">Représente une requête qui permet d'effectuer le suivi des changements dans le cycle de vie des activités qui composent une instance de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="0d345-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="0d345-104">Par exemple, vous souhaiterez effectuer le suivi de chaque fois que l’activité « Envoyer un message électronique » se termine dans une instance de workflow.</span><span class="sxs-lookup"><span data-stu-id="0d345-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="0d345-105">Cette requête est nécessaire pour qu'un participant au suivi puisse s'abonner à des objets d'enregistrement d'état d'activité.</span><span class="sxs-lookup"><span data-stu-id="0d345-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="0d345-106">Les états disponibles auxquels s'abonner sont spécifiés dans ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="0d345-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="0d345-107">Pour plus d’informations sur les requêtes de modèle de suivi, consultez [modèles de suivi](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0d345-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0d345-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0d345-108">\<system.serviceModel></span></span>  
<span data-ttu-id="0d345-109">\<suivi ></span><span class="sxs-lookup"><span data-stu-id="0d345-109">\<tracking></span></span>  
<span data-ttu-id="0d345-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0d345-110">\<trackingProfile></span></span>  
<span data-ttu-id="0d345-111">\<flux de travail ></span><span class="sxs-lookup"><span data-stu-id="0d345-111">\<workflow></span></span>  
<span data-ttu-id="0d345-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="0d345-112">\<activityStateQueries></span></span>  
<span data-ttu-id="0d345-113">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="0d345-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d345-114">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0d345-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
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
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d345-115">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="0d345-115">Attributes and Elements</span></span>  
 <span data-ttu-id="0d345-116">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="0d345-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d345-117">Attributs</span><span class="sxs-lookup"><span data-stu-id="0d345-117">Attributes</span></span>  
  
|<span data-ttu-id="0d345-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="0d345-118">Attribute</span></span>|<span data-ttu-id="0d345-119">Description</span><span class="sxs-lookup"><span data-stu-id="0d345-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d345-120">activityName</span><span class="sxs-lookup"><span data-stu-id="0d345-120">activityName</span></span>|<span data-ttu-id="0d345-121">Chaîne qui spécifie le nom de l'activité sur lequel filtrer des instances <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="0d345-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d345-122">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="0d345-122">Child Elements</span></span>  
  
|<span data-ttu-id="0d345-123">Élément</span><span class="sxs-lookup"><span data-stu-id="0d345-123">Element</span></span>|<span data-ttu-id="0d345-124">Description</span><span class="sxs-lookup"><span data-stu-id="0d345-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d345-125">\<arguments ></span><span class="sxs-lookup"><span data-stu-id="0d345-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="0d345-126">Collection d’arguments associés à cette requête d’activité.</span><span class="sxs-lookup"><span data-stu-id="0d345-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="0d345-127">\<États ></span><span class="sxs-lookup"><span data-stu-id="0d345-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="0d345-128">Collection d’éléments de configuration qui contiennent les états de l’activité faisant l’objet d’un abonnement pour laquelle un enregistrement de suivi doit être émis.</span><span class="sxs-lookup"><span data-stu-id="0d345-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="0d345-129">\<États ></span><span class="sxs-lookup"><span data-stu-id="0d345-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="0d345-130">Collection de variables associées à cette requête d’activité.</span><span class="sxs-lookup"><span data-stu-id="0d345-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d345-131">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="0d345-131">Parent Elements</span></span>  
  
|<span data-ttu-id="0d345-132">Élément</span><span class="sxs-lookup"><span data-stu-id="0d345-132">Element</span></span>|<span data-ttu-id="0d345-133">Description</span><span class="sxs-lookup"><span data-stu-id="0d345-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d345-134">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="0d345-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="0d345-135">Représente une liste d'éléments de configuration qui permettent d'effectuer le suivi des demandes d'annulation d'une activité enfant par l'activité parent.</span><span class="sxs-lookup"><span data-stu-id="0d345-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0d345-136">La requête est nécessaire pour qu'un participant au suivi puisse s'abonner à des objets d'enregistrement de demande d'annulation.</span><span class="sxs-lookup"><span data-stu-id="0d345-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d345-137">Notes</span><span class="sxs-lookup"><span data-stu-id="0d345-137">Remarks</span></span>  
 <span data-ttu-id="0d345-138">Une fonctionnalité propre à ActivityStateQuery est la possibilité d’extraire des données lors du suivi de l’exécution d’un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="0d345-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0d345-139">Vous disposez ainsi d'un contexte supplémentaire lors de l'accès à une post-exécution d'enregistrements de suivi.</span><span class="sxs-lookup"><span data-stu-id="0d345-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0d345-140">Vous pouvez utiliser la [ \<arguments >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<États >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) et [ \<États >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) éléments à extraire une variable ou un argument à partir de toutes les activités dans un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="0d345-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="0d345-141">L’exemple suivant illustre une requête d’état d’activité qui extrait des variables et arguments lorsque l’enregistrement de suivi `Closed` de l’activité est émis.</span><span class="sxs-lookup"><span data-stu-id="0d345-141">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0d345-142">Variables et arguments peuvent être extraits uniquement avec un objet ActivityStateRecord et par conséquent, êtes abonnés au sein d’un suivi à l’aide du profil [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="0d345-142">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d345-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d345-143">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="0d345-144">Suivi et traçage de workflow</span><span class="sxs-lookup"><span data-stu-id="0d345-144">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0d345-145">Profils de suivi</span><span class="sxs-lookup"><span data-stu-id="0d345-145">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

---
title: '&lt;add&gt; de &lt;services&gt;'
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 709636f0b9667a431838b463c05cfd00f6521f6b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754065"
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="37452-102">&lt;add&gt; de &lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="37452-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="37452-103">Spécifie les paramètres d’une instance de <xref:System.Workflow.Runtime.WorkflowRuntime> pour l’hébergement des services de Windows Communication Foundation (WCF) basée sur les flux de travail.</span><span class="sxs-lookup"><span data-stu-id="37452-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="37452-104">Cet élément est de type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="37452-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="37452-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="37452-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="37452-106">\<comportements ></span><span class="sxs-lookup"><span data-stu-id="37452-106">\<behaviors></span></span>  
<span data-ttu-id="37452-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="37452-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="37452-108">\<comportement ></span><span class="sxs-lookup"><span data-stu-id="37452-108">\<behavior></span></span>  
<span data-ttu-id="37452-109">\<services></span><span class="sxs-lookup"><span data-stu-id="37452-109">\<services></span></span>  
<span data-ttu-id="37452-110">\<add></span><span class="sxs-lookup"><span data-stu-id="37452-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37452-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="37452-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37452-112">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="37452-112">Attributes and Elements</span></span>  
 <span data-ttu-id="37452-113">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="37452-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37452-114">Attributs</span><span class="sxs-lookup"><span data-stu-id="37452-114">Attributes</span></span>  
  
|<span data-ttu-id="37452-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="37452-115">Attribute</span></span>|<span data-ttu-id="37452-116">Description</span><span class="sxs-lookup"><span data-stu-id="37452-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37452-117">type</span><span class="sxs-lookup"><span data-stu-id="37452-117">type</span></span>|<span data-ttu-id="37452-118">Chaîne indiquant le nom qualifié du type d'assembly correspondant au service à initialiser.</span><span class="sxs-lookup"><span data-stu-id="37452-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="37452-119">Les services spécifiés doivent suivre certaines règles en ce qui concerne les signatures de leurs constructeurs.</span><span class="sxs-lookup"><span data-stu-id="37452-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="37452-120">Pour plus d'informations, voir <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="37452-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37452-121">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="37452-121">Child Elements</span></span>  
 <span data-ttu-id="37452-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="37452-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37452-123">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="37452-123">Parent Elements</span></span>  
  
|<span data-ttu-id="37452-124">Élément</span><span class="sxs-lookup"><span data-stu-id="37452-124">Element</span></span>|<span data-ttu-id="37452-125">Description</span><span class="sxs-lookup"><span data-stu-id="37452-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37452-126">\<services></span><span class="sxs-lookup"><span data-stu-id="37452-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="37452-127">Collection de services qui sera ajoutée au moteur de <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="37452-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="37452-128">Les éléments sont de type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="37452-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="37452-129">Les services spécifiés dans la collection sont initialisés par le moteur d'exécution de workflow et ajoutés à ses services lorsque le constructeur <xref:System.Workflow.Runtime.WorkflowRuntime> approprié est appelé.</span><span class="sxs-lookup"><span data-stu-id="37452-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="37452-130">Par conséquent, les services spécifiés dans la collection doivent suivre certaines règles en ce qui concerne les signatures de leurs constructeurs.</span><span class="sxs-lookup"><span data-stu-id="37452-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="37452-131">Pour plus d'informations, voir <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="37452-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37452-132">Notes</span><span class="sxs-lookup"><span data-stu-id="37452-132">Remarks</span></span>  
 <span data-ttu-id="37452-133">Le service spécifié dans cet élément est initialisé par le moteur d'exécution de workflow et ajouté à ses services lorsque le constructeur <xref:System.Workflow.Runtime.WorkflowRuntime> approprié est appelé.</span><span class="sxs-lookup"><span data-stu-id="37452-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="37452-134">Par conséquent, le service spécifié doit suivre certaines règles en ce qui concerne les signatures de son constructeur.</span><span class="sxs-lookup"><span data-stu-id="37452-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="37452-135">Pour plus d'informations, voir <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="37452-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37452-136">Exemple</span><span class="sxs-lookup"><span data-stu-id="37452-136">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="37452-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37452-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="37452-138">Fichiers de Configuration de flux de travail</span><span class="sxs-lookup"><span data-stu-id="37452-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)

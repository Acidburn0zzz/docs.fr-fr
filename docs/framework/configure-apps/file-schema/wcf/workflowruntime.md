---
title: '&lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 849b09936f303c21fe55a6a46d561590c6a4c808
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504959"
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="504ea-102">&lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="504ea-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="504ea-103">Spécifie les paramètres d’une instance de <xref:System.Workflow.Runtime.WorkflowRuntime> pour l’hébergement de services de Windows Communication Foundation (WCF) basés sur les flux de travail.</span><span class="sxs-lookup"><span data-stu-id="504ea-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="504ea-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="504ea-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="504ea-105">\<comportements ></span><span class="sxs-lookup"><span data-stu-id="504ea-105">\<behaviors></span></span>  
<span data-ttu-id="504ea-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="504ea-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="504ea-107">\<comportement ></span><span class="sxs-lookup"><span data-stu-id="504ea-107">\<behavior></span></span>  
<span data-ttu-id="504ea-108">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="504ea-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="504ea-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="504ea-109">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"  
                                  enablePerformanceCounters="Boolean"  
                                  name="String"  
                                  validateOnCreate="Boolean">  
                 <commonParameters>  
                    <add name="String" value="String" />  
                 </commonParameters>  
                 <services>  
                    <add type="String"/>  
                 </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="504ea-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="504ea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="504ea-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="504ea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="504ea-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="504ea-112">Attributes</span></span>  
  
|<span data-ttu-id="504ea-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="504ea-113">Attribute</span></span>|<span data-ttu-id="504ea-114">Description</span><span class="sxs-lookup"><span data-stu-id="504ea-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="504ea-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="504ea-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="504ea-116">Valeur <xref:System.TimeSpan> facultative qui définit la durée maximale pendant laquelle une instance de workflow reste en mémoire en ayant l'état inactif avant d'être déchargée ou annulée.</span><span class="sxs-lookup"><span data-stu-id="504ea-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="504ea-117">Si le workflowruntime contient `PersistenceService` qui exécute unloadOnIdle, cet attribut est ignoré.</span><span class="sxs-lookup"><span data-stu-id="504ea-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="504ea-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="504ea-118">enablePerformanceCounters</span></span>|<span data-ttu-id="504ea-119">Valeur booléenne facultative indiquant si les compteurs de performance sont activés.</span><span class="sxs-lookup"><span data-stu-id="504ea-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="504ea-120">Les compteurs de performance fournissent des informations sur différentes statistiques concernant le workflow, mais ils entraînent une altération des performances lorsque le moteur d'exécution de workflow démarre et lorsque les instances de workflow s'exécutent.</span><span class="sxs-lookup"><span data-stu-id="504ea-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="504ea-121">La valeur par défaut est `true`.</span><span class="sxs-lookup"><span data-stu-id="504ea-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="504ea-122">name</span><span class="sxs-lookup"><span data-stu-id="504ea-122">name</span></span>|<span data-ttu-id="504ea-123">Chaîne contenant le nom du moteur d'exécution de workflow.</span><span class="sxs-lookup"><span data-stu-id="504ea-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="504ea-124">Ce nom est utilisé dans la sortie pour distinguer ce runtime d'autres runtime qui peuvent s'exécuter sur le système, par exemple, dans les compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="504ea-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="504ea-125">La valeur par défaut est une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="504ea-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="504ea-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="504ea-126">validateOnCreate</span></span>|<span data-ttu-id="504ea-127">Valeur booléenne facultative indiquant si la validation de la définition de workflow aura lieu lors de l'ouverture de WorkflowServiceHost.</span><span class="sxs-lookup"><span data-stu-id="504ea-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="504ea-128">Si cet attribut a la valeur `true`, la validation du workflow est exécutée à chaque appel de `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="504ea-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="504ea-129">En cas d'erreurs de validation, une erreur <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> est générée.</span><span class="sxs-lookup"><span data-stu-id="504ea-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="504ea-130">Lorsque cette propriété a la valeur `false`, aucune validation de la définition du Workflow n'a lieu.</span><span class="sxs-lookup"><span data-stu-id="504ea-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="504ea-131">La valeur par défaut de cette propriété est `true`.</span><span class="sxs-lookup"><span data-stu-id="504ea-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="504ea-132">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="504ea-132">Child Elements</span></span>  
  
|<span data-ttu-id="504ea-133">Élément</span><span class="sxs-lookup"><span data-stu-id="504ea-133">Element</span></span>|<span data-ttu-id="504ea-134">Description</span><span class="sxs-lookup"><span data-stu-id="504ea-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="504ea-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="504ea-135">commonParameters</span></span>|<span data-ttu-id="504ea-136">Collection de paramètres communs utilisée par les services.</span><span class="sxs-lookup"><span data-stu-id="504ea-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="504ea-137">Cette collection inclut généralement la chaîne de connexion de base de données pouvant être partagée par les services fiables.</span><span class="sxs-lookup"><span data-stu-id="504ea-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="504ea-138">services</span><span class="sxs-lookup"><span data-stu-id="504ea-138">services</span></span>|<span data-ttu-id="504ea-139">Collection de services qui sera ajoutée au moteur de <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="504ea-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="504ea-140">Les éléments sont de type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="504ea-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="504ea-141">Les services spécifiés dans la collection sont initialisés par le moteur d'exécution de workflow et ajoutés à ses services lorsque le constructeur <xref:System.Workflow.Runtime.WorkflowRuntime> approprié est appelé.</span><span class="sxs-lookup"><span data-stu-id="504ea-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="504ea-142">Par conséquent, les services spécifiés dans la collection doivent suivre certaines règles en ce qui concerne les signatures de leurs constructeurs.</span><span class="sxs-lookup"><span data-stu-id="504ea-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="504ea-143">Pour plus d'informations, voir <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="504ea-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="504ea-144">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="504ea-144">Parent Elements</span></span>  
  
|<span data-ttu-id="504ea-145">Élément</span><span class="sxs-lookup"><span data-stu-id="504ea-145">Element</span></span>|<span data-ttu-id="504ea-146">Description</span><span class="sxs-lookup"><span data-stu-id="504ea-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="504ea-147">\<behavior></span><span class="sxs-lookup"><span data-stu-id="504ea-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="504ea-148">Spécifie un élément de comportement.</span><span class="sxs-lookup"><span data-stu-id="504ea-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="504ea-149">Notes</span><span class="sxs-lookup"><span data-stu-id="504ea-149">Remarks</span></span>  
 <span data-ttu-id="504ea-150">Pour plus d’informations sur l’utilisation d’un fichier de configuration pour contrôler le comportement d’un <xref:System.Workflow.Runtime.WorkflowRuntime> objet d’une application hôte Windows Workflow Foundation, consultez [les fichiers de Configuration de flux de travail](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="504ea-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="504ea-151">Exemple</span><span class="sxs-lookup"><span data-stu-id="504ea-151">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <commonParameters>  
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
            <add name="EnableRetries" value="True" />  
         </commonParameters>  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="504ea-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="504ea-152">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <span data-ttu-id="504ea-153">[Fichiers de Configuration de flux de travail](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="504ea-153">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>

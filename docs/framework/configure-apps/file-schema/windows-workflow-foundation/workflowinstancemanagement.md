---
title: '&lt;workflowInstanceManagement&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: d86b0f61c6741fa156e04da75a62853f459324d1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancemanagementgt"></a><span data-ttu-id="af95b-102">&lt;workflowInstanceManagement&gt;</span><span class="sxs-lookup"><span data-stu-id="af95b-102">&lt;workflowInstanceManagement&gt;</span></span>
<span data-ttu-id="af95b-103">Comportement de service qui vous permet de spécifier des paramètres qui contrôlent le mode d'exécution des instances de flux de travail, notamment la persistance, le comportement d'exception non prise en charge et le comportement inactif.</span><span class="sxs-lookup"><span data-stu-id="af95b-103">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
<span data-ttu-id="af95b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="af95b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="af95b-105">\<comportements ></span><span class="sxs-lookup"><span data-stu-id="af95b-105">\<behaviors></span></span>  
<span data-ttu-id="af95b-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="af95b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="af95b-107">\<comportement ></span><span class="sxs-lookup"><span data-stu-id="af95b-107">\<behavior></span></span>  
<span data-ttu-id="af95b-108">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="af95b-108">\<workflowInstanceManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af95b-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="af95b-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af95b-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="af95b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="af95b-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="af95b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af95b-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="af95b-112">Attributes</span></span>  
  
|<span data-ttu-id="af95b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="af95b-113">Attribute</span></span>|<span data-ttu-id="af95b-114">Description</span><span class="sxs-lookup"><span data-stu-id="af95b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af95b-115">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="af95b-115">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="af95b-116">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="af95b-116">Child Elements</span></span>  
 <span data-ttu-id="af95b-117">Aucun.</span><span class="sxs-lookup"><span data-stu-id="af95b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af95b-118">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="af95b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="af95b-119">Élément</span><span class="sxs-lookup"><span data-stu-id="af95b-119">Element</span></span>|<span data-ttu-id="af95b-120">Description</span><span class="sxs-lookup"><span data-stu-id="af95b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af95b-121">\<comportement > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="af95b-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="af95b-122">Spécifie un élément de comportement.</span><span class="sxs-lookup"><span data-stu-id="af95b-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af95b-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af95b-123">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>

---
title: Interopérabilité avec l'ensemble de règles 3.5
ms.date: 03/30/2017
ms.assetid: 969f3295-d874-428c-a9c6-623e3d578e51
ms.openlocfilehash: 5ea5454ef80bfd83611ed20392782d99cd8c0c25
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43777091"
---
# <a name="interop-with-35-rule-set"></a><span data-ttu-id="35e7b-102">Interopérabilité avec l'ensemble de règles 3.5</span><span class="sxs-lookup"><span data-stu-id="35e7b-102">Interop with 3.5 Rule Set</span></span>
<span data-ttu-id="35e7b-103">Cet exemple illustre l’utilisation de la <xref:System.Activities.Statements.Interop> activité à intégrer à une activité personnalisée dans [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] à l’aide de <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` et règles.</span><span class="sxs-lookup"><span data-stu-id="35e7b-103">This sample demonstrates the use of the <xref:System.Activities.Statements.Interop> activity to integrate with a custom activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] using <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` and rules.</span></span> <span data-ttu-id="35e7b-104">Il passe des données à l'activité personnalisée en liant des variables [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] aux propriétés de dépendance exposées par l'activité personnalisée.</span><span class="sxs-lookup"><span data-stu-id="35e7b-104">It passes data to the custom activity by binding [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35e7b-105">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="35e7b-105">Requirements</span></span>  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
2.  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
3.  [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]  
  
## <a name="demonstrates"></a><span data-ttu-id="35e7b-106">Démonstrations</span><span class="sxs-lookup"><span data-stu-id="35e7b-106">Demonstrates</span></span>  
 <span data-ttu-id="35e7b-107"><xref:System.Activities.Statements.Interop> activité, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activité dans [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] avec les propriétés de dépendance</span><span class="sxs-lookup"><span data-stu-id="35e7b-107"><xref:System.Activities.Statements.Interop> activity, <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] with dependency properties</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="35e7b-108">Discussion</span><span class="sxs-lookup"><span data-stu-id="35e7b-108">Discussion</span></span>  
 <span data-ttu-id="35e7b-109">L'exemple illustre l'un des scénarios d'intégration pour l'intégration avec une activité [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35e7b-109">The sample demonstrates one of the integration scenarios for integrating with a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] activity.</span></span> <span data-ttu-id="35e7b-110">Cet exemple inclut un [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] activité personnalisée qui appelle un <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activité.</span><span class="sxs-lookup"><span data-stu-id="35e7b-110">This sample includes a [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] custom activity that invokes a <!--zz <xref:System.Workflow.Activities.Policy> --> `System.Workflow.Activities.Policy` activity.</span></span>  
  
## <a name="travelrulelibrary"></a><span data-ttu-id="35e7b-111">TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="35e7b-111">TravelRuleLibrary</span></span>  
 <span data-ttu-id="35e7b-112">L'ouverture de TravelRuleSet.cs dans le concepteur affiche une activité séquentielle personnalisée qui contient une activité Policy telles que la suivante :</span><span class="sxs-lookup"><span data-stu-id="35e7b-112">Opening TravelRuleSet.cs in the designer shows a custom sequential activity that contains a Policy activity as follows</span></span>  
  
 <span data-ttu-id="35e7b-113">![Activité d’interopérabilité](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span><span class="sxs-lookup"><span data-stu-id="35e7b-113">![Interop Activity](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulespolicy.jpg "InteropRulesPolicy")</span></span>  
  
 <span data-ttu-id="35e7b-114">Double-cliquez sur le **DiscountPolicy** activité pour examiner les règles de stratégie.</span><span class="sxs-lookup"><span data-stu-id="35e7b-114">Double-click the **DiscountPolicy** policy activity to examine the rules.</span></span> <span data-ttu-id="35e7b-115">L'éditeur de règles semble afficher les règles.</span><span class="sxs-lookup"><span data-stu-id="35e7b-115">The Rules editor appears to show the rules.</span></span>  
  
 <span data-ttu-id="35e7b-116">![Éditeur d’ensemble de règles](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span><span class="sxs-lookup"><span data-stu-id="35e7b-116">![Rule Set Editor](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesruleseteditor.jpg "InteropRulesRuleSetEditor")</span></span>  
  
 <span data-ttu-id="35e7b-117">Avec le bouton droit le **DiscountPolicy** activité et sélectionnez le **afficher le Code** option pour examiner le code-beside code c# qui accompagne cette activité.</span><span class="sxs-lookup"><span data-stu-id="35e7b-117">Right-click the **DiscountPolicy** activity and select the **View Code** option to examine the code-beside C# code that goes with this activity.</span></span> <span data-ttu-id="35e7b-118">Observez le paramètre de propriété de dépendance pour `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="35e7b-118">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="35e7b-119">Cela est équivalent à un <xref:System.Activities.Argument> dans [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35e7b-119">This is equivalent to an <xref:System.Activities.Argument> in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span>  
  
```  
public static DependencyProperty DiscountLevelProperty = DependencyProperty.Register("DiscountLevel", typeof(int), typeof(TravelRuleSet));  
  
[DescriptionAttribute("DiscountLevel")]  
[CategoryAttribute("DiscountLevel Category")]  
[BrowsableAttribute(true)]  
[DesignerSerializationVisibilityAttribute(DesignerSerializationVisibility.Visible)]  
public int DiscountLevel  
{  
   get  
   {  
return ((int)base.GetValue(TravelRuleSet.DiscountLevelProperty)));  
   }  
   set  
   {  
base.SetValue(TravelRuleSet.DiscountLevelProperty, value);  
   }  
}  
```  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="35e7b-120">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="35e7b-120">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="35e7b-121">C'est un projet de workflow séquentiel [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] qui utilise l'activité <xref:System.Activities.Statements.Interop> pour une intégration à l'ensemble de règles personnalisé créé dans le projet TravelRuleLibrary.</span><span class="sxs-lookup"><span data-stu-id="35e7b-121">This is a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom rule set created in the TravelRuleLibrary project.</span></span> <span data-ttu-id="35e7b-122">Les variables sont créées sur le <xref:System.Activities.Statements.Sequence> de niveau supérieur, comme suit.</span><span class="sxs-lookup"><span data-stu-id="35e7b-122">Variables are created on the top-level <xref:System.Activities.Statements.Sequence> as follows.</span></span>  
  
 <span data-ttu-id="35e7b-123">![Variables](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span><span class="sxs-lookup"><span data-stu-id="35e7b-123">![Variables](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesvariables.jpg "InteropRulesVariables")</span></span>  
  
 <span data-ttu-id="35e7b-124">![L’Explorateur de solutions](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span><span class="sxs-lookup"><span data-stu-id="35e7b-124">![Solution Explorer](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulessolutionexplorer.jpg "InteropRulesSolutionExplorer")</span></span>  
  
 <span data-ttu-id="35e7b-125">Pour finir, l'activité <xref:System.Activities.Statements.Interop> est utilisée pour s'intégrer à TravelRuleSet.</span><span class="sxs-lookup"><span data-stu-id="35e7b-125">Lastly, the <xref:System.Activities.Statements.Interop> activity is used to integrate with the TravelRuleSet.</span></span> <span data-ttu-id="35e7b-126">Les variables qui ont été déclarées précédemment sur <xref:System.Activities.Statements.Sequence> sont utilisées pour créer une liaison aux propriétés de dépendance.</span><span class="sxs-lookup"><span data-stu-id="35e7b-126">The variables that were declared earlier on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
 <span data-ttu-id="35e7b-127">![Type d’activité](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span><span class="sxs-lookup"><span data-stu-id="35e7b-127">![Activity Type](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprules.jpg "InteropRules")</span></span>  
  
 <span data-ttu-id="35e7b-128">![Flèche](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span><span class="sxs-lookup"><span data-stu-id="35e7b-128">![Arrow](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesarrow.jpg "InteropRulesArrow")</span></span>  
  
 <span data-ttu-id="35e7b-129">![Propriétés](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span><span class="sxs-lookup"><span data-stu-id="35e7b-129">![Properties](../../../../docs/framework/windows-workflow-foundation/samples/media/interoprulesproperties.jpg "InteropRulesProperties")</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35e7b-130">Les exemples peuvent déjà être installés sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="35e7b-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="35e7b-131">Recherchez le répertoire (par défaut) suivant avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="35e7b-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="35e7b-132">Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples.</span><span class="sxs-lookup"><span data-stu-id="35e7b-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35e7b-133">Cet exemple se trouve dans le répertoire suivant.</span><span class="sxs-lookup"><span data-stu-id="35e7b-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`

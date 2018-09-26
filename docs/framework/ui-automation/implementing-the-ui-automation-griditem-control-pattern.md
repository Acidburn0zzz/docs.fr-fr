---
title: Implémentation du modèle de contrôle GridItem d'UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 68de80e4a01de27c16c0ed85c4177c562d5e328b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47089946"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="4223d-102">Implémentation du modèle de contrôle GridItem d’UI Automation</span><span class="sxs-lookup"><span data-stu-id="4223d-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="4223d-103">Cette documentation s'adresse aux développeurs .NET Framework qui souhaitent utiliser les classes [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] managées définies dans l'espace de noms <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="4223d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4223d-104">Pour plus d’informations sur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consultez [Windows Automation API : UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4223d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4223d-105">Cette rubrique présente les conventions de mise en œuvre et <xref:System.Windows.Automation.Provider.IGridItemProvider>, y compris des informations sur les propriétés.</span><span class="sxs-lookup"><span data-stu-id="4223d-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="4223d-106">Des liens vers des références supplémentaires sont répertoriés à la fin de la vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="4223d-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="4223d-107">Le <xref:System.Windows.Automation.GridItemPattern> modèle de contrôle est utilisé pour prendre en charge les contrôles enfants individuels de conteneurs qui implémentent <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="4223d-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="4223d-108">Pour obtenir des exemples de contrôles implémentant ce modèle de contrôle, consultez [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4223d-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="4223d-109">Conventions et recommandations en matière d'implémentation</span><span class="sxs-lookup"><span data-stu-id="4223d-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="4223d-110">Lors de l’implémentation <xref:System.Windows.Automation.Provider.IGridProvider>, notez les conventions et recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4223d-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="4223d-111">Les coordonnées de grille ont une base zéro et la cellule supérieure gauche possède les coordonnées (0, 0).</span><span class="sxs-lookup"><span data-stu-id="4223d-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="4223d-112">Cellules fusionnées signalent leurs <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> et <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> propriétés basées sur leur cellule d’ancrage sous-jacente, comme défini par le fournisseur UI Automation.</span><span class="sxs-lookup"><span data-stu-id="4223d-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="4223d-113">En règle générale, il s’agit de la ligne la plus haute ou de la colonne la plus à gauche.</span><span class="sxs-lookup"><span data-stu-id="4223d-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
-   <span data-ttu-id="4223d-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> ne fournit pas de manipulation active de la grille telle que la fusion ou le fractionnement des cellules.</span><span class="sxs-lookup"><span data-stu-id="4223d-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
-   <span data-ttu-id="4223d-115">Contrôles qui implémentent <xref:System.Windows.Automation.Provider.IGridItemProvider> peut généralement être parcouru (autrement dit, un client UI Automation peut déplacer vers les contrôles adjacents) à l’aide du clavier.</span><span class="sxs-lookup"><span data-stu-id="4223d-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="4223d-116">Membres obligatoires pour IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="4223d-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="4223d-117">Les propriétés et méthodes suivantes sont nécessaires à l'implémentation d'<xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="4223d-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="4223d-118">Membres requis</span><span class="sxs-lookup"><span data-stu-id="4223d-118">Required members</span></span>|<span data-ttu-id="4223d-119">Type de membre</span><span class="sxs-lookup"><span data-stu-id="4223d-119">Member type</span></span>|<span data-ttu-id="4223d-120">Notes</span><span class="sxs-lookup"><span data-stu-id="4223d-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="4223d-121">Propriété</span><span class="sxs-lookup"><span data-stu-id="4223d-121">Property</span></span>|<span data-ttu-id="4223d-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="4223d-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="4223d-123">Propriété</span><span class="sxs-lookup"><span data-stu-id="4223d-123">Property</span></span>|<span data-ttu-id="4223d-124">Aucun.</span><span class="sxs-lookup"><span data-stu-id="4223d-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="4223d-125">Propriété</span><span class="sxs-lookup"><span data-stu-id="4223d-125">Property</span></span>|<span data-ttu-id="4223d-126">Aucun.</span><span class="sxs-lookup"><span data-stu-id="4223d-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="4223d-127">Propriété</span><span class="sxs-lookup"><span data-stu-id="4223d-127">Property</span></span>|<span data-ttu-id="4223d-128">Aucun.</span><span class="sxs-lookup"><span data-stu-id="4223d-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="4223d-129">Propriété</span><span class="sxs-lookup"><span data-stu-id="4223d-129">Property</span></span>|<span data-ttu-id="4223d-130">Aucun.</span><span class="sxs-lookup"><span data-stu-id="4223d-130">None</span></span>|  
  
 <span data-ttu-id="4223d-131">Ce modèle de contrôle n’est associé à aucune méthode ou aucun événement.</span><span class="sxs-lookup"><span data-stu-id="4223d-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="4223d-132">Exceptions</span><span class="sxs-lookup"><span data-stu-id="4223d-132">Exceptions</span></span>  
 <span data-ttu-id="4223d-133">Ce modèle de contrôle n’est associé à aucune exception.</span><span class="sxs-lookup"><span data-stu-id="4223d-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4223d-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4223d-134">See Also</span></span>  
 [<span data-ttu-id="4223d-135">Vue d’ensemble des modèles de contrôle UI Automation</span><span class="sxs-lookup"><span data-stu-id="4223d-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="4223d-136">Prendre en charge des modèles de contrôle dans un fournisseur UI Automation</span><span class="sxs-lookup"><span data-stu-id="4223d-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="4223d-137">Modèles de contrôle UI Automation pour les clients</span><span class="sxs-lookup"><span data-stu-id="4223d-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="4223d-138">Implémentation du modèle de contrôle Grid d’UI Automation</span><span class="sxs-lookup"><span data-stu-id="4223d-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="4223d-139">Présentation de l’arborescence UI Automation</span><span class="sxs-lookup"><span data-stu-id="4223d-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="4223d-140">Utiliser la mise en cache dans UI Automation</span><span class="sxs-lookup"><span data-stu-id="4223d-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)

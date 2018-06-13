---
title: Appeler un contrôle à l'aide d'UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 89e528e7ff3dbeeba30307adf83434b83f540221
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408322"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="163d7-102">Appeler un contrôle à l'aide d'UI Automation</span><span class="sxs-lookup"><span data-stu-id="163d7-102">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="163d7-103">Cette documentation s'adresse aux développeurs .NET Framework qui souhaitent utiliser les classes [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] managées définies dans l'espace de noms <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="163d7-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="163d7-104">Pour obtenir les dernières informations sur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consultez [API Windows Automation : UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="163d7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="163d7-105">Cette rubrique montre comment effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="163d7-105">This topic demonstrates how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="163d7-106">Rechercher un contrôle qui correspond aux conditions de la propriété spécifique en parcourant la vue de contrôle de l’arborescence [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] pour l’application cible.</span><span class="sxs-lookup"><span data-stu-id="163d7-106">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
-   <span data-ttu-id="163d7-107">Créer un <xref:System.Windows.Automation.AutomationElement> pour chaque contrôle.</span><span class="sxs-lookup"><span data-stu-id="163d7-107">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
-   <span data-ttu-id="163d7-108">Obtenir un objet <xref:System.Windows.Automation.InvokePattern> depuis n’importe quel élément [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] trouvé qui prend en charge le modèle de contrôle <xref:System.Windows.Automation.InvokePattern> .</span><span class="sxs-lookup"><span data-stu-id="163d7-108">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
-   <span data-ttu-id="163d7-109">Utiliser <xref:System.Windows.Automation.InvokePattern.Invoke%2A> pour appeler le contrôle à partir d’un gestionnaire d’événements client.</span><span class="sxs-lookup"><span data-stu-id="163d7-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="163d7-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="163d7-110">Example</span></span>  
 <span data-ttu-id="163d7-111">Cet exemple utilise la méthode <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> de la classe <xref:System.Windows.Automation.AutomationElement> pour générer un objet <xref:System.Windows.Automation.InvokePattern> et appeler un contrôle à l’aide de la méthode <xref:System.Windows.Automation.InvokePattern.Invoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="163d7-111">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="163d7-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="163d7-112">See Also</span></span>  
 [<span data-ttu-id="163d7-113">InvokePattern et ExpandCollapsePattern Menu exemple d’élément</span><span class="sxs-lookup"><span data-stu-id="163d7-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](http://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)

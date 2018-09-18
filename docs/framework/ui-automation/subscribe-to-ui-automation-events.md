---
title: S'abonner à des événements UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: c6845a85f9d3e07a4ecc9aad1ec11df8cdbc1f7a
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45745956"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="92f1c-102">S'abonner à des événements UI Automation</span><span class="sxs-lookup"><span data-stu-id="92f1c-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
>  <span data-ttu-id="92f1c-103">Cette documentation s'adresse aux développeurs .NET Framework qui souhaitent utiliser les classes [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] managées définies dans l'espace de noms <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="92f1c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="92f1c-104">Pour plus d’informations sur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consultez [Windows Automation API : UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="92f1c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="92f1c-105">Cette rubrique montre comment s’abonner à des événements déclenchés par des fournisseurs UI Automation.</span><span class="sxs-lookup"><span data-stu-id="92f1c-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92f1c-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="92f1c-106">Example</span></span>  
 <span data-ttu-id="92f1c-107">L’exemple de code suivant inscrit un gestionnaire d’événements pour l’événement qui est déclenché quand un contrôle tel qu’un bouton est appelé, et le supprime à la fermeture du formulaire d’application.</span><span class="sxs-lookup"><span data-stu-id="92f1c-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="92f1c-108">L’événement est identifié par un <xref:System.Windows.Automation.AutomationEvent> passé en tant que paramètre à <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="92f1c-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="92f1c-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="92f1c-109">Example</span></span>  
 <span data-ttu-id="92f1c-110">L’exemple suivant montre comment utiliser [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] pour vous abonner à un événement est déclenché lorsque le focus est modifié.</span><span class="sxs-lookup"><span data-stu-id="92f1c-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="92f1c-111">L’inscription du gestionnaire d’événements est annulée dans une méthode qui peut être appelée à l’arrêt de l’application, ou quand la notification d’événements d’interface utilisateur n’est plus obligatoire.</span><span class="sxs-lookup"><span data-stu-id="92f1c-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="92f1c-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92f1c-112">See Also</span></span>  
 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>  
 [<span data-ttu-id="92f1c-113">Vue d’ensemble des événements UI Automation</span><span class="sxs-lookup"><span data-stu-id="92f1c-113">UI Automation Events Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-events-overview.md)

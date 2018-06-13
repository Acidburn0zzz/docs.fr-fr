---
title: 'Comment : rechercher une horloge de façon synchrone'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: d8e7b0f4bfa3a59814d87bfb6d7e8b40bd80f6e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559853"
---
# <a name="how-to-seek-a-clock-synchronously"></a><span data-ttu-id="26b2a-102">Comment : rechercher une horloge de façon synchrone</span><span class="sxs-lookup"><span data-stu-id="26b2a-102">How to: Seek a Clock Synchronously</span></span>
<span data-ttu-id="26b2a-103">Utilisez la <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> méthode pour rechercher de façon synchrone une horloge à un point spécifique.</span><span class="sxs-lookup"><span data-stu-id="26b2a-103">Use the <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> method to seek a clock to a specific point synchronously.</span></span> <span data-ttu-id="26b2a-104">L’exemple suivant montre les deux le <xref:System.Windows.Media.Animation.ClockController.Seek%2A> et <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> méthodes d’un <xref:System.Windows.Media.Animation.ClockController>.</span><span class="sxs-lookup"><span data-stu-id="26b2a-104">The following example demonstrates both the <xref:System.Windows.Media.Animation.ClockController.Seek%2A> and <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> methods of a <xref:System.Windows.Media.Animation.ClockController>.</span></span>  
  
 <span data-ttu-id="26b2a-105">Cet exemple montre comment rechercher un <xref:System.Windows.Media.Animation.Clock>; pour obtenir un exemple montrant comment rechercher un storyboard, consultez [rechercher une table de montage séquentiel de façon synchrone](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .</span><span class="sxs-lookup"><span data-stu-id="26b2a-105">This example shows how to seek a <xref:System.Windows.Media.Animation.Clock>; for an example showing how to seek a storyboard, see [Seek a Storyboard Synchronously](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .</span></span>  
  
## <a name="example"></a><span data-ttu-id="26b2a-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="26b2a-106">Example</span></span>  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]

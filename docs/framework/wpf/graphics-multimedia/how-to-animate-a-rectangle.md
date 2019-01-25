---
title: 'Procédure : Animer un rectangle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], rectangles
- rectangles [WPF], animating
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
ms.openlocfilehash: d164a6ecc64c1a4e78be41304cace7515684b488
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530107"
---
# <a name="how-to-animate-a-rectangle"></a><span data-ttu-id="c1191-102">Procédure : Animer un rectangle</span><span class="sxs-lookup"><span data-stu-id="c1191-102">How to: Animate a Rectangle</span></span>
<span data-ttu-id="c1191-103">Cet exemple montre comment animer les modifications apportées à la taille et à la position d’un rectangle.</span><span class="sxs-lookup"><span data-stu-id="c1191-103">This example shows how to animate changes to the size and position of a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1191-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="c1191-104">Example</span></span>  
 <span data-ttu-id="c1191-105">L’exemple suivant utilise une instance de la <xref:System.Windows.Media.Animation.RectAnimation> classe pour animer la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> propriété d’un <xref:System.Windows.Media.RectangleGeometry>, qui anime les modifications apportées à la taille et la position du rectangle.</span><span class="sxs-lookup"><span data-stu-id="c1191-105">The following example uses an instance of the <xref:System.Windows.Media.Animation.RectAnimation> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>, which animates changes to the size and position of the rectangle.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c1191-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1191-106">See also</span></span>
- <xref:System.Windows.Media.Animation.RectAnimation>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.RectangleGeometry>
- [<span data-ttu-id="c1191-107">Vue d’ensemble de l’animation</span><span class="sxs-lookup"><span data-stu-id="c1191-107">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="c1191-108">Graphiques et multimédia</span><span class="sxs-lookup"><span data-stu-id="c1191-108">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [<span data-ttu-id="c1191-109">Rubriques de guide pratique</span><span class="sxs-lookup"><span data-stu-id="c1191-109">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)
- [<span data-ttu-id="c1191-110">Animation et minutage</span><span class="sxs-lookup"><span data-stu-id="c1191-110">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="c1191-111">Rubriques de guide pratique</span><span class="sxs-lookup"><span data-stu-id="c1191-111">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)

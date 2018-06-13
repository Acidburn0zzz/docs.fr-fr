---
title: 'Comment : dessiner une seule B&#233;Spline de Bézier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: 9e91b63275c37fc0cdde5721fddd114e1bf2264e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521334"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="ef42c-102">Comment : dessiner une seule B&#233;Spline de Bézier</span><span class="sxs-lookup"><span data-stu-id="ef42c-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="ef42c-103">Une spline de Bézier est définie par quatre points : un point de départ, deux points de contrôle et un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef42c-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef42c-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="ef42c-104">Example</span></span>  
 <span data-ttu-id="ef42c-105">L’exemple suivant dessine une spline de Bézier avec le point de départ (10, 100) et le point de terminaison (200, 100).</span><span class="sxs-lookup"><span data-stu-id="ef42c-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="ef42c-106">Les points de contrôle sont (100, 10) et (150, 150).</span><span class="sxs-lookup"><span data-stu-id="ef42c-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="ef42c-107">L’illustration suivante montre la spline de Bézier qui en résulte avec son point de départ, les points de contrôle et point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="ef42c-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="ef42c-108">L’illustration montre également forme convexe de la spline, qui est un polygone formé en reliant les quatre points avec des lignes droites.</span><span class="sxs-lookup"><span data-stu-id="ef42c-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 <span data-ttu-id="ef42c-109">![Spline de Bézier](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span><span class="sxs-lookup"><span data-stu-id="ef42c-109">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline1.png "BezierSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ef42c-110">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="ef42c-110">Compiling the Code</span></span>  
 <span data-ttu-id="ef42c-111">L'exemple précédent est conçu pour une utilisation avec Windows Forms et nécessite <xref:System.Windows.Forms.PaintEventArgs> `e`, qui est un paramètre du gestionnaire d'événements <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="ef42c-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef42c-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef42c-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawBezier%2A>  
 [<span data-ttu-id="ef42c-113">Splines de Bézier dans GDI+</span><span class="sxs-lookup"><span data-stu-id="ef42c-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="ef42c-114">Guide pratique pour dessiner une séquence de splines de Bézier</span><span class="sxs-lookup"><span data-stu-id="ef42c-114">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)

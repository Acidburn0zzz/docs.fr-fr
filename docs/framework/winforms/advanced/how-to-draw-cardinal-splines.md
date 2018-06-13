---
title: 'Comment : dessiner des splines cardinales'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 3ad06eb28e1d8e6b5d5f4a77e545f174d8a68d9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525058"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="b324f-102">Comment : dessiner des splines cardinales</span><span class="sxs-lookup"><span data-stu-id="b324f-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="b324f-103">Une spline cardinale est une courbe qui passe progressivement par un ensemble donné de points.</span><span class="sxs-lookup"><span data-stu-id="b324f-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="b324f-104">Pour dessiner une spline cardinale, créez un <xref:System.Drawing.Graphics> de l’objet et passez l’adresse d’un tableau de points à le <xref:System.Drawing.Graphics.DrawCurve%2A> (méthode).</span><span class="sxs-lookup"><span data-stu-id="b324f-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="b324f-105">Dessin d’une Spline cardinale en forme de cloche</span><span class="sxs-lookup"><span data-stu-id="b324f-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="b324f-106">L’exemple suivant dessine une spline cardinale en forme de cloche qui passe par cinq points définis.</span><span class="sxs-lookup"><span data-stu-id="b324f-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="b324f-107">L’illustration suivante montre la courbe et cinq points.</span><span class="sxs-lookup"><span data-stu-id="b324f-107">The following illustration shows the curve and five points.</span></span>  
  
     <span data-ttu-id="b324f-108">![Spline cardinale](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span><span class="sxs-lookup"><span data-stu-id="b324f-108">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="b324f-109">Dessiner une Spline cardinale fermée</span><span class="sxs-lookup"><span data-stu-id="b324f-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="b324f-110">Utilisez le <xref:System.Drawing.Graphics.DrawClosedCurve%2A> méthode de la <xref:System.Drawing.Graphics> classe pour dessiner une spline cardinale fermée.</span><span class="sxs-lookup"><span data-stu-id="b324f-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="b324f-111">Dans une spline cardinale fermée, la courbe se poursuit jusqu’au dernier point dans le tableau et se connecte avec le premier point dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="b324f-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="b324f-112">L’exemple suivant dessine une spline cardinale fermée qui passe par six points définis.</span><span class="sxs-lookup"><span data-stu-id="b324f-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="b324f-113">L’illustration suivante montre la spline fermée avec les six points.</span><span class="sxs-lookup"><span data-stu-id="b324f-113">The following illustration shows the closed spline along with the six points.</span></span>  
  
 <span data-ttu-id="b324f-114">![Spline cardinale](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span><span class="sxs-lookup"><span data-stu-id="b324f-114">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="b324f-115">Modification de la courbure d’une Spline cardinale</span><span class="sxs-lookup"><span data-stu-id="b324f-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="b324f-116">Modifier la courbure d’une spline cardinale en passant un argument de tension à le <xref:System.Drawing.Graphics.DrawCurve%2A> (méthode).</span><span class="sxs-lookup"><span data-stu-id="b324f-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="b324f-117">L’exemple suivant dessine trois splines cardinales qui passent par le même ensemble de points.</span><span class="sxs-lookup"><span data-stu-id="b324f-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="b324f-118">L’illustration suivante montre les trois splines avec leur valeur de tension.</span><span class="sxs-lookup"><span data-stu-id="b324f-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="b324f-119">Notez que lorsque la tension est 0, les points sont connectés par des lignes droites.</span><span class="sxs-lookup"><span data-stu-id="b324f-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 <span data-ttu-id="b324f-120">![Spline cardinale](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span><span class="sxs-lookup"><span data-stu-id="b324f-120">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b324f-121">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="b324f-121">Compiling the Code</span></span>  
 <span data-ttu-id="b324f-122">Les exemples précédents sont conçus pour une utilisation avec Windows Forms, et ils nécessitent <xref:System.Windows.Forms.PaintEventArgs> `e`, qui est un paramètre de la <xref:System.Windows.Forms.Control.Paint> Gestionnaire d’événements.</span><span class="sxs-lookup"><span data-stu-id="b324f-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b324f-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b324f-123">See Also</span></span>  
 [<span data-ttu-id="b324f-124">Lignes, courbes et formes</span><span class="sxs-lookup"><span data-stu-id="b324f-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="b324f-125">Génération et dessin de courbes</span><span class="sxs-lookup"><span data-stu-id="b324f-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)

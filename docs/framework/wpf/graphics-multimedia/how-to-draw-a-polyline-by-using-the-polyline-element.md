---
title: "Comment : dessiner une polyligne à l'aide de l'élément Polyline"
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 2abfa29f7aca4bfc8c5f91e36fd974093a98a9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Comment : dessiner une polyligne à l'aide de l'élément Polyline
Cet exemple montre comment dessiner une polyligne, c'est-à-dire une série de lignes connectées, à l’aide de la <xref:System.Windows.Shapes.Polyline> élément.  
  
 Pour dessiner une polyligne, créez un <xref:System.Windows.Shapes.Polyline> élément et utiliser ses <xref:System.Windows.Shapes.Polyline.Points%2A> propriété pour spécifier les sommets de forme. Enfin, utilisez la <xref:System.Windows.Shapes.Shape.Stroke%2A> et <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> montrer de propriétés pour décrire la polyligne car une ligne sans trait est invisible.  
  
> [!NOTE]
>  Étant donné que la <xref:System.Windows.Shapes.Polyline> élément n’est pas une forme fermée, la <xref:System.Windows.Shapes.Shape.Fill%2A> propriété n’a aucun effet, même si vous fermez délibérément le contour de la forme. Pour créer une forme fermée avec un <xref:System.Windows.Shapes.Shape.Fill%2A>, utilisez un <xref:System.Windows.Shapes.Polygon> élément.  
  
 L’exemple suivant dessine deux <xref:System.Windows.Shapes.Polyline> éléments à l’intérieur d’un <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Exemple  
 Dans [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], une syntaxe valide pour les points est une liste délimitée par l’espace de paires de séparées par des virgules coordonnées x et y.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Bien que cet exemple utilise un <xref:System.Windows.Controls.Canvas> pour contenir les polylignes, vous pouvez utiliser des éléments de type polyligne (et tous les autres éléments de forme) avec n’importe quelle <xref:System.Windows.Controls.Panel> ou <xref:System.Windows.Controls.Control> qui prend en charge le contenu non textuel.  
  
 Cet exemple fait partie d’un exemple plus complet ; Pour obtenir un exemple complet, consultez [éléments de forme, exemple](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Éléments de forme, exemple](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Vue d’ensemble des formes et dessins de base dans WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)

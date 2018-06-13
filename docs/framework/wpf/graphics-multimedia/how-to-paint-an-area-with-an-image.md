---
title: 'Comment : peindre une zone avec une image'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 4efecc3c8083396d4c06d86d9ece01bd584a1c6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560956"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Comment : peindre une zone avec une image
Cet exemple montre comment utiliser la <xref:System.Windows.Media.ImageBrush> classe pour peindre une zone avec une image. Un <xref:System.Windows.Media.ImageBrush> affiche une seule image, ce qui est spécifiée par son <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propriété.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant peint le <xref:System.Windows.Controls.Control.Background%2A> d’un bouton en utilisant un <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Par défaut, un <xref:System.Windows.Media.ImageBrush> étire son image pour remplir complètement la zone qui vous sont en train de peindre. Dans l’exemple précédent, l’image est étirée pour remplir le bouton, ce qui peut éventuellement déformer l’image. Vous pouvez contrôler ce comportement en définissant le <xref:System.Windows.Media.TileBrush.Stretch%2A> propriété du <xref:System.Windows.Media.TileBrush> à <xref:System.Windows.Media.Stretch.Uniform> ou <xref:System.Windows.Media.Stretch.UniformToFill>, ce qui entraîne le pinceau conserver les proportions de l’image.  
  
 Si vous définissez la <xref:System.Windows.Media.TileBrush.Viewport%2A> et <xref:System.Windows.Media.TileBrush.TileMode%2A> propriétés d’un <xref:System.Windows.Media.ImageBrush>, vous pouvez créer un modèle extensible. L’exemple suivant peint un bouton en utilisant un modèle créé à partir d’une image.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Pour plus d’informations sur la <xref:System.Windows.Media.ImageBrush> de classe, consultez [peinture avec des Images, des dessins et des éléments visuels](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Cet exemple de code fait partie d’un exemple plus complet fourni pour la <xref:System.Windows.Media.ImageBrush> classe. Pour obtenir un exemple complet, consultez [ImageBrush, exemple](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Voir aussi  
 [Peinture avec des images, des dessins et des objets visuels](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)

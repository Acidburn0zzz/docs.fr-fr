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
ms.openlocfilehash: 7f7cf24f7883553329de3761ff0670e8e3a09463
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151006"
---
# <a name="how-to-animate-a-rectangle"></a>Procédure : Animer un rectangle
Cet exemple montre comment animer les modifications apportées à la taille et à la position d’un rectangle.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise une instance de la <xref:System.Windows.Media.Animation.RectAnimation> classe pour animer la <xref:System.Windows.Media.RectangleGeometry.Rect%2A> propriété d’un <xref:System.Windows.Media.RectangleGeometry>, qui anime les modifications apportées à la taille et la position du rectangle.  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Windows.Media.Animation.RectAnimation>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.RectangleGeometry>
- [Vue d'ensemble de l'animation](animation-overview.md)
- [Graphiques et multimédia](index.md)
- [Rubriques "Comment" relatives aux graphiques](graphics-how-to-topics.md)
- [Rubriques "Comment" relatives à l'animation et au minutage](animation-and-timing-how-to-topics.md)

---
title: 'Comment : peindre une zone avec un dégradé linéaire'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: aee9931fc366131ae492891cc4d0fff70b4a4441
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779995"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Comment : peindre une zone avec un dégradé linéaire
Cet exemple montre comment utiliser le <xref:System.Windows.Media.LinearGradientBrush> classe pour peindre une zone avec un dégradé linéaire. Dans l’exemple suivant, le <xref:System.Windows.Shapes.Shape.Fill%2A> d’un <xref:System.Windows.Shapes.Rectangle> est peint avec un dégradé linéaire diagonal qui passe du jaune au rouge au bleu au citron vert.  
  
## <a name="example"></a>Exemple  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 L’illustration suivante montre le dégradé créé par l’exemple précédent.  
  
 ![Dégradé linéaire en diagonale](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Pour créer un dégradé linéaire horizontal, modifiez le <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> et <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> en (0,0.5) et (1,0.5). Dans l’exemple suivant, un <xref:System.Windows.Shapes.Rectangle> est peint avec un dégradé linéaire horizontal.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 L’illustration suivante montre le dégradé créé par l’exemple précédent.  
  
 ![Un dégradé linéaire horizontal](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Pour créer un dégradé linéaire vertical, modifiez le <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> et <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> en (0.5,0) et (0.5,1). Dans l’exemple suivant, un <xref:System.Windows.Shapes.Rectangle> est peint avec un dégradé linéaire vertical.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 L’illustration suivante montre le dégradé créé par l’exemple précédent.  
  
 ![Dégradé linéaire vertical](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  Les exemples de cette rubrique utilisent le système de coordonnées par défaut pour la définition des points de départ et points de terminaison. Le système de coordonnées par défaut est relative à une zone englobante : 0 indique 0 % de la zone englobante, et 1 indique 100 % de la zone englobante. Vous pouvez modifier ce système de coordonnées en définissant le <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valeur à la propriété <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>. Un système de coordonnées absolu n’est pas relatif à un rectangle englobant. Les valeurs sont interprétées directement dans l’espace local.  
  
 Pour obtenir des exemples supplémentaires, consultez [pinceaux, exemple](https://go.microsoft.com/fwlink/?LinkID=159973). Pour plus d’informations sur les dégradés et les autres types de pinceaux, consultez [peinture avec des couleurs unies et vue d’ensemble des dégradés](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).

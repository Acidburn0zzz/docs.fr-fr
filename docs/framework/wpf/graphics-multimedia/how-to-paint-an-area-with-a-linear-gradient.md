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
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="5e767-102">Comment : peindre une zone avec un dégradé linéaire</span><span class="sxs-lookup"><span data-stu-id="5e767-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="5e767-103">Cet exemple montre comment utiliser le <xref:System.Windows.Media.LinearGradientBrush> classe pour peindre une zone avec un dégradé linéaire.</span><span class="sxs-lookup"><span data-stu-id="5e767-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="5e767-104">Dans l’exemple suivant, le <xref:System.Windows.Shapes.Shape.Fill%2A> d’un <xref:System.Windows.Shapes.Rectangle> est peint avec un dégradé linéaire diagonal qui passe du jaune au rouge au bleu au citron vert.</span><span class="sxs-lookup"><span data-stu-id="5e767-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e767-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="5e767-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="5e767-106">L’illustration suivante montre le dégradé créé par l’exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="5e767-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5e767-107">![Dégradé linéaire en diagonale](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="5e767-107">![Diagonal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="5e767-108">Pour créer un dégradé linéaire horizontal, modifiez le <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> et <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> en (0,0.5) et (1,0.5).</span><span class="sxs-lookup"><span data-stu-id="5e767-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="5e767-109">Dans l’exemple suivant, un <xref:System.Windows.Shapes.Rectangle> est peint avec un dégradé linéaire horizontal.</span><span class="sxs-lookup"><span data-stu-id="5e767-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="5e767-110">L’illustration suivante montre le dégradé créé par l’exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="5e767-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5e767-111">![Un dégradé linéaire horizontal](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="5e767-111">![A horizontal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="5e767-112">Pour créer un dégradé linéaire vertical, modifiez le <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> et <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> de la <xref:System.Windows.Media.LinearGradientBrush> en (0.5,0) et (0.5,1).</span><span class="sxs-lookup"><span data-stu-id="5e767-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="5e767-113">Dans l’exemple suivant, un <xref:System.Windows.Shapes.Rectangle> est peint avec un dégradé linéaire vertical.</span><span class="sxs-lookup"><span data-stu-id="5e767-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="5e767-114">L’illustration suivante montre le dégradé créé par l’exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="5e767-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="5e767-115">![Dégradé linéaire vertical](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="5e767-115">![Vertical linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e767-116">Les exemples de cette rubrique utilisent le système de coordonnées par défaut pour la définition des points de départ et points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="5e767-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="5e767-117">Le système de coordonnées par défaut est relative à une zone englobante : 0 indique 0 % de la zone englobante, et 1 indique 100 % de la zone englobante.</span><span class="sxs-lookup"><span data-stu-id="5e767-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="5e767-118">Vous pouvez modifier ce système de coordonnées en définissant le <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valeur à la propriété <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5e767-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5e767-119">Un système de coordonnées absolu n’est pas relatif à un rectangle englobant.</span><span class="sxs-lookup"><span data-stu-id="5e767-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="5e767-120">Les valeurs sont interprétées directement dans l’espace local.</span><span class="sxs-lookup"><span data-stu-id="5e767-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="5e767-121">Pour obtenir des exemples supplémentaires, consultez [pinceaux, exemple](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="5e767-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="5e767-122">Pour plus d’informations sur les dégradés et les autres types de pinceaux, consultez [peinture avec des couleurs unies et vue d’ensemble des dégradés](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5e767-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>

---
title: 'Comment : peindre une zone avec un dégradé radial'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: d794f85ce4968e1cf1759df5358834f3b4cdfb50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560639"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="f0921-102">Comment : peindre une zone avec un dégradé radial</span><span class="sxs-lookup"><span data-stu-id="f0921-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="f0921-103">Cet exemple montre comment utiliser la <xref:System.Windows.Media.RadialGradientBrush> classe pour peindre une zone avec un dégradé radial.</span><span class="sxs-lookup"><span data-stu-id="f0921-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0921-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="f0921-104">Example</span></span>  
 <span data-ttu-id="f0921-105">L’exemple suivant utilise un <xref:System.Windows.Media.RadialGradientBrush> pour peindre un rectangle avec un dégradé radial qui passe du jaune au rouge au bleu au citron vert.</span><span class="sxs-lookup"><span data-stu-id="f0921-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="f0921-106">L’illustration suivante montre le dégradé de l’exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="f0921-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="f0921-107">Le nom du dégradé ont été mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="f0921-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="f0921-108">![Points de dégradé dans un dégradé radial](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="f0921-108">![Gradient stops in a radial gradient](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0921-109">Les exemples dans cette rubrique utilisent le système de coordonnées par défaut pour la définition de points de contrôle.</span><span class="sxs-lookup"><span data-stu-id="f0921-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="f0921-110">Le système de coordonnées par défaut est relative à une zone englobante : 0 indique 0 % de la zone englobante, et 1 indique 100 % de la zone englobante.</span><span class="sxs-lookup"><span data-stu-id="f0921-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="f0921-111">Vous pouvez modifier ce système de coordonnées en définissant le <xref:System.Windows.Media.GradientBrush.MappingMode%2A> valeur à la propriété <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="f0921-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="f0921-112">Un système de coordonnées absolu n’est pas relatif à un rectangle englobant.</span><span class="sxs-lookup"><span data-stu-id="f0921-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="f0921-113">Les valeurs sont interprétées directement dans l’espace local.</span><span class="sxs-lookup"><span data-stu-id="f0921-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="f0921-114">Pour plus <xref:System.Windows.Media.RadialGradientBrush> obtenir des exemples, consultez la [pinceaux, exemple](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="f0921-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="f0921-115">Pour plus d’informations sur les dégradés et les autres types de pinceaux, consultez [peinture avec des couleurs unies et vue d’ensemble des dégradés](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f0921-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>

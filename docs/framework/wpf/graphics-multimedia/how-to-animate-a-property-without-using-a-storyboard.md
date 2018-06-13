---
title: 'Comment : animer une propriété sans utiliser de storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: 18f8fb4edf5f71904335180e43dd65bd9910bdef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561012"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a><span data-ttu-id="d6382-102">Comment : animer une propriété sans utiliser de storyboard</span><span class="sxs-lookup"><span data-stu-id="d6382-102">How to: Animate a Property Without Using a Storyboard</span></span>
<span data-ttu-id="d6382-103">Cet exemple montre une manière d’appliquer une animation à une propriété sans utiliser un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="d6382-103">This example shows one way to apply an animation to a property without using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6382-104">La fonctionnalité n’est pas disponible en langage [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6382-104">This functionality is not available in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="d6382-105">Pour plus d’informations sur l’animation d’une propriété en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], consultez [Animer une propriété à l’aide d’un storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="d6382-105">For information about animating a property in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="d6382-106">Pour appliquer une animation locale à une propriété, utilisez le <xref:System.Windows.UIElement.BeginAnimation%2A> (méthode).</span><span class="sxs-lookup"><span data-stu-id="d6382-106">To apply a local animation to a property, use the <xref:System.Windows.UIElement.BeginAnimation%2A> method.</span></span> <span data-ttu-id="d6382-107">Cette méthode accepte deux paramètres : un <xref:System.Windows.DependencyProperty> qui spécifie la propriété à animer et l’animation à appliquer à cette propriété.</span><span class="sxs-lookup"><span data-stu-id="d6382-107">This method takes two parameters: a <xref:System.Windows.DependencyProperty> that specifies the property to animate, and the animation to apply to that property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6382-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="d6382-108">Example</span></span>  
 <span data-ttu-id="d6382-109">L’exemple suivant montre comment animer la couleur d’arrière-plan et de largeur d’un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="d6382-109">The following example shows how to animate the width and background color of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <span data-ttu-id="d6382-110">Diverses classes d’animation dans le <xref:System.Windows.Media.Animation> espace de noms existe pour animer les différents types de propriétés.</span><span class="sxs-lookup"><span data-stu-id="d6382-110">A variety of animation classes in the <xref:System.Windows.Media.Animation> namespace exist for animating different types of properties.</span></span> <span data-ttu-id="d6382-111">Pour plus d’informations sur l’animation de propriétés, consultez [Vue d’ensemble de l’animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6382-111">For more information about animating properties, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="d6382-112">Pour plus d’informations sur les propriétés de dépendance (le type de propriétés présentées dans ces exemples) et leurs fonctionnalités, consultez [Vue d’ensemble des propriétés de dépendance](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6382-112">For more information about dependency properties (the type of properties that are shown in these examples) and their features, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="d6382-113">Il existe autres façons d’animer sans utiliser <xref:System.Windows.Media.Animation.Storyboard> objets ; pour plus d’informations, consultez [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6382-113">There are other ways to animate without using <xref:System.Windows.Media.Animation.Storyboard> objects; for more information, see [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6382-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6382-114">See Also</span></span>  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>  
 <xref:System.Windows.Media.Animation>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="d6382-115">Vue d’ensemble des techniques d’animation de propriétés</span><span class="sxs-lookup"><span data-stu-id="d6382-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="d6382-116">Vue d’ensemble de l’animation</span><span class="sxs-lookup"><span data-stu-id="d6382-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)

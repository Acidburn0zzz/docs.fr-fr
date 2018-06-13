---
title: "Comment : animer une propriété à l'aide d'un AnimationClock"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: b8c64586d0dc5dc2e565fe4cb002e0f9cd4109af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558730"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="67855-102">Comment : animer une propriété à l'aide d'un AnimationClock</span><span class="sxs-lookup"><span data-stu-id="67855-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="67855-103">Cet exemple montre comment utiliser <xref:System.Windows.Media.Animation.Clock> objets pour animer une propriété.</span><span class="sxs-lookup"><span data-stu-id="67855-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="67855-104">Il existe trois façons d’animer une propriété de dépendance :</span><span class="sxs-lookup"><span data-stu-id="67855-104">There are three ways to animate a dependency property:</span></span>  
  
-   <span data-ttu-id="67855-105">Créer un <xref:System.Windows.Media.Animation.AnimationTimeline> et l’associer à cette propriété en utilisant un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="67855-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
-   <span data-ttu-id="67855-106">Utilisez l’objet <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> pour appliquer une seule méthode <xref:System.Windows.Media.Animation.AnimationTimeline> à une propriété cible.</span><span class="sxs-lookup"><span data-stu-id="67855-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
-   <span data-ttu-id="67855-107">Créer un <xref:System.Windows.Media.Animation.AnimationClock> d’un <xref:System.Windows.Media.Animation.AnimationTimeline> et appliquez-le à une propriété.</span><span class="sxs-lookup"><span data-stu-id="67855-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="67855-108"><xref:System.Windows.Media.Animation.Storyboard> objets et la <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> méthode permettent d’animer des propriétés sans créer et distribuer des horloges directement (pour obtenir des exemples, consultez [animer une propriété à l’aide d’un Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) et [animer une propriété sans À l’aide d’un Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)) ; horloges sont créés et distribués automatiquement pour vous.</span><span class="sxs-lookup"><span data-stu-id="67855-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67855-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="67855-109">Example</span></span>  
 <span data-ttu-id="67855-110">L’exemple suivant montre comment créer un <xref:System.Windows.Media.Animation.AnimationClock> et l’appliquer à deux propriétés similaires.</span><span class="sxs-lookup"><span data-stu-id="67855-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="67855-111">Pour obtenir un exemple montrant comment contrôler de façon interactive une <xref:System.Windows.Media.Animation.Clock> après son démarrage, consultez [contrôler de façon interactive une horloge au format](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span><span class="sxs-lookup"><span data-stu-id="67855-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67855-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67855-112">See Also</span></span>  
 [<span data-ttu-id="67855-113">Animer une propriété à l’aide d’une table de montage séquentiel</span><span class="sxs-lookup"><span data-stu-id="67855-113">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="67855-114">Animer une propriété sans utiliser de storyboard</span><span class="sxs-lookup"><span data-stu-id="67855-114">Animate a Property Without Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [<span data-ttu-id="67855-115">Vue d’ensemble des techniques d’animation de propriétés</span><span class="sxs-lookup"><span data-stu-id="67855-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)

---
title: "Comment : contrôler le minutage d'une animation d'image clé"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: d65bf6f7643adf1d98d468853ae8017a4a6554ac
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43892676"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="95c6d-102">Comment : contrôler le minutage d'une animation d'image clé</span><span class="sxs-lookup"><span data-stu-id="95c6d-102">How to: Control Key-Frame Animation Timing</span></span>
<span data-ttu-id="95c6d-103">Cet exemple montre comment contrôler le minutage des images clés d’une animation d’image clé.</span><span class="sxs-lookup"><span data-stu-id="95c6d-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="95c6d-104">Comme les autres animations, les animations d’image clé ont une <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="95c6d-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="95c6d-105">En plus de spécifier la durée d’une animation, vous devez spécifier quelle partie de cette durée est alloué à chacun de ses images clés.</span><span class="sxs-lookup"><span data-stu-id="95c6d-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="95c6d-106">Pour allouer du temps, vous spécifiez un <xref:System.Windows.Media.Animation.KeyTime> pour chaque image clé de l’animation.</span><span class="sxs-lookup"><span data-stu-id="95c6d-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>  
  
 <span data-ttu-id="95c6d-107">Le <xref:System.Windows.Media.Animation.KeyTime> pour chaque image clé spécifie la fin d’une image clé (il ne spécifie pas la durée de lecture d’une image clé).</span><span class="sxs-lookup"><span data-stu-id="95c6d-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="95c6d-108">Vous pouvez spécifier un <xref:System.Windows.Media.Animation.KeyTime> comme un <xref:System.TimeSpan> valeur sous forme de pourcentage ou en tant que le <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ou <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valeur spéciale.</span><span class="sxs-lookup"><span data-stu-id="95c6d-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95c6d-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="95c6d-109">Example</span></span>  
 <span data-ttu-id="95c6d-110">L’exemple suivant utilise un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> pour animer un rectangle sur l’écran.</span><span class="sxs-lookup"><span data-stu-id="95c6d-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="95c6d-111">Temps clés des images clés sont définies avec <xref:System.TimeSpan> valeurs.</span><span class="sxs-lookup"><span data-stu-id="95c6d-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 <span data-ttu-id="95c6d-112">L’illustration suivante montre les lorsque la valeur de chaque image clé est atteinte.</span><span class="sxs-lookup"><span data-stu-id="95c6d-112">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="95c6d-113">![Valeurs de clés atteintes à 3, 4 et 10 secondes](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="95c6d-113">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>  
  
 <span data-ttu-id="95c6d-114">L’exemple suivant illustre une animation qui est identique, sauf que les temps clés des images clés sont définies avec les valeurs de pourcentage.</span><span class="sxs-lookup"><span data-stu-id="95c6d-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 <span data-ttu-id="95c6d-115">L’illustration suivante montre les lorsque la valeur de chaque image clé est atteinte.</span><span class="sxs-lookup"><span data-stu-id="95c6d-115">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="95c6d-116">![Valeurs de clés atteintes à 3, 4 et 10 secondes](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="95c6d-116">![Key values are reached at 3, 4, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>  
  
 <span data-ttu-id="95c6d-117">L’exemple suivant utilise <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> valeurs de temps clé.</span><span class="sxs-lookup"><span data-stu-id="95c6d-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 <span data-ttu-id="95c6d-118">L’illustration suivante montre les lorsque la valeur de chaque image clé est atteinte.</span><span class="sxs-lookup"><span data-stu-id="95c6d-118">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="95c6d-119">![Valeurs de clés atteintes à 3,3, 6,6 et 9,9 secondes](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="95c6d-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>  
  
 <span data-ttu-id="95c6d-120">Le dernier exemple utilise <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valeurs de temps clé.</span><span class="sxs-lookup"><span data-stu-id="95c6d-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 <span data-ttu-id="95c6d-121">L’illustration suivante montre les lorsque la valeur de chaque image clé est atteinte.</span><span class="sxs-lookup"><span data-stu-id="95c6d-121">The following illustration shows when the value of each key frame is reached.</span></span>  
  
 <span data-ttu-id="95c6d-122">![Valeurs de clés atteintes à 0, 5 et 10 secondes](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="95c6d-122">![Key values are reached at 0, 5, and 10 seconds](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>  
  
 <span data-ttu-id="95c6d-123">Par souci de simplicité, les versions de code de cet exemple utilisent des animations locales, pas storyboards, car une seule animation est appliquée à une propriété unique, mais les exemples peuvent être modifiés pour utiliser des tables de montage séquentiel à la place.</span><span class="sxs-lookup"><span data-stu-id="95c6d-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="95c6d-124">Pour obtenir un exemple montrant comment déclarer un storyboard dans le code, consultez [animer une propriété à l’aide d’un Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="95c6d-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="95c6d-125">Pour l’exemple complet, consultez la page [Animation d’image clé, exemple](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="95c6d-125">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="95c6d-126">Pour plus d’informations sur les animations d’image clé, consultez le [vue d’ensemble des Animations image clé](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="95c6d-126">For more information about key frame animations, see the [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c6d-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95c6d-127">See Also</span></span>  
 [<span data-ttu-id="95c6d-128">Vue d'ensemble des animations d'image clé</span><span class="sxs-lookup"><span data-stu-id="95c6d-128">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="95c6d-129">Vue d’ensemble de l’animation</span><span class="sxs-lookup"><span data-stu-id="95c6d-129">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="95c6d-130">Rubriques de guide pratique</span><span class="sxs-lookup"><span data-stu-id="95c6d-130">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)

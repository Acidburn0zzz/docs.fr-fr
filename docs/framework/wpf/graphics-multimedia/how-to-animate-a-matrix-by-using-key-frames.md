---
title: "Comment : animer une matrice à l'aide d'images clés"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: edb7074dffab23810872f4347f5339270af86bd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557015"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="0dcb2-102">Comment : animer une matrice à l'aide d'images clés</span><span class="sxs-lookup"><span data-stu-id="0dcb2-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="0dcb2-103">Cet exemple montre comment animer la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propriété d’un <xref:System.Windows.Media.MatrixTransform> à l’aide d’images clés.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0dcb2-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="0dcb2-104">Example</span></span>  
 <span data-ttu-id="0dcb2-105">L’exemple suivant utilise le <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe pour animer la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propriété d’un <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="0dcb2-106">L’exemple utilise le <xref:System.Windows.Media.MatrixTransform> objet à transformer l’apparence et la position d’un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="0dcb2-107">Cette animation utilise la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> classe pour créer deux images clés et effectue les opérations suivantes avec eux :</span><span class="sxs-lookup"><span data-stu-id="0dcb2-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="0dcb2-108">Réalise une animation de la première <xref:System.Windows.Media.Matrix> pendant les premières secondes 0,2.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="0dcb2-109">L’exemple modifie la <xref:System.Windows.Media.Matrix.M11%2A> et <xref:System.Windows.Media.Matrix.M12%2A> propriétés de la <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="0dcb2-110">Cette modification, le bouton Étirer et être faussées.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="0dcb2-111">L’exemple modifie également le <xref:System.Windows.Media.Matrix.OffsetX%2A> et <xref:System.Windows.Media.Matrix.OffsetY%2A> propriétés afin que le bouton change de position.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="0dcb2-112">Anime la deuxième <xref:System.Windows.Media.Matrix> à 1 seconde.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="0dcb2-113">Le bouton se déplace vers un autre alors que le bouton n’est plus incliné ni étiré.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="0dcb2-114">Répète l’animation indéfiniment.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0dcb2-115">Images clés qui dérivent de la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> soudains entre les valeurs de création d’objet, le déplacement de l’animation est saccadé.</span><span class="sxs-lookup"><span data-stu-id="0dcb2-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="0dcb2-116">Pour l’exemple complet, consultez la page [Animation d’image clé, exemple](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="0dcb2-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dcb2-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0dcb2-117">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [<span data-ttu-id="0dcb2-118">Vue d'ensemble des animations d'image clé</span><span class="sxs-lookup"><span data-stu-id="0dcb2-118">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="0dcb2-119">Guides pratiques relatifs aux images clés</span><span class="sxs-lookup"><span data-stu-id="0dcb2-119">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)

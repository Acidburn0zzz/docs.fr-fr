---
title: 'Comment : améliorer les performances de rendu en mettant en cache un élément'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: a92909c623db0c10e3434677b4275fa82b787fa7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559296"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="98c01-102">Comment : améliorer les performances de rendu en mettant en cache un élément</span><span class="sxs-lookup"><span data-stu-id="98c01-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="98c01-103">Utilisez le <xref:System.Windows.Media.BitmapCache> classe pour améliorer les performances de rendu d’un type complexe <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="98c01-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="98c01-104">Pour mettre en cache un élément, créer une nouvelle instance de la <xref:System.Windows.Media.BitmapCache> de classe et l’affecter à l’élément <xref:System.Windows.UIElement.CacheMode%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="98c01-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="98c01-105">Vous pouvez réutiliser un <xref:System.Windows.Media.BitmapCache> efficacement dans un <xref:System.Windows.Media.BitmapCacheBrush>.</span><span class="sxs-lookup"><span data-stu-id="98c01-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98c01-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="98c01-106">Example</span></span>  
 <span data-ttu-id="98c01-107">L’exemple de code suivant montre comment créer un élément complexe et de mettre en cache sous forme de bitmap, ce qui améliore les performances lors de l’élément est animé.</span><span class="sxs-lookup"><span data-stu-id="98c01-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="98c01-108">L’élément est une zone qui contient les géométries de forme avec un grand nombre de sommets.</span><span class="sxs-lookup"><span data-stu-id="98c01-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="98c01-109">A <xref:System.Windows.Media.BitmapCache> avec la valeur par défaut des valeurs est attribué à la <xref:System.Windows.UIElement.CacheMode%2A> de la zone de dessin, et une animation montre l’évolution en douceur de l’image bitmap mise en cache.</span><span class="sxs-lookup"><span data-stu-id="98c01-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="98c01-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98c01-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="98c01-111">Guide pratique pour utiliser un élément mis en cache comme pinceau</span><span class="sxs-lookup"><span data-stu-id="98c01-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)

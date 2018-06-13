---
title: "Comment : définir les propriétés Width d'un élément"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 72617744a8b2565857d19a1c6ef41bf4211c89ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554833"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="e7fcd-102">Comment : définir les propriétés Width d'un élément</span><span class="sxs-lookup"><span data-stu-id="e7fcd-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="e7fcd-103">Exemple</span><span class="sxs-lookup"><span data-stu-id="e7fcd-103">Example</span></span>  
 <span data-ttu-id="e7fcd-104">Cet exemple montre visuellement les différences de comportement entre les quatre propriétés associées à la largeur de rendu [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7fcd-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="e7fcd-105">La <xref:System.Windows.FrameworkElement> classe expose quatre propriétés qui décrivent les caractéristiques de la largeur d’un élément.</span><span class="sxs-lookup"><span data-stu-id="e7fcd-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="e7fcd-106">Ces quatre propriétés peuvent entrer en conflit, et dans ce cas, la valeur est prioritaire est déterminée comme suit : le <xref:System.Windows.FrameworkElement.MinWidth%2A> valeur est prioritaire sur la <xref:System.Windows.FrameworkElement.MaxWidth%2A> valeur, qui à son tour est prioritaire sur la <xref:System.Windows.FrameworkElement.Width%2A> valeur.</span><span class="sxs-lookup"><span data-stu-id="e7fcd-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="e7fcd-107">Une quatrième propriété, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, est en lecture seule et la largeur réelle déterminée par les interactions avec le processus de mise en page des rapports.</span><span class="sxs-lookup"><span data-stu-id="e7fcd-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="e7fcd-108">Les éléments suivants [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] exemples dessinent un <xref:System.Windows.Shapes.Rectangle> élément (`rect1`) en tant qu’enfant de <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="e7fcd-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e7fcd-109">Vous pouvez modifier les propriétés de la largeur d’un <xref:System.Windows.Shapes.Rectangle> à l’aide d’une série de <xref:System.Windows.Controls.ListBox> éléments qui représentent les valeurs de propriété <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, et <xref:System.Windows.FrameworkElement.Width%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7fcd-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="e7fcd-110">De cette manière, la priorité de chaque propriété est affichée visuellement.</span><span class="sxs-lookup"><span data-stu-id="e7fcd-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="e7fcd-111">Les exemples de code-behind suivants gèrent les événements qui le <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> déclenche des événements.</span><span class="sxs-lookup"><span data-stu-id="e7fcd-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="e7fcd-112">Chaque méthode personnalisée extrait l’entrée de la <xref:System.Windows.Controls.ListBox>, analyse la valeur en tant qu’un <xref:System.Double>et applique la valeur à la propriété associées à la largeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e7fcd-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="e7fcd-113">Les valeurs de largeur sont également converties en une chaîne et écrites dans différents <xref:System.Windows.Controls.TextBlock> éléments (définition de ces éléments n’est pas affichée dans le XAML sélectionné).</span><span class="sxs-lookup"><span data-stu-id="e7fcd-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="e7fcd-114">Pour obtenir un exemple complet, consultez [propriétés Width, exemple de comparaison](http://go.microsoft.com/fwlink/?LinkID=160050).</span><span class="sxs-lookup"><span data-stu-id="e7fcd-114">For the complete sample, see [Width Properties Comparison Sample](http://go.microsoft.com/fwlink/?LinkID=160050).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7fcd-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7fcd-115">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>  
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 [<span data-ttu-id="e7fcd-116">Vue d’ensemble de Panel</span><span class="sxs-lookup"><span data-stu-id="e7fcd-116">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="e7fcd-117">Définir les propriétés Height d’un élément</span><span class="sxs-lookup"><span data-stu-id="e7fcd-117">Set the Height Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)  
 [<span data-ttu-id="e7fcd-118">Comparaison des propriétés Width, exemple</span><span class="sxs-lookup"><span data-stu-id="e7fcd-118">Width Properties Comparison Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160050)

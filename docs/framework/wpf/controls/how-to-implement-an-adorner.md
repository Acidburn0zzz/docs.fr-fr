---
title: 'Comment : implémenter un ornement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: f5b0ed080a413546a3b985055858e209f9f347eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552963"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="84074-102">Comment : implémenter un ornement</span><span class="sxs-lookup"><span data-stu-id="84074-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="84074-103">Cet exemple montre une implémentation d’ornement minimale.</span><span class="sxs-lookup"><span data-stu-id="84074-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="84074-104">Notes pour les implémenteurs</span><span class="sxs-lookup"><span data-stu-id="84074-104">Notes for Implementers</span></span>  
 <span data-ttu-id="84074-105">Il est important de noter que les ornements n’incluent aucun comportement de rendu inhérent ; il appartient donc à l’implémenteur d’un ornement de vérifier son rendu.</span><span class="sxs-lookup"><span data-stu-id="84074-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="84074-106">Une méthode courante de l’implémentation du comportement de rendu consiste à remplacer le <xref:System.Windows.UIElement.OnRender%2A> méthode et l’utilisation d’un ou plusieurs <xref:System.Windows.Media.DrawingContext> objets pour restituer les visuels de l’ornement en fonction des besoins (comme indiqué dans cet exemple).</span><span class="sxs-lookup"><span data-stu-id="84074-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="84074-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="84074-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="84074-108">Description</span><span class="sxs-lookup"><span data-stu-id="84074-108">Description</span></span>  
 <span data-ttu-id="84074-109">Un ornement personnalisé est créé en implémentant une classe qui hérite de l’abstraite <xref:System.Windows.Documents.Adorner> classe.</span><span class="sxs-lookup"><span data-stu-id="84074-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="84074-110">L’ornement d’exemple orne simplement les angles d’un <xref:System.Windows.UIElement> avec des cercles en substituant la <xref:System.Windows.UIElement.OnRender%2A> (méthode).</span><span class="sxs-lookup"><span data-stu-id="84074-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="84074-111">Code</span><span class="sxs-lookup"><span data-stu-id="84074-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="84074-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84074-112">See Also</span></span>  
 [<span data-ttu-id="84074-113">Vue d’ensemble des ornements</span><span class="sxs-lookup"><span data-stu-id="84074-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)

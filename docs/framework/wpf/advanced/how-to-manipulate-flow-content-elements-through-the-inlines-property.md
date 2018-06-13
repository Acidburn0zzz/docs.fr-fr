---
title: 'Comment : manipuler des éléments de contenu de flux avec la propriété Inlines'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: 3bbeac2eda8811939be3c710a8ce28349e7f0759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545569"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="40af1-102">Comment : manipuler des éléments de contenu de flux avec la propriété Inlines</span><span class="sxs-lookup"><span data-stu-id="40af1-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="40af1-103">Ces exemples montrent quelques-unes des opérations plus courantes qui peuvent être effectuées sur les éléments de contenu de flux inline (et conteneurs de tels éléments, tels que <xref:System.Windows.Controls.TextBlock>) via le **incorporations** propriété.</span><span class="sxs-lookup"><span data-stu-id="40af1-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="40af1-104">Cette propriété est utilisée pour ajouter et supprimer des éléments de <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="40af1-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="40af1-105">Éléments de contenu flux cette fonctionnalité une **incorporations** propriété incluent :</span><span class="sxs-lookup"><span data-stu-id="40af1-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="40af1-106">Il arrive que ces exemples utilisent <xref:System.Windows.Documents.Span> en tant que flux de l’élément de contenu, mais ces techniques sont applicables à tous les éléments ou les contrôles qui hébergent une <xref:System.Windows.Documents.InlineCollection> collection.</span><span class="sxs-lookup"><span data-stu-id="40af1-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40af1-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="40af1-107">Example</span></span>  
 <span data-ttu-id="40af1-108">L’exemple suivant crée un nouveau <xref:System.Windows.Documents.Span> objet, puis utilise le **ajouter** méthode pour ajouter du texte deux s’exécute en tant que contenu enfant de le <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="40af1-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="40af1-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="40af1-109">Example</span></span>  
 <span data-ttu-id="40af1-110">L’exemple suivant crée un nouveau <xref:System.Windows.Documents.Run> élément et l’insère au début de la <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="40af1-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="40af1-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="40af1-111">Example</span></span>  
 <span data-ttu-id="40af1-112">L’exemple suivant obtient le nombre de niveau supérieur <xref:System.Windows.Documents.Inline> éléments contenus dans le <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="40af1-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="40af1-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="40af1-113">Example</span></span>  
 <span data-ttu-id="40af1-114">L’exemple suivant supprime le dernier <xref:System.Windows.Documents.Inline> élément dans le <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="40af1-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="40af1-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="40af1-115">Example</span></span>  
 <span data-ttu-id="40af1-116">L’exemple suivant efface tout le contenu (<xref:System.Windows.Documents.Inline> éléments) à partir de la <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="40af1-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="40af1-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40af1-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="40af1-118">Vue d’ensemble des documents dynamiques</span><span class="sxs-lookup"><span data-stu-id="40af1-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="40af1-119">Manipuler un FlowDocument avec la propriété Blocks</span><span class="sxs-lookup"><span data-stu-id="40af1-119">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="40af1-120">Manipuler les colonnes d’un tableau avec la propriété Columns</span><span class="sxs-lookup"><span data-stu-id="40af1-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="40af1-121">Manipuler les groupes de lignes d’un tableau avec la propriété RowGroups</span><span class="sxs-lookup"><span data-stu-id="40af1-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)

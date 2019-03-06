---
title: 'Procédure : Définir une table avec XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 7398af6fddae56238e1af3ee4e726420c01ab7ea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376921"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="afdc4-102">Procédure : Définir une table avec XAML</span><span class="sxs-lookup"><span data-stu-id="afdc4-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="afdc4-103">L’exemple suivant montre comment définir un <xref:System.Windows.Documents.Table> à l’aide de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afdc4-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="afdc4-104">L’exemple de table a quatre colonnes (représentées par <xref:System.Windows.Documents.TableColumn> éléments) et plusieurs lignes (représentées par <xref:System.Windows.Documents.TableRow> éléments) contenant des données ainsi que le titre, en-tête et informations de pied de page.</span><span class="sxs-lookup"><span data-stu-id="afdc4-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="afdc4-105">Lignes doivent être contenues dans un <xref:System.Windows.Documents.TableRowGroup> élément.</span><span class="sxs-lookup"><span data-stu-id="afdc4-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="afdc4-106">Chaque ligne dans la table est composée d’une ou plusieurs cellules (représentées par <xref:System.Windows.Documents.TableCell> éléments).</span><span class="sxs-lookup"><span data-stu-id="afdc4-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="afdc4-107">Contenu dans une cellule de tableau doit être contenu dans un <xref:System.Windows.Documents.Block> élément ; dans ce cas <xref:System.Windows.Documents.Paragraph> éléments sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="afdc4-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="afdc4-108">La table héberge également un lien hypertexte (représenté par la <xref:System.Windows.Documents.Hyperlink> élément) dans la ligne de pied de page.</span><span class="sxs-lookup"><span data-stu-id="afdc4-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afdc4-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="afdc4-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="afdc4-110">La figure suivante illustre le rendu de la table définie dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="afdc4-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="afdc4-111">![Table affichée.](./media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="afdc4-111">![Rendered table.](./media/tableeg.png "TableEG")</span></span>

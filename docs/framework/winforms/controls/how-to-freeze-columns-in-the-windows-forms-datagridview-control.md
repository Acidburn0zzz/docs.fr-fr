---
title: 'Comment : figer les colonnes du contrôle DataGridView Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: 6eb6fab4b147365221ba79a682c4eaf744d24b25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532667"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="31afb-102">Comment : figer les colonnes du contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31afb-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="31afb-103">Quand des utilisateurs consultent des données affichées dans un contrôle Windows Forms <xref:System.Windows.Forms.DataGridView>, ils doivent parfois faire fréquemment référence à une même colonne ou un même ensemble de colonnes.</span><span class="sxs-lookup"><span data-stu-id="31afb-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="31afb-104">Par exemple, lors de l'affichage d'un tableau d'informations sur des clients qui contient de nombreuses colonnes, il est utile d'afficher le nom du client en permanence tout en laissant d'autres colonnes défiler à l'extérieur de la zone visible.</span><span class="sxs-lookup"><span data-stu-id="31afb-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="31afb-105">Pour obtenir ce comportement, vous pouvez figer des colonnes dans le contrôle.</span><span class="sxs-lookup"><span data-stu-id="31afb-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="31afb-106">Quand vous figez une colonne, toutes les colonnes à sa gauche (ou à sa droite dans les scripts de droite à gauche) sont aussi figées.</span><span class="sxs-lookup"><span data-stu-id="31afb-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="31afb-107">Les colonnes figées restent en place, tandis que toutes les autres colonnes peuvent défiler.</span><span class="sxs-lookup"><span data-stu-id="31afb-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31afb-108">Si la réorganisation des colonnes est activée, les colonnes figées sont traitées comme un groupe distinct des colonnes non figées.</span><span class="sxs-lookup"><span data-stu-id="31afb-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="31afb-109">Les utilisateurs peuvent repositionner des colonnes dans l'un ou l'autre groupe, mais ils ne peuvent pas déplacer une colonne d'un groupe à l'autre.</span><span class="sxs-lookup"><span data-stu-id="31afb-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="31afb-110">La propriété <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> d'une colonne détermine si la colonne est toujours visible dans la grille.</span><span class="sxs-lookup"><span data-stu-id="31afb-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="31afb-111">Cette tâche est prise en charge dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31afb-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="31afb-112">Consultez également [Comment : figer les colonnes dans les Windows Forms DataGridView contrôle à l’aide du concepteur](http://msdn.microsoft.com/library/717ss6s6\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="31afb-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/717ss6s6\(v=vs.110\)).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="31afb-113">Pour figer une colonne par programmation</span><span class="sxs-lookup"><span data-stu-id="31afb-113">To freeze a column programmatically</span></span>  
  
-   <span data-ttu-id="31afb-114">Affectez à la propriété <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> la valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="31afb-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31afb-115">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="31afb-115">Compiling the Code</span></span>  
 <span data-ttu-id="31afb-116">Cet exemple nécessite :</span><span class="sxs-lookup"><span data-stu-id="31afb-116">This example requires:</span></span>  
  
-   <span data-ttu-id="31afb-117">un contrôle <xref:System.Windows.Forms.DataGridView> nommé `dataGridView1` qui contient une colonne nommée `AddToCartButton` ;</span><span class="sxs-lookup"><span data-stu-id="31afb-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
-   <span data-ttu-id="31afb-118">des références aux assemblys <xref:System?displayProperty=nameWithType> et <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31afb-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31afb-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31afb-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="31afb-120">Fonctionnalités de base liées aux colonnes, lignes et cellules dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31afb-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="31afb-121">Guide pratique pour activer la réorganisation des colonnes du contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31afb-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)

---
title: 'Comment : modifier les styles de bordures et de quadrillage dans le contrôle DataGridView Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: 94e5ae11d7fb2b67e028f368183246f8d8543a08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528747"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d1041-102">Comment : modifier les styles de bordures et de quadrillage dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1041-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d1041-103">Avec la <xref:System.Windows.Forms.DataGridView> (contrôle), vous pouvez personnaliser l’apparence de bordure du contrôle et des quadrillages pour améliorer l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d1041-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="d1041-104">Vous pouvez modifier la couleur du quadrillage principal et le style de bordure de contrôle en plus des styles de bordure des cellules dans le contrôle.</span><span class="sxs-lookup"><span data-stu-id="d1041-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="d1041-105">Vous pouvez également appliquer des styles de bordure de cellule différentes pour les cellules ordinaires, les cellules d’en-tête de ligne et les cellules d’en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="d1041-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1041-106">La couleur du quadrillage est utilisée uniquement avec les <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, et <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> les valeurs de la <xref:System.Windows.Forms.DataGridViewCellBorderStyle> énumération et la <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> valeur de la <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> énumération.</span><span class="sxs-lookup"><span data-stu-id="d1041-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="d1041-107">Les autres valeurs de ces énumérations utilisent des couleurs spécifiées par le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="d1041-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="d1041-108">En outre, lorsque les styles visuels sont activés sur Windows XP et la famille Windows Server 2003 via la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> (méthode), la <xref:System.Windows.Forms.DataGridView.GridColor%2A> valeur de propriété n’est pas utilisée.</span><span class="sxs-lookup"><span data-stu-id="d1041-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="d1041-109">Pour modifier la couleur du quadrillage par programmation</span><span class="sxs-lookup"><span data-stu-id="d1041-109">To change the gridline color programmatically</span></span>  
  
-   <span data-ttu-id="d1041-110">Définissez la propriété <xref:System.Windows.Forms.DataGridView.GridColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1041-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="d1041-111">Pour modifier le style de bordure du contrôle DataGridView entier par programmation</span><span class="sxs-lookup"><span data-stu-id="d1041-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
-   <span data-ttu-id="d1041-112">Affectez l'une des valeurs de l'énumération <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> à la propriété <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="d1041-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="d1041-113">Pour modifier par programme des styles de bordure des cellules DataGridView</span><span class="sxs-lookup"><span data-stu-id="d1041-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
-   <span data-ttu-id="d1041-114">Définir le <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, et <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> propriétés.</span><span class="sxs-lookup"><span data-stu-id="d1041-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="d1041-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="d1041-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d1041-116">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="d1041-116">Compiling the Code</span></span>  
 <span data-ttu-id="d1041-117">Cet exemple nécessite :</span><span class="sxs-lookup"><span data-stu-id="d1041-117">This example requires:</span></span>  
  
-   <span data-ttu-id="d1041-118">un contrôle <xref:System.Windows.Forms.DataGridView> nommé `dataGridView1` ;</span><span class="sxs-lookup"><span data-stu-id="d1041-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="d1041-119">des références aux assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> et <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d1041-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1041-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1041-120">See Also</span></span>  
 <xref:System.Windows.Forms.BorderStyle>  
 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellBorderStyle>  
 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>  
 [<span data-ttu-id="d1041-121">Mises en forme et styles de base dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1041-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)

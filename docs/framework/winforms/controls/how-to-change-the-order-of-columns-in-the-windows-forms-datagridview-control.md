---
title: "Comment : modifier l'ordre des colonnes dans le contrôle DataGridView Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 75362a2623cfe685f38259b9e581b593b2bd8d17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530612"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d72f5-102">Comment : modifier l'ordre des colonnes dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d72f5-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d72f5-103">Quand vous utilisez un <xref:System.Windows.Forms.DataGridView> pour afficher des données à partir d'une source de données, les colonnes du schéma de la source de données apparaissent parfois dans un ordre différent de celui souhaité.</span><span class="sxs-lookup"><span data-stu-id="d72f5-103">When you use a <xref:System.Windows.Forms.DataGridView> to display data from a data source, the columns in the data source's schema sometimes do not appear in the order you would like to display them.</span></span> <span data-ttu-id="d72f5-104">Vous pouvez modifier l'ordre des colonnes à l'aide de la propriété <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> de la classe <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="d72f5-104">You can change the displayed order of the columns by using the <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> property of the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <span data-ttu-id="d72f5-105">L’exemple de code suivant repositionne quelques-unes des colonnes générées automatiquement lors de la liaison à la table Customers dans l’exemple de base de données Northwind.</span><span class="sxs-lookup"><span data-stu-id="d72f5-105">The following code example repositions some of the columns automatically generated when binding to the Customers table in the Northwind sample database.</span></span> <span data-ttu-id="d72f5-106">Pour plus d’informations sur la façon de lier le <xref:System.Windows.Forms.DataGridView> le contrôle à une table de base de données, consultez [Comment : lier des données au contrôle DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d72f5-106">For more information about how to bind the <xref:System.Windows.Forms.DataGridView> control to a database table, see [How to: Bind Data to the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="d72f5-107">Cette tâche est prise en charge dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d72f5-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="d72f5-108">Consultez également [Comment : modifier l’ordre des colonnes dans les Windows Forms DataGridView contrôle à l’aide du Concepteur](http://msdn.microsoft.com/library/hb1dk7ax\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="d72f5-108">Also see [How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/hb1dk7ax\(v=vs.110\))</span></span>  
  
## <a name="example"></a><span data-ttu-id="d72f5-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="d72f5-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d72f5-110">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="d72f5-110">Compiling the Code</span></span>  
 <span data-ttu-id="d72f5-111">Cet exemple nécessite :</span><span class="sxs-lookup"><span data-stu-id="d72f5-111">This example requires:</span></span>  
  
-   <span data-ttu-id="d72f5-112">un contrôle <xref:System.Windows.Forms.DataGridView> nommé `customersDataGridView` qui est lié à une table avec les noms de colonnes indiqués, comme la table `Customers` dans la base de données Northwind ;</span><span class="sxs-lookup"><span data-stu-id="d72f5-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView` that is bound to a table with the indicated column names, such as the `Customers` table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="d72f5-113">des références aux assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> et <xref:System.Xml?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d72f5-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72f5-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d72f5-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d72f5-115">Affichage des données dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d72f5-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d72f5-116">Guide pratique pour lier des données au contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d72f5-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)

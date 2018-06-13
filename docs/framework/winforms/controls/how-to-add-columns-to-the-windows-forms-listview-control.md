---
title: 'Comment : ajouter des colonnes au contrôle ListView Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 4c284e9d2798a1992e3152a85eca47c8d33bfde8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528277"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="d3a99-102">Comment : ajouter des colonnes au contrôle ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3a99-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="d3a99-103">Dans la vue Détails, le <xref:System.Windows.Forms.ListView> contrôle peut afficher plusieurs colonnes pour chaque élément de liste.</span><span class="sxs-lookup"><span data-stu-id="d3a99-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="d3a99-104">Vous pouvez utiliser les colonnes à afficher à l’utilisateur plusieurs types d’informations sur chaque élément de liste.</span><span class="sxs-lookup"><span data-stu-id="d3a99-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="d3a99-105">Par exemple, une liste de fichiers peut afficher le nom de fichier, type de fichier, taille et date de que dernière modification du fichier.</span><span class="sxs-lookup"><span data-stu-id="d3a99-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="d3a99-106">Pour plus d’informations sur le remplissage des colonnes après leur création, consultez [Comment : afficher des sous-éléments en colonnes avec le contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d3a99-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="d3a99-107">Pour ajouter des colonnes par programme</span><span class="sxs-lookup"><span data-stu-id="d3a99-107">To add columns programmatically</span></span>  
  
1.  <span data-ttu-id="d3a99-108">Valeur du contrôle <xref:System.Windows.Forms.ListView.View%2A> propriété <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="d3a99-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="d3a99-109">Utilisez le <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> (méthode) de la vue de liste <xref:System.Windows.Forms.ListView.Columns%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="d3a99-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="d3a99-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3a99-110">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 [<span data-ttu-id="d3a99-111">Contrôle ListView</span><span class="sxs-lookup"><span data-stu-id="d3a99-111">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="d3a99-112">Vue d’ensemble du contrôle ListView</span><span class="sxs-lookup"><span data-stu-id="d3a99-112">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)

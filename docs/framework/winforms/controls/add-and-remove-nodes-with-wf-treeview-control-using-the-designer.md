---
title: 'Comment : ajouter et supprimer des nœuds avec le contrôle TreeView Windows Forms à l’aide du concepteur'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 95f3f097d8e01828f2727bac742c752b656019e5
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507821"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="3d85a-102">Comment : ajouter et supprimer des nœuds avec le contrôle TreeView Windows Forms à l’aide du concepteur</span><span class="sxs-lookup"><span data-stu-id="3d85a-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="3d85a-103">Étant donné que les Windows Forms <xref:System.Windows.Forms.TreeView> contrôle affiche les nœuds de façon hiérarchique, lors de l’ajout d’un nœud, vous devez faire attention à ce qui est son nœud parent.</span><span class="sxs-lookup"><span data-stu-id="3d85a-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="3d85a-104">La procédure suivante nécessite un **Windows Application** projet avec un formulaire contenant un <xref:System.Windows.Forms.TreeView> contrôle.</span><span class="sxs-lookup"><span data-stu-id="3d85a-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="3d85a-105">Pour plus d’informations sur la configuration d’un tel projet, consultez [Comment : créer un projet d’Application Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) et [Comment : ajouter des contrôles aux Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3d85a-105">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d85a-106">Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.</span><span class="sxs-lookup"><span data-stu-id="3d85a-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3d85a-107">Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="3d85a-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3d85a-108">Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3d85a-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="3d85a-109">Pour ajouter ou supprimer des nœuds dans le Concepteur</span><span class="sxs-lookup"><span data-stu-id="3d85a-109">To add or remove nodes in the designer</span></span>  
  
1.  <span data-ttu-id="3d85a-110">Sélectionnez le contrôle <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="3d85a-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2.  <span data-ttu-id="3d85a-111">Dans le **propriétés** fenêtre, cliquez sur le **points de suspension** (![d’écran de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) situé en regard le <xref:System.Windows.Forms.TreeView.Nodes%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="3d85a-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="3d85a-112">Le **Éditeur TreeNode** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="3d85a-112">The **TreeNode Editor** appears.</span></span>  
  
3.  <span data-ttu-id="3d85a-113">Pour ajouter des nœuds, un nœud racine doit exister ; s’il n’existe pas, vous devez d’abord ajouter une racine en cliquant sur le **racine ajouter** bouton.</span><span class="sxs-lookup"><span data-stu-id="3d85a-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="3d85a-114">Vous pouvez ensuite ajouter des nœuds enfants en sélectionnant la racine ou tout autre nœud, puis en cliquant sur le **ajouter un enfant** bouton.</span><span class="sxs-lookup"><span data-stu-id="3d85a-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4.  <span data-ttu-id="3d85a-115">Pour supprimer des nœuds, sélectionnez le nœud à supprimer, puis cliquez sur le **supprimer** bouton.</span><span class="sxs-lookup"><span data-stu-id="3d85a-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d85a-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d85a-116">See Also</span></span>  
 [<span data-ttu-id="3d85a-117">TreeView, contrôle</span><span class="sxs-lookup"><span data-stu-id="3d85a-117">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="3d85a-118">Vue d’ensemble du contrôle TreeView</span><span class="sxs-lookup"><span data-stu-id="3d85a-118">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="3d85a-119">Guide pratique pour définir des icônes pour le contrôle TreeView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d85a-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="3d85a-120">Guide pratique pour itérer au sein de tous les nœuds d’un contrôle TreeView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d85a-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="3d85a-121">Guide pratique pour identifier le nœud de TreeView sur lequel un clic est effectué</span><span class="sxs-lookup"><span data-stu-id="3d85a-121">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="3d85a-122">Guide pratique pour ajouter des informations personnalisées à un contrôle TreeView ou ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3d85a-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)

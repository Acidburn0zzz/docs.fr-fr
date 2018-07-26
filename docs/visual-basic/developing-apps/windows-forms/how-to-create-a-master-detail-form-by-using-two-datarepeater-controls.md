---
title: 'Comment : créer un formulaire maître / détail en utilisant deux contrôles DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245526"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="70316-102">Comment : créer un formulaire maître/détail en utilisant deux contrôles DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="70316-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="70316-103">Vous pouvez afficher les données associées à l’aide de deux ou plusieurs <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> contrôles pour créer un formulaire maître/détail.</span><span class="sxs-lookup"><span data-stu-id="70316-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="70316-104">Par exemple, vous souhaiterez peut-être afficher une liste de clients dans un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>et lorsque l’utilisateur sélectionne un client, afficher la liste des commandes de ce client dans un deuxième <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="70316-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="70316-105">Vous pouvez afficher les données associées en faisant glisser des éléments de détail qui partagent le même nœud de la table principale à partir de la **des Sources de données** fenêtre sur un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> contrôle.</span><span class="sxs-lookup"><span data-stu-id="70316-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="70316-106">Par exemple, si vous avez une source de données qui a une table Customers et une table de commandes connexe, consultez les deux tables en tant que nœuds de niveau supérieur dans l’arborescence dans le **des Sources de données** fenêtre.</span><span class="sxs-lookup"><span data-stu-id="70316-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="70316-107">Développez le nœud clients afin que vous puissiez voir les colonnes.</span><span class="sxs-lookup"><span data-stu-id="70316-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="70316-108">Notez que la dernière colonne dans la liste est un nœud extensible qui représente la table Orders.</span><span class="sxs-lookup"><span data-stu-id="70316-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="70316-109">Ce nœud représente les commandes connexes d’un client.</span><span class="sxs-lookup"><span data-stu-id="70316-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="70316-110">Pour afficher les données associées dans deux contrôles DataRepeater</span><span class="sxs-lookup"><span data-stu-id="70316-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="70316-111">Faites glisser deux <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> des contrôles de la **Visual Basic PowerPacks** onglet dans le **boîte à outils** à un contrôle de formulaire ou un conteneur.</span><span class="sxs-lookup"><span data-stu-id="70316-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="70316-112">Faites glisser les poignées de dimensionnement et de déplacement pour redimensionner les contrôles et les placer côte à côte.</span><span class="sxs-lookup"><span data-stu-id="70316-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="70316-113">Dans le menu **Données** , cliquez sur **Afficher les sources de données**.</span><span class="sxs-lookup"><span data-stu-id="70316-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70316-114">Si le **des Sources de données** fenêtre est vide, ajoutez une source de données à ce dernier.</span><span class="sxs-lookup"><span data-stu-id="70316-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="70316-115">Pour plus d’informations, consultez [Ajouter de nouvelles sources de données](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="70316-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="70316-116">Dans le **des Sources de données** fenêtre, sélectionnez le nœud de niveau supérieur pour la table principale.</span><span class="sxs-lookup"><span data-stu-id="70316-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="70316-117">Modifier le type de déplacement de la table principale vers les détails en cliquant sur **détails** dans la liste déroulante sur le nœud de la table.</span><span class="sxs-lookup"><span data-stu-id="70316-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="70316-118">Faites glisser le nœud de la table principale sur la région de modèle d’élément du premier <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> contrôle.</span><span class="sxs-lookup"><span data-stu-id="70316-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="70316-119">Développez le nœud de la table principale et sélectionnez le nœud secondaire de la table associée.</span><span class="sxs-lookup"><span data-stu-id="70316-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="70316-120">Modifier le type de déplacement de la table de détail pour les détails en cliquant sur **détails** dans la liste déroulante sur le nœud de la table.</span><span class="sxs-lookup"><span data-stu-id="70316-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="70316-121">Sélectionnez ce nœud table et faites-le glisser vers la région du modèle d’élément de la deuxième <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> contrôle.</span><span class="sxs-lookup"><span data-stu-id="70316-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70316-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70316-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="70316-123">Introduction au contrôle DataRepeater</span><span class="sxs-lookup"><span data-stu-id="70316-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="70316-124">Guide pratique : afficher des données liées dans un contrôle DataRepeater</span><span class="sxs-lookup"><span data-stu-id="70316-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="70316-125">Guide pratique pour afficher des données connexes dans une application Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70316-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="70316-126">Guide pratique : modifier l’apparence d’un contrôle DataRepeater</span><span class="sxs-lookup"><span data-stu-id="70316-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="70316-127">Dépannage des problèmes liés au contrôle DataRepeater</span><span class="sxs-lookup"><span data-stu-id="70316-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)

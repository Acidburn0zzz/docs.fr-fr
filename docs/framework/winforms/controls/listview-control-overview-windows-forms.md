---
title: Vue d'ensemble du contrôle ListView (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: ab2d0d9456f64f215ddbc0003833db1858f0ce1a
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45569331"
---
# <a name="listview-control-overview-windows-forms"></a>Vue d'ensemble du contrôle ListView (Windows Forms)
Le contrôle <xref:System.Windows.Forms.ListView> Windows Forms affiche une liste d'éléments avec des icônes. Vous pouvez utiliser un affichage de liste pour créer une interface utilisateur comme le volet droit de l'Explorateur Windows. Le contrôle a quatre modes d’affichage : LargeIcon, SmallIcon, liste et détails.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Ce que vous pouvez faire avec le contrôle ListView  
  
> [!NOTE]
>  Mode d’affichage supplémentaire, mosaïque, est uniquement disponible sur Windows XP et le système d’exploitation Windows Server 2003. Pour plus d’informations, consultez [Comment : activer l’affichage en mosaïque dans un contrôle ListView Windows Forms à](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 Le mode LargeIcon affiche de grandes icônes en regard du texte de l’élément ; Si le contrôle est suffisamment grand, les éléments apparaissent dans plusieurs colonnes. Le mode SmallIcon est la même, à ceci près qu’il affiche des petites icônes. Le mode liste affiche les petites icônes mais est toujours dans une seule colonne. Le mode Détails affiche les éléments dans plusieurs colonnes. Pour plus d’informations, consultez [Comment : ajouter des colonnes au contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md). Le mode d’affichage est déterminé par le <xref:System.Windows.Forms.ListView.View%2A> propriété. Tous les modes d’affichage peuvent afficher des images à partir de listes d’images. Pour plus d’informations, consultez [Comment : afficher des icônes pour le contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 Le tableau suivant répertorie certaines de la <xref:System.Windows.Forms.ListView> membres et les vues qu’ils sont valides dans.  
  
|Membre de ListView|Vue|  
|---------------------|----------|  
|Propriété <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> ou <xref:System.Windows.Forms.View.LargeIcon>|  
|Propriété <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> ou <xref:System.Windows.Forms.View.LargeIcon>|  
|Méthode <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Propriété <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> ou <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem> Événement|<xref:System.Windows.Forms.View.Details>|  
|Méthode <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>ou <xref:System.Windows.Forms.View.Tile>|  
|Méthode <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> ou <xref:System.Windows.Forms.View.LargeIcon>|  
|Méthode <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> ou <xref:System.Windows.Forms.View.Tile>|  
|Propriété <xref:System.Windows.Forms.ListView.Groups%2A>|Toutes les vues à l’exception <xref:System.Windows.Forms.View.List>|  
|Propriété <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View.Details>.|  
|Propriété <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>ou <xref:System.Windows.Forms.View.Tile>|  
  
 La propriété de clé de la <xref:System.Windows.Forms.ListView> contrôle est <xref:System.Windows.Forms.ListView.Items%2A>, qui contient les éléments affichés par le contrôle. Le <xref:System.Windows.Forms.ListView.SelectedItems%2A> propriété constituée une collection d’éléments actuellement sélectionnés dans le contrôle. L’utilisateur peut sélectionner plusieurs éléments, par exemple, pour glisser -déplacer plusieurs éléments à la fois à un autre contrôle, si le <xref:System.Windows.Forms.ListView.MultiSelect%2A> propriété est définie sur `true`. Le <xref:System.Windows.Forms.ListView> contrôle peut afficher des cases à cocher en regard des éléments, si le <xref:System.Windows.Forms.ListView.CheckBoxes%2A> propriété est définie sur `true`.  
  
 Le <xref:System.Windows.Forms.ListView.Activation%2A> propriété détermine le type d’action de l’utilisateur doit effectuer pour activer un élément dans la liste : les options sont <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, et <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick> l’activation requiert un seul clic pour activer l’élément. <xref:System.Windows.Forms.ItemActivation.TwoClick> l’activation, l’utilisateur doit double-cliquer pour activer l’élément ; un seul clic modifie la couleur de texte de l’élément. <xref:System.Windows.Forms.ItemActivation.Standard> l’activation, l’utilisateur doit double-cliquer pour activer un élément, mais l’élément ne change pas d’apparence.  
  
 Le <xref:System.Windows.Forms.ListView> contrôle prend également en charge les styles visuels et les autres fonctionnalités disponibles sur la plateforme Windows XP, y compris le regroupement, l’affichage en mosaïque et marques d’insertion. Pour plus d’informations, consultez [fonctionnalités de Windows XP et les contrôles Windows Forms](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.ListView>  
 [Contrôle ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Guide pratique pour ajouter et supprimer des éléments avec le contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Guide pratique pour ajouter des colonnes au contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [Guide pratique pour afficher des icônes pour le contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [Guide pratique pour afficher des sous-éléments en colonnes avec le contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [Guide pratique pour sélectionner un élément dans le contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 [Guide pratique pour grouper des éléments dans un contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)  
 [Guide pratique pour afficher une marque d'insertion dans un contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 [Guide pratique pour ajouter des fonctions de recherche à un contrôle ListView](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
 [Guide pratique pour ajouter des informations personnalisées à un contrôle TreeView ou ListView (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [Guide pratique pour créer une interface utilisateur à plusieurs volets à l'aide des Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)

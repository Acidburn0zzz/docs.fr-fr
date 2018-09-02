---
title: "Comment : masquer des ToolStripMenuItems à l'aide du concepteur"
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 37371269ef9db929573efff0a8e62c86a51b2c35
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423872"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>Comment : masquer des ToolStripMenuItems à l'aide du concepteur
Masquage d’éléments de menu est un moyen de contrôler l’interface utilisateur (IU) de votre application et de restreindre les commandes de l’utilisateur. Souvent, vous devez masquer un menu quand tous les éléments de menu sur ce dernier ne sont pas disponibles. Cela est moins distrait pour l’utilisateur. En outre, vous souhaiterez peut-être cacher et désactiver le menu ou un élément de menu, comme simple masquage n’empêche pas l’utilisateur d’accéder à une commande de menu à l’aide d’une touche de raccourci. Pour plus d’informations sur la désactivation des éléments de menu, consultez [Comment : désactiver des ToolStripMenuItems à l’aide du concepteur](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>Pour masquer un menu de niveau supérieur et ses éléments de sous-menu  
  
1.  Sélectionnez l’élément de menu de niveau supérieur et définissez son <xref:System.Windows.Forms.ToolStripItem.Visible%2A> ou <xref:System.Windows.Forms.ToolStripItem.Available%2A> propriété `false`.  
  
     Lorsque vous masquez l’élément de menu de niveau supérieur, tous les éléments de menu au sein de ce menu sont également masqués. Si vous cliquez quelque part autre que sur le <xref:System.Windows.Forms.MenuStrip> après avoir défini <xref:System.Windows.Forms.ToolStripItem.Visible%2A> à `false`, l’élément de menu de niveau supérieur entier et ses éléments de sous-menu disparaissent de votre formulaire, vous montrant ainsi l’effet de l’exécution de votre action. Pour afficher l’élément de menu de niveau supérieur masqué au moment du design, cliquez sur le <xref:System.Windows.Forms.MenuStrip> dans le **barre d’état du composant**, dans **structure du Document**, ou en haut de la grille des propriétés.  
  
> [!NOTE]
>  Vous allez masquer rarement un menu à l’exception de plusieurs menus enfants MDI (interface) de document dans un scénario de fusion.  
  
### <a name="to-hide-a-submenu-item"></a>Pour masquer un élément de sous-menu  
  
1.  Sélectionnez l’élément de sous-menu et définissez son <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propriété `false`.  
  
     Lorsque vous masquez un élément de sous-menu, il reste visible sur votre formulaire au moment du design afin que vous puissiez le sélectionner facilement pour les tâches ultérieures. Il est en fait masqué au moment de l’exécution.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [Vue d'ensemble du contrôle MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Guide pratique pour désactiver des ToolStripMenuItems à l’aide du concepteur](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)

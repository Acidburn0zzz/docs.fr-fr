---
title: 'Comment : désactiver des ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: 20d0e13642aac3004a31ff416318cf6723207379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532026"
---
# <a name="how-to-disable-toolstripmenuitems"></a>Comment : désactiver des ToolStripMenuItems
Vous pouvez limiter ou élargir les commandes de que l’utilisateur peut effectuer par activation et désactivation des éléments de menu en réponse aux activités de l’utilisateur. Éléments de menu sont activés par défaut lorsqu’ils sont créés, mais cela peut être ajusté par la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propriété. Vous pouvez modifier cette propriété au moment du design dans le **propriétés** fenêtre ou par programme en définissant dans le code.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Pour désactiver un élément de menu par programme  
  
-   Dans la méthode où vous définissez les propriétés de l’élément de menu, ajoutez le code pour définir le <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propriété `false`.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  La désactivation de l’élément de menu de niveau supérieur ou première dans un menu masque tous les éléments de menu contenus dans le menu, mais ne désactive pas les. De même, la désactivation d’un élément de menu qui comporte des éléments de sous-menu masque les éléments de sous-menu, mais ne désactive pas les. Si toutes les commandes de menu ne sont pas disponibles à l’utilisateur, il est considéré comme bonne pratique de programmation à masquer et désactiver l’intégralité du menu, comme cela présente une interface utilisateur propre. Masquer et désactivez le menu et chaque élément et l’élément de sous-menu du menu, de désactiver, car le masquage seul n’empêche pas l’accès à une commande de menu via une touche de raccourci. Définir le <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propriété d’un élément de menu de niveau supérieur pour `false` pour masquer l’intégralité du menu.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Guide pratique pour masquer des ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [Vue d'ensemble du contrôle MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)

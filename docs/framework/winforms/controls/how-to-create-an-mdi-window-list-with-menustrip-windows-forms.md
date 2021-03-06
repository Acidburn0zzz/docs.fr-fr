---
title: 'Procédure : Créer une liste des fenêtres MDI avec MenuStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: ec0d8af81e320bea3d9d69305f91bd56666ba7cc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299642"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a>Procédure : Créer une liste des fenêtres MDI avec MenuStrip (Windows Forms)
Utilisez l’interface multidocument (MDI) pour créer des applications qui peuvent ouvrir plusieurs documents simultanément le même temps et copiez et collez le contenu d’un document à l’autre.  
  
 Cette procédure vous montre comment créer une liste de tous les formulaires enfants actifs dans le menu de fenêtre du parent.  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a>Pour créer une liste de fenêtres MDI sur un MenuStrip  
  
1. Créez un formulaire et affectez la valeur `true` à sa propriété <xref:System.Windows.Forms.Form.IsMdiContainer%2A>.  
  
2. Ajoutez un <xref:System.Windows.Forms.MenuStrip> au formulaire.  
  
3. Ajoutez deux éléments de menu de niveau supérieur à la <xref:System.Windows.Forms.MenuStrip> et définissez leurs <xref:System.Windows.Forms.Control.Text%2A> propriétés à `&File` et `&Window`.  
  
4. Ajoutez un élément de sous-menu à l'élément de menu `&File` et affectez la valeur `&Open` à la propriété <xref:System.Windows.Forms.ToolStripItem.Text%2A>.  
  
5. Définir le <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propriété de la <xref:System.Windows.Forms.MenuStrip> à la `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
6. Ajoutez un formulaire au projet et ajouter le contrôle souhaité, un autre <xref:System.Windows.Forms.MenuStrip>.  
  
7. Créer un gestionnaire d’événements pour le <xref:System.Windows.Forms.Control.Click> événements de la `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8. Dans le Gestionnaire d’événements, insérez du code semblable à ce qui suit pour créer et afficher les nouvelles instances de `Form2` en tant qu’enfants MDI de `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. Placez le code comme suit dans le `&New`<xref:System.Windows.Forms.ToolStripMenuItem> pour inscrire le Gestionnaire d’événements.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Cet exemple nécessite :  
  
-   deux <xref:System.Windows.Forms.Form> contrôles nommés `Form1` et `Form2` ;  
  
-   un contrôle <xref:System.Windows.Forms.MenuStrip> sur `Form1` nommé `menuStrip1` et un contrôle <xref:System.Windows.Forms.MenuStrip> sur `Form2` nommé `menuStrip2` ;  
  
-   des références aux assemblys <xref:System?displayProperty=nameWithType> et <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Voir aussi

- [Procédure : créer des formulaires parents MDI](../advanced/how-to-create-mdi-parent-forms.md)
- [Procédure : créer des formulaires enfants MDI](../advanced/how-to-create-mdi-child-forms.md)
- [MenuStrip, contrôle](menustrip-control-windows-forms.md)

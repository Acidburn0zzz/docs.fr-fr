---
title: 'Procédure : ajouter et supprimer des onglets avec le contrôle TabControl de Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 723e05803b1f7d2bc56476248987085dbe5e23f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101599"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Procédure : ajouter et supprimer des onglets avec le contrôle TabControl de Windows Forms
Par défaut, un <xref:System.Windows.Forms.TabControl> contrôle contient deux <xref:System.Windows.Forms.TabPage> contrôles. Vous pouvez accéder à ces onglets via le <xref:System.Windows.Forms.TabControl.TabPages%2A> propriété.  
  
### <a name="to-add-a-tab-programmatically"></a>Pour ajouter un onglet par programme  
  
-   Utilisez le <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> méthode de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propriété.  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a>Pour supprimer un onglet par programme  
  
-   Pour supprimer les onglets sélectionnés, utilisez la <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> méthode de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propriété.  
  
     - ou -  
  
-   Pour supprimer tous les onglets, utilisez la <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> méthode de la <xref:System.Windows.Forms.TabControl.TabPages%2A> propriété.  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a>Voir aussi

- [Vue d’ensemble du contrôle TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procédure : ajouter un contrôle à un onglet](how-to-add-a-control-to-a-tab-page.md)
- [Procédure : désactiver des onglets](how-to-disable-tab-pages.md)
- [Procédure : modifier l’aspect du contrôle TabControl Windows Forms](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)

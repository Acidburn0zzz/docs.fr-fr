---
title: "Comment : définir l'arrière-plan d'un panneau Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: ff0c748cfb7b38c41b2ede211aed7bf6e6f68544
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534785"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Comment : définir l'arrière-plan d'un panneau Windows Forms
Windows Forms <xref:System.Windows.Forms.Panel> contrôle peut afficher une couleur d’arrière-plan et une image d’arrière-plan. Le <xref:System.Windows.Forms.Control.BackColor%2A> propriété définit la couleur d’arrière-plan des contrôles contenus, tels que les étiquettes et cases d’option. Si le <xref:System.Windows.Forms.Control.BackgroundImage%2A> propriété n’est pas définie, la <xref:System.Windows.Forms.Control.BackColor%2A> sélection remplira du panneau tout entier. Si le <xref:System.Windows.Forms.Control.BackgroundImage%2A> propriété est définie, l’image est affichée derrière les contrôles contenus.  
  
### <a name="to-set-the-background-programmatically"></a>Pour définir l’arrière-plan par programmation  
  
1.  Définir le panneau <xref:System.Windows.Forms.Control.BackColor%2A> propriété à une valeur de type <xref:System.Drawing.Color?displayProperty=nameWithType>.  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  Définir le panneau <xref:System.Windows.Forms.Control.BackgroundImage%2A> à l’aide de la propriété du <xref:System.Drawing.Image.FromFile%2A> méthode de la <xref:System.Drawing.Image?displayProperty=nameWithType> classe.  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Panel, contrôle](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Vue d’ensemble du contrôle Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)

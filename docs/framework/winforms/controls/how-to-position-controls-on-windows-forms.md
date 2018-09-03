---
title: 'Comment : positionner des contrôles dans des Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 6843c22fec964de92c41760f1108d1c83e1f5bf8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2018
ms.locfileid: "43476077"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Comment : positionner des contrôles dans des Windows Forms
Pour positionner des contrôles, utiliser le Concepteur de formulaires Windows ou spécifiez le <xref:System.Windows.Forms.Control.Location%2A> propriété.  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Pour positionner un contrôle sur l’aire de conception du Concepteur Windows Forms  
  
-   Faites glisser le contrôle vers l’emplacement approprié avec la souris.  
  
    > [!NOTE]
    >  Sélectionnez le contrôle et les déplacer avec la flèche touches pour positionner plus précisément. En outre, *les lignes d’alignement* vous aident à placer les contrôles avec précision sur votre formulaire. Pour plus d’informations, consultez [procédure pas à pas : organisation des contrôles dans les Windows Forms à l’aide des lignes d’alignement](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### <a name="to-position-a-control-using-the-properties-window"></a>Pour positionner un contrôle à l’aide de la fenêtre Propriétés  
  
1.  Cliquez sur le contrôle que vous souhaitez positionner.  
  
2.  Dans le **propriétés** fenêtre, les valeurs de type pour le <xref:System.Windows.Forms.Control.Location%2A> propriété séparés par une virgule, pour positionner le contrôle dans son conteneur.  
  
     Le premier nombre (X) est la distance entre la bordure gauche du conteneur ; le deuxième nombre (Y) est la distance entre la bordure supérieure de la zone conteneur, en pixels.  
  
    > [!NOTE]
    >  Vous pouvez développer le <xref:System.Windows.Forms.Control.Location%2A> propriété permettant de taper le **X** et **Y** valeurs individuellement.  
  
### <a name="to-position-a-control-programmatically"></a>Pour positionner un contrôle par programmation  
  
1.  Définir le <xref:System.Windows.Forms.Control.Location%2A> propriété du contrôle à un <xref:System.Drawing.Point>.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Modifiez la coordonnée X de l’emplacement du contrôle à l’aide de la <xref:System.Windows.Forms.Control.Left%2A> sous-propriété.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>Pour incrémenter l’emplacement d’un contrôle par programmation  
  
1.  Définir le <xref:System.Windows.Forms.Control.Left%2A> sous-propriété pour incrémenter la coordonnée X du contrôle.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Utilisez le <xref:System.Windows.Forms.Control.Location%2A> propriété à définir d’un contrôle X et Y place simultanément. Pour définir une position individuellement, utilisez le contrôle <xref:System.Windows.Forms.Control.Left%2A> (**X**) ou <xref:System.Windows.Forms.Control.Top%2A> (**Y**) sous-propriété. N’essayez pas de définir implicitement les coordonnées X et Y de la <xref:System.Drawing.Point> structure qui représente la position du bouton, car cette structure contient une copie des coordonnées du bouton.  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Procédure pas à pas : organisation des contrôles dans les Windows Forms à l’aide des lignes d’alignement](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Procédure pas à pas : organisation des contrôles dans les Windows Forms à l’aide d’un TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Procédure pas à pas : organisation des contrôles dans les Windows Forms à l’aide d’un FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Disposition des contrôles dans les Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Création d'étiquettes et de raccourcis pour les contrôles Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Contrôles à utiliser dans les Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Classement par fonction des contrôles Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [Comment : définir l’emplacement de l’écran des Windows Forms](https://msdn.microsoft.com/library/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)

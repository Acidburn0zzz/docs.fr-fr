---
title: 'Comment : modifier les bordures des Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 76bae6ba3b2a36e9dfa527528fe1e4322a87426c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539774"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Comment : modifier les bordures des Windows Forms
Vous pouvez choisir parmi plusieurs styles de bordure quand vous déterminez l'apparence et le comportement de vos Windows Forms. En modifiant la propriété <xref:System.Windows.Forms.Form.FormBorderStyle%2A>, vous pouvez contrôler le comportement de redimensionnement du formulaire. De plus, la définition de <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affecte l'affichage de la barre de légende et de ses boutons. Pour plus d'informations, consultez <xref:System.Windows.Forms.FormBorderStyle>.  
  
 Cette tâche est très bien prise en charge dans Visual Studio.  
  
 Voir aussi [Comment : modifier les bordures des Windows Forms à l’aide du concepteur](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>Pour définir le style de bordure des Windows Forms par programmation  
  
-   Affectez à la propriété <xref:System.Windows.Forms.Form.FormBorderStyle%2A> le style souhaité. L’exemple de code suivant définit le style de bordure du formulaire `DlgBx1` à <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     Consultez également [Comment : créer des boîtes de dialogue au moment du Design](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).  
  
     En outre, si vous avez choisi un style de bordure du formulaire fournit facultatif **réduire** et **agrandir** boutons, vous pouvez spécifier si vous souhaitez que ces deux boutons puisse fonctionner. Ils sont utiles quand vous souhaitez contrôler étroitement l'expérience utilisateur. Le **réduire** et **agrandir** boutons sont activés par défaut et leur fonctionnalité est définie via la **propriétés** fenêtre.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [Bien démarrer avec Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)

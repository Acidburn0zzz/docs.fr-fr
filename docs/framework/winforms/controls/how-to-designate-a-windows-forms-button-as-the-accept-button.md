---
title: 'Comment : désigner un contrôle Button Windows Forms comme bouton Accepter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: a69964b83e9948a844483725616a150234a38c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Comment : désigner un contrôle Button Windows Forms comme bouton Accepter
Sur un Windows Form, vous pouvez désigner un <xref:System.Windows.Forms.Button> contrôle bouton Accepter, également connu sous le bouton par défaut. Chaque fois que l’utilisateur appuie sur la touche entrée, le bouton par défaut est cliqué sur quelles que soient les autres contrôles du formulaire a le focus.  
  
> [!NOTE]
>  Les exceptions sont lorsque le contrôle qui a le focus est un autre bouton, dans ce cas, un clic sur le bouton a le focus, ou une zone de texte multiligne ou un contrôle personnalisé qui intercepte la touche ENTRÉE.  
  
### <a name="to-designate-the-accept-button"></a>Pour désigner le bouton Accepter  
  
1.  Valeur du formulaire <xref:System.Windows.Forms.Form.AcceptButton%2A> propriété approprié <xref:System.Windows.Forms.Button> contrôle.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Vue d'ensemble du contrôle Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Méthodes de sélection du contrôle Button Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Guide pratique pour répondre à un clic du contrôle Button Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Guide pratique pour désigner un contrôle Button Windows Forms en tant que bouton Annuler](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [Button, contrôle](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)

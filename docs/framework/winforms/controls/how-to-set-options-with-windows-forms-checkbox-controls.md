---
title: 'Comment : définir des options avec les contrôles CheckBox Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: dc9e7b1aea74874c66bf9eb96a5b919ed9b4b73b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534084"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="44ca7-102">Comment : définir des options avec les contrôles CheckBox Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44ca7-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="44ca7-103">Windows Forms <xref:System.Windows.Forms.CheckBox> contrôle permet de donner aux utilisateurs vrai/faux ou Oui/non.</span><span class="sxs-lookup"><span data-stu-id="44ca7-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="44ca7-104">Le contrôle affiche une case à cocher lorsqu’il est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="44ca7-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="44ca7-105">Pour définir des options avec les contrôles de case à cocher</span><span class="sxs-lookup"><span data-stu-id="44ca7-105">To set options with CheckBox controls</span></span>  
  
1.  <span data-ttu-id="44ca7-106">Examinez la valeur de la <xref:System.Windows.Forms.CheckBox.Checked%2A> propriété pour déterminer son état, cette valeur permet de définir une option.</span><span class="sxs-lookup"><span data-stu-id="44ca7-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="44ca7-107">Dans l’exemple de code ci-dessous, lorsque le <xref:System.Windows.Forms.CheckBox> du contrôle <xref:System.Windows.Forms.CheckBox.CheckedChanged> événement est déclenché, du formulaire <xref:System.Windows.Forms.Control.AllowDrop%2A> est définie sur `false` si la case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="44ca7-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="44ca7-108">Cela est utile pour les situations où vous souhaitez limiter l’interaction de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44ca7-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="44ca7-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="44ca7-109">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="44ca7-110">Vue d'ensemble du contrôle CheckBox</span><span class="sxs-lookup"><span data-stu-id="44ca7-110">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="44ca7-111">Guide pratique pour répondre à un clic du contrôle CheckBox Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44ca7-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="44ca7-112">CheckBox, contrôle</span><span class="sxs-lookup"><span data-stu-id="44ca7-112">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)

---
title: "Comment : désigner un bouton Windows Forms comme bouton Accepter à l'aide du concepteur"
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: aade1b6e988fc4b43f7ad9cfb58382302c875d37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527041"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="007fe-102">Comment : désigner un bouton Windows Forms comme bouton Accepter à l'aide du concepteur</span><span class="sxs-lookup"><span data-stu-id="007fe-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="007fe-103">Sur un Windows Form, vous pouvez désigner un <xref:System.Windows.Forms.Button> contrôle bouton Accepter, également connu sous le bouton par défaut.</span><span class="sxs-lookup"><span data-stu-id="007fe-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="007fe-104">Chaque fois que l’utilisateur appuie sur la touche entrée, le bouton par défaut est cliqué sur quelles que soient les autres contrôles du formulaire a le focus.</span><span class="sxs-lookup"><span data-stu-id="007fe-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="007fe-105">Les exceptions sont lorsque le contrôle qui a le focus est un autre bouton, dans ce cas, un clic sur le bouton a le focus, ou une zone de texte multiligne ou un contrôle personnalisé qui intercepte la touche ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="007fe-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="007fe-106">Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.</span><span class="sxs-lookup"><span data-stu-id="007fe-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="007fe-107">Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="007fe-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="007fe-108">Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="007fe-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="007fe-109">Pour désigner le bouton Accepter</span><span class="sxs-lookup"><span data-stu-id="007fe-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="007fe-110">Sélectionnez le formulaire sur lequel se trouve le bouton.</span><span class="sxs-lookup"><span data-stu-id="007fe-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="007fe-111">Dans le **propriétés** , configurez du formulaire <xref:System.Windows.Forms.Form.AcceptButton%2A> propriété le <xref:System.Windows.Forms.Button> nom du contrôle.</span><span class="sxs-lookup"><span data-stu-id="007fe-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007fe-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="007fe-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [<span data-ttu-id="007fe-113">Vue d'ensemble du contrôle Button</span><span class="sxs-lookup"><span data-stu-id="007fe-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="007fe-114">Méthodes de sélection du contrôle Button Windows Forms</span><span class="sxs-lookup"><span data-stu-id="007fe-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="007fe-115">Guide pratique pour répondre à un clic du contrôle Button Windows Forms</span><span class="sxs-lookup"><span data-stu-id="007fe-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="007fe-116">Guide pratique pour désigner un bouton Windows Forms comme bouton Annuler à l’aide du concepteur</span><span class="sxs-lookup"><span data-stu-id="007fe-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="007fe-117">Button, contrôle</span><span class="sxs-lookup"><span data-stu-id="007fe-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)

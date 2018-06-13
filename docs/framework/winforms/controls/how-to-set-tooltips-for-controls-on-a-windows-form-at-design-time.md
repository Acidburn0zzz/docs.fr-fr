---
title: "Comment : définir des info-bulles pour les contrôles d'un Windows Form au moment du design"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 4e4623c1c0fe7d082e4d1a1f404ddaa94e79fc2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533628"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="0fcd4-102">Comment : définir des info-bulles pour les contrôles d'un Windows Form au moment du design</span><span class="sxs-lookup"><span data-stu-id="0fcd4-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="0fcd4-103">Vous pouvez définir un <xref:System.Windows.Forms.ToolTip> chaîne dans le code ou dans le Concepteur Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0fcd4-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="0fcd4-104">Pour plus d’informations sur la <xref:System.Windows.Forms.ToolTip> composant, consultez [vue d’ensemble du composant ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0fcd4-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fcd4-105">Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.</span><span class="sxs-lookup"><span data-stu-id="0fcd4-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0fcd4-106">Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="0fcd4-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0fcd4-107">Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0fcd4-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="0fcd4-108">Pour définir une info-bulle par programmation</span><span class="sxs-lookup"><span data-stu-id="0fcd4-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="0fcd4-109">Ajoutez le contrôle qui affiche l’info-bulle.</span><span class="sxs-lookup"><span data-stu-id="0fcd4-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="0fcd4-110">Utilisez le <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> méthode de la <xref:System.Windows.Forms.ToolTip> composant.</span><span class="sxs-lookup"><span data-stu-id="0fcd4-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="0fcd4-111">Pour définir une info-bulle dans le Concepteur</span><span class="sxs-lookup"><span data-stu-id="0fcd4-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="0fcd4-112">Ajoutez un composant <xref:System.Windows.Forms.ToolTip> au formulaire.</span><span class="sxs-lookup"><span data-stu-id="0fcd4-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="0fcd4-113">Sélectionnez le contrôle qui affiche l’info-bulle, ou ajoutez-le au formulaire.</span><span class="sxs-lookup"><span data-stu-id="0fcd4-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="0fcd4-114">Dans le **propriétés** , configurez la **info-bulle sur ToolTip1** valeur à une chaîne de texte appropriée.</span><span class="sxs-lookup"><span data-stu-id="0fcd4-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcd4-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0fcd4-115">See Also</span></span>  
 [<span data-ttu-id="0fcd4-116">Vue d’ensemble du composant ToolTip</span><span class="sxs-lookup"><span data-stu-id="0fcd4-116">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="0fcd4-117">Guide pratique pour modifier la durée avant affichage du composant ToolTip Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fcd4-117">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [<span data-ttu-id="0fcd4-118">ToolTip, composant</span><span class="sxs-lookup"><span data-stu-id="0fcd4-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)

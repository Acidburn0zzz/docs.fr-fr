---
title: 'Comment : créer une interface de style Explorateur Windows sur un Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 2d5b79244d867ea4b6134413d42710b2eadc871e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532384"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="28da5-102">Comment : créer une interface de style Explorateur Windows sur un Windows Form</span><span class="sxs-lookup"><span data-stu-id="28da5-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="28da5-103">L’Explorateur Windows est un choix d’interface utilisateur commune pour les applications en raison de son caractère familier.</span><span class="sxs-lookup"><span data-stu-id="28da5-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="28da5-104">Est de l’Explorateur Windows, essentiellement, un <xref:System.Windows.Forms.TreeView> contrôle et un <xref:System.Windows.Forms.ListView> contrôle sur des panneaux séparés.</span><span class="sxs-lookup"><span data-stu-id="28da5-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="28da5-105">Les panneaux sont rendus redimensionnables par un séparateur.</span><span class="sxs-lookup"><span data-stu-id="28da5-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="28da5-106">Cette disposition des contrôles est très efficace pour afficher et parcourir des informations.</span><span class="sxs-lookup"><span data-stu-id="28da5-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="28da5-107">Les étapes suivantes montrent comment organiser les contrôles dans un formulaire de type Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="28da5-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="28da5-108">Elles ne présentent pas de procédure Ajouter les fonctionnalités d’exploration des fichiers de l’application de l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="28da5-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28da5-109">Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.</span><span class="sxs-lookup"><span data-stu-id="28da5-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="28da5-110">Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="28da5-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="28da5-111">Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="28da5-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="28da5-112">Pour créer un formulaire Windows de style Explorateur Windows</span><span class="sxs-lookup"><span data-stu-id="28da5-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="28da5-113">Créer un nouveau projet d’Application Windows.</span><span class="sxs-lookup"><span data-stu-id="28da5-113">Create a new Windows Application project.</span></span> <span data-ttu-id="28da5-114">Pour plus d’informations, consultez l’article [Comment : créer un projet d’application Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="28da5-114">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="28da5-115">À partir de la **boîte à outils**:</span><span class="sxs-lookup"><span data-stu-id="28da5-115">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="28da5-116">Faites glisser un <xref:System.Windows.Forms.SplitContainer> contrôle vers votre formulaire.</span><span class="sxs-lookup"><span data-stu-id="28da5-116">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="28da5-117">Faites glisser un <xref:System.Windows.Forms.TreeView> contrôler en **SplitterPanel1** (le panneau de configuration de la <xref:System.Windows.Forms.SplitContainer> contrôle marqué comme **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="28da5-117">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="28da5-118">Faites glisser un <xref:System.Windows.Forms.ListView> contrôler en **SplitterPanel2** (le panneau de configuration de la <xref:System.Windows.Forms.SplitContainer> contrôle marqué comme **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="28da5-118">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="28da5-119">Sélectionnez les trois contrôles en appuyant sur la touche CTRL ENFONCÉE et en cliquant dessus à son tour.</span><span class="sxs-lookup"><span data-stu-id="28da5-119">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="28da5-120">Lorsque vous sélectionnez le <xref:System.Windows.Forms.SplitContainer> contrôler, cliquez sur la barre de fractionnement, plutôt que les panneaux.</span><span class="sxs-lookup"><span data-stu-id="28da5-120">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28da5-121">N’utilisez pas le **sélectionner tout** commande sur le **modifier** menu.</span><span class="sxs-lookup"><span data-stu-id="28da5-121">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="28da5-122">Si vous procédez ainsi, la propriété nécessaire à l’étape suivante n’apparaîtra pas dans le **propriétés** fenêtre.</span><span class="sxs-lookup"><span data-stu-id="28da5-122">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="28da5-123">Dans le **propriétés** , configurez la <xref:System.Windows.Forms.SplitContainer.Dock%2A> propriété <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="28da5-123">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="28da5-124">Appuyez sur F5 pour exécuter l'application.</span><span class="sxs-lookup"><span data-stu-id="28da5-124">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="28da5-125">Le formulaire affiche une interface utilisateur en deux parties, semblable à celle de l’Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="28da5-125">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28da5-126">Lorsque vous faites glisser le séparateur, les panneaux se redimensionnent.</span><span class="sxs-lookup"><span data-stu-id="28da5-126">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28da5-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28da5-127">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="28da5-128">Guide pratique pour créer une interface utilisateur à plusieurs volets à l'aide des Windows Forms</span><span class="sxs-lookup"><span data-stu-id="28da5-128">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [<span data-ttu-id="28da5-129">Guide pratique pour définir le redimensionnement et le positionnement du comportement dans une fenêtre fractionnée</span><span class="sxs-lookup"><span data-stu-id="28da5-129">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [<span data-ttu-id="28da5-130">Guide pratique pour fractionner une fenêtre horizontalement</span><span class="sxs-lookup"><span data-stu-id="28da5-130">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [<span data-ttu-id="28da5-131">SplitContainer, contrôle</span><span class="sxs-lookup"><span data-stu-id="28da5-131">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)

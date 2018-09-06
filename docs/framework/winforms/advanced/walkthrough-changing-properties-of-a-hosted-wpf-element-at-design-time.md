---
title: "Procédure pas à pas : modification des propriétés d'un élément WPF hébergé au moment du design"
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: 15cab9266af5840aa4b37a62b71bd5010b7a859a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741018"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a><span data-ttu-id="20637-102">Procédure pas à pas : modification des propriétés d'un élément WPF hébergé au moment du design</span><span class="sxs-lookup"><span data-stu-id="20637-102">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>
<span data-ttu-id="20637-103">Cette procédure pas à pas montre comment modifier les valeurs de propriétés d'un contrôle Windows Presentation Foundation (WPF) hébergé sur un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="20637-103">This walkthrough shows you how to change property values of a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>  
  
 <span data-ttu-id="20637-104">Lors de cette procédure pas à pas, vous allez exécuter les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="20637-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="20637-105">créer le projet ;</span><span class="sxs-lookup"><span data-stu-id="20637-105">Create the project.</span></span>  
  
-   <span data-ttu-id="20637-106">créer le contrôle WPF ;</span><span class="sxs-lookup"><span data-stu-id="20637-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="20637-107">héberger les contrôles WPF sur un Windows Form ;</span><span class="sxs-lookup"><span data-stu-id="20637-107">Host the WPF controls on a Windows Form.</span></span>  
  
-   <span data-ttu-id="20637-108">utiliser le Concepteur WPF pour Visual Studio pour modifier les valeurs de propriétés.</span><span class="sxs-lookup"><span data-stu-id="20637-108">Use the WPF Designer for Visual Studio to change property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20637-109">Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.</span><span class="sxs-lookup"><span data-stu-id="20637-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="20637-110">Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="20637-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="20637-111">Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="20637-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20637-112">Prérequis</span><span class="sxs-lookup"><span data-stu-id="20637-112">Prerequisites</span></span>  
 <span data-ttu-id="20637-113">Pour exécuter cette procédure pas à pas, vous devez disposer des composants suivants :</span><span class="sxs-lookup"><span data-stu-id="20637-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="20637-114">.</span><span class="sxs-lookup"><span data-stu-id="20637-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="20637-115">Création du projet</span><span class="sxs-lookup"><span data-stu-id="20637-115">Creating the Project</span></span>  
 <span data-ttu-id="20637-116">La première étape consiste à créer le projet Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="20637-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20637-117">Lors de l'hébergement de contenu WPF, seuls les projets Visual Basic et C# sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="20637-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="20637-118">Pour créer le projet</span><span class="sxs-lookup"><span data-stu-id="20637-118">To create the project</span></span>  
  
-   <span data-ttu-id="20637-119">Créer un nouveau projet d’Application de Windows Forms dans Visual Basic ou Visual c# nommé `WpfHost`.</span><span class="sxs-lookup"><span data-stu-id="20637-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `WpfHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="20637-120">Création du contrôle WPF</span><span class="sxs-lookup"><span data-stu-id="20637-120">Creating the WPF Control</span></span>  
 <span data-ttu-id="20637-121">Après avoir ajouté un contrôle WPF au projet, vous pouvez le disposer sur le formulaire.</span><span class="sxs-lookup"><span data-stu-id="20637-121">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="20637-122">Pour créer des contrôles WPF</span><span class="sxs-lookup"><span data-stu-id="20637-122">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="20637-123">Ajoutez un nouveau <xref:System.Windows.Controls.UserControl> WPF au projet.</span><span class="sxs-lookup"><span data-stu-id="20637-123">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="20637-124">Utilisez le nom par défaut pour le type de contrôle, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="20637-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="20637-125">Pour plus d’informations, consultez [procédure pas à pas : création de nouveau contenu WPF sur les formulaires Windows au moment du Design](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="20637-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="20637-126">Dans le **propriétés** fenêtre, définissez la valeur de la <xref:System.Windows.Controls.Control.Background%2A> propriété `Blue`.</span><span class="sxs-lookup"><span data-stu-id="20637-126">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
3.  <span data-ttu-id="20637-127">Générez le projet.</span><span class="sxs-lookup"><span data-stu-id="20637-127">Build the project.</span></span>  
  
## <a name="changing-property-values-on-the-wpf-control"></a><span data-ttu-id="20637-128">Modification de valeurs de propriétés sur le contrôle WPF</span><span class="sxs-lookup"><span data-stu-id="20637-128">Changing Property Values on the WPF Control</span></span>  
 <span data-ttu-id="20637-129">Le Smart Tag <xref:System.Windows.Forms.Integration.ElementHost> facilite la modification des propriétés du contenu WPF hébergé à l'aide du Concepteur WPF.</span><span class="sxs-lookup"><span data-stu-id="20637-129">The <xref:System.Windows.Forms.Integration.ElementHost> smart tag makes it easy to change properties of hosted WPF content by using the WPF Designer.</span></span>  
  
#### <a name="to-host-a-wpf-control"></a><span data-ttu-id="20637-130">Pour héberger un contrôle WPF</span><span class="sxs-lookup"><span data-stu-id="20637-130">To host a WPF control</span></span>  
  
1.  <span data-ttu-id="20637-131">Ouvrez `Form1` dans le Concepteur Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="20637-131">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="20637-132">Dans le **boîte à outils**, dans le **contrôles utilisateur WPF** onglet, double-cliquez sur `UserControl1` pour créer une instance de `UserControl1` sur le formulaire.</span><span class="sxs-lookup"><span data-stu-id="20637-132">In the **Toolbox**, in the **WPF User Controls** tab, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="20637-133">L'instance de `UserControl1` est hébergée dans un nouveau contrôle <xref:System.Windows.Forms.Integration.ElementHost> nommé `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="20637-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="20637-134">Dans le **tâches ElementHost** panneau des balises actives, sélectionnez **modifier le contenu hébergé**.</span><span class="sxs-lookup"><span data-stu-id="20637-134">In the **ElementHost Tasks** smart tag panel, select **Edit Hosted Content**.</span></span>  
  
     <span data-ttu-id="20637-135">UserControl1.xaml s'ouvre dans le Concepteur WPF.</span><span class="sxs-lookup"><span data-stu-id="20637-135">UserControl1.xaml opens in the WPF Designer.</span></span>  
  
4.  <span data-ttu-id="20637-136">Dans le **propriétés** fenêtre, définissez la valeur de la <xref:System.Windows.Controls.Control.Background%2A> propriété `Red`.</span><span class="sxs-lookup"><span data-stu-id="20637-136">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Red`.</span></span>  
  
5.  <span data-ttu-id="20637-137">Regénérez le projet.</span><span class="sxs-lookup"><span data-stu-id="20637-137">Rebuild the project.</span></span>  
  
6.  <span data-ttu-id="20637-138">Ouvrez `Form1` dans le Concepteur Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="20637-138">Open `Form1` in the Windows Forms Designer.</span></span>  
  
     <span data-ttu-id="20637-139">L'instance de `UserControl1` possède un arrière-plan rouge.</span><span class="sxs-lookup"><span data-stu-id="20637-139">The instance of `UserControl1` has a red background.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20637-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20637-140">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="20637-141">Guide pratique pour ancrer et arrimer des contrôles enfants dans un contrôle TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="20637-141">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="20637-142">Guide pratique pour aligner un contrôle sur les bords des formulaires au moment du design</span><span class="sxs-lookup"><span data-stu-id="20637-142">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="20637-143">Procédure pas à pas : organisation des contrôles dans les Windows Forms à l’aide des lignes d’alignement</span><span class="sxs-lookup"><span data-stu-id="20637-143">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="20637-144">Migration et interopérabilité</span><span class="sxs-lookup"><span data-stu-id="20637-144">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="20637-145">Utilisation de contrôles WPF</span><span class="sxs-lookup"><span data-stu-id="20637-145">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="20637-146">Concevoir en XAML dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20637-146">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)

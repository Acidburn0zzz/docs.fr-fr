---
title: "Procédure pas à pas : copier-coller d'un contrôle ElementHost dans d'autres Windows Forms"
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
ms.openlocfilehash: 55b426fbe95bac269183a649ecd839175a8cbdda
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037251"
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="4860e-102">Procédure pas à pas : copier-coller d'un contrôle ElementHost dans d'autres Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4860e-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="4860e-103">Cette procédure pas à pas montre comment copier un contrôle Windows Presentation Foundation (WPF) d'un Windows Form à un autre.</span><span class="sxs-lookup"><span data-stu-id="4860e-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="4860e-104">Lors de cette procédure pas à pas, vous allez exécuter les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="4860e-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="4860e-105">créer le projet ;</span><span class="sxs-lookup"><span data-stu-id="4860e-105">Create the project.</span></span>  
  
-   <span data-ttu-id="4860e-106">copier un contrôle WPF.</span><span class="sxs-lookup"><span data-stu-id="4860e-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4860e-107">Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.</span><span class="sxs-lookup"><span data-stu-id="4860e-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4860e-108">Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="4860e-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4860e-109">Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="4860e-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4860e-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4860e-110">Prerequisites</span></span>  
 <span data-ttu-id="4860e-111">Pour exécuter cette procédure pas à pas, vous devez disposer des composants suivants :</span><span class="sxs-lookup"><span data-stu-id="4860e-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="4860e-112">.</span><span class="sxs-lookup"><span data-stu-id="4860e-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="4860e-113">Création du projet</span><span class="sxs-lookup"><span data-stu-id="4860e-113">Creating the Project</span></span>  
 <span data-ttu-id="4860e-114">La première étape consiste à créer le projet Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4860e-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4860e-115">Lors de l'hébergement de contenu WPF, seuls les projets Visual Basic et C# sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4860e-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="4860e-116">Pour créer le projet</span><span class="sxs-lookup"><span data-stu-id="4860e-116">To create the project</span></span>  
  
-   <span data-ttu-id="4860e-117">Créer un nouveau projet d’Application de Windows Forms dans Visual Basic ou Visual c# nommé `CopyElementHost`.</span><span class="sxs-lookup"><span data-stu-id="4860e-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="4860e-118">Copie d'un contrôle WPF</span><span class="sxs-lookup"><span data-stu-id="4860e-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="4860e-119">Après avoir ajouté un contrôle WPF au projet, vous pouvez le copier vers d'autres formulaires du projet.</span><span class="sxs-lookup"><span data-stu-id="4860e-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="4860e-120">Pour copier un contrôle WPF</span><span class="sxs-lookup"><span data-stu-id="4860e-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="4860e-121">Ajoutez un nouveau projet <xref:System.Windows.Controls.UserControl> WPF à la solution.</span><span class="sxs-lookup"><span data-stu-id="4860e-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="4860e-122">Utilisez le nom par défaut pour le type de contrôle, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="4860e-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="4860e-123">Pour plus d’informations, consultez [procédure pas à pas : création de nouveau contenu WPF sur les formulaires Windows au moment du Design](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="4860e-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="4860e-124">Générez le projet.</span><span class="sxs-lookup"><span data-stu-id="4860e-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="4860e-125">Ouvrez `Form1` dans le Concepteur Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4860e-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="4860e-126">À partir de la **boîte à outils**, faites glisser une instance de `UserControl1` vers le formulaire.</span><span class="sxs-lookup"><span data-stu-id="4860e-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="4860e-127">Une instance de `UserControl1` est hébergée dans un nouveau contrôle <xref:System.Windows.Forms.Integration.ElementHost> nommé `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="4860e-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="4860e-128">`elementHost1` étant sélectionné, appuyez sur Ctrl+C pour le copier dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="4860e-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="4860e-129">Ajoutez un nouveau Windows Form au projet.</span><span class="sxs-lookup"><span data-stu-id="4860e-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="4860e-130">Utilisez le nom par défaut pour le type de formulaire, `Form2`.</span><span class="sxs-lookup"><span data-stu-id="4860e-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="4860e-131">`Form2` étant ouvert dans le Concepteur Windows Forms, appuyez sur Ctrl+V pour coller une copie de `elementHost1` sur le formulaire.</span><span class="sxs-lookup"><span data-stu-id="4860e-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="4860e-132">Le contrôle copié se nomme également `elementHost1`, car il s'agit d'un champ privé de la classe `Form2`.</span><span class="sxs-lookup"><span data-stu-id="4860e-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="4860e-133">Il n'existe aucune collision de nom avec le `elementHost1` dans la classe `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4860e-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4860e-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4860e-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="4860e-135">Migration et interopérabilité</span><span class="sxs-lookup"><span data-stu-id="4860e-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="4860e-136">Utilisation de contrôles WPF</span><span class="sxs-lookup"><span data-stu-id="4860e-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="4860e-137">Concevoir en XAML dans Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4860e-137">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)

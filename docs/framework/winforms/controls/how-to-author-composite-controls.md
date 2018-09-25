---
title: 'Comment : créer des contrôles composites'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
ms.openlocfilehash: 7abdeae4d19ceb6425f85e3cdd28f565a03d7ea4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075474"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="2f48b-102">Comment : créer des contrôles composites</span><span class="sxs-lookup"><span data-stu-id="2f48b-102">How to: Author Composite Controls</span></span>
<span data-ttu-id="2f48b-103">Les contrôles composites peuvent être utilisés de plusieurs façons.</span><span class="sxs-lookup"><span data-stu-id="2f48b-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="2f48b-104">Vous pouvez les créer dans le cadre d’un projet d’application de bureau Windows et les utiliser uniquement sur les formulaires du projet.</span><span class="sxs-lookup"><span data-stu-id="2f48b-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="2f48b-105">Ou vous pouvez les créer dans un projet de bibliothèque de contrôles Windows, compiler le projet dans un assembly et utiliser les contrôles dans d’autres projets.</span><span class="sxs-lookup"><span data-stu-id="2f48b-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="2f48b-106">Vous pouvez même hériter d’eux et utiliser l’héritage visuel pour les personnaliser rapidement à des fins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="2f48b-106">You can even inherit from them, and use visual inheritance to customize them quickly for special purposes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f48b-107">Si vous souhaitez créer un contrôle à utiliser sur des Web Forms, consultez [Développement de contrôles serveur ASP.NET personnalisés](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span><span class="sxs-lookup"><span data-stu-id="2f48b-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
>   
>  <span data-ttu-id="2f48b-108">Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.</span><span class="sxs-lookup"><span data-stu-id="2f48b-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2f48b-109">Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="2f48b-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2f48b-110">Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="2f48b-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-author-a-composite-control"></a><span data-ttu-id="2f48b-111">Pour créer un contrôle composite</span><span class="sxs-lookup"><span data-stu-id="2f48b-111">To author a composite control</span></span>  
  
1.  <span data-ttu-id="2f48b-112">Ouvrez un nouveau projet d’**application Windows** nommé `DemoControlHost`.</span><span class="sxs-lookup"><span data-stu-id="2f48b-112">Open a new **Windows Application** project called `DemoControlHost`.</span></span>  
  
2.  <span data-ttu-id="2f48b-113">Dans le menu **Projet** , cliquez sur **Ajouter un contrôle utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-113">On the **Project** menu, click **Add User Control**.</span></span>  
  
3.  <span data-ttu-id="2f48b-114">Dans la boîte de dialogue **Ajouter un nouvel élément**, donnez au fichier de classe (fichier .vb ou .cs) le nom que vous souhaitez pour le contrôle composite.</span><span class="sxs-lookup"><span data-stu-id="2f48b-114">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>  
  
4.  <span data-ttu-id="2f48b-115">Sélectionnez le **ajouter** bouton pour créer le fichier de classe pour le contrôle composite.</span><span class="sxs-lookup"><span data-stu-id="2f48b-115">Select the **Add** button to create the class file for the composite control.</span></span>  
  
5.  <span data-ttu-id="2f48b-116">Utilisez la **boîte à outils** pour ajouter des contrôles à la surface du contrôle composite.</span><span class="sxs-lookup"><span data-stu-id="2f48b-116">Add controls from the **Toolbox** to the composite control surface.</span></span>  
  
6.  <span data-ttu-id="2f48b-117">Placez le code dans des procédures événementielles afin de gérer les événements déclenchés par le contrôle composite ou par ses contrôles constitutifs.</span><span class="sxs-lookup"><span data-stu-id="2f48b-117">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>  
  
7.  <span data-ttu-id="2f48b-118">Fermez le concepteur du contrôle composite et enregistrez le fichier lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="2f48b-118">Close the designer for the composite control, and save the file when you are prompted.</span></span>  
  
8.  <span data-ttu-id="2f48b-119">Dans le menu **Générer** , cliquez sur **Générer la solution**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-119">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="2f48b-120">Le projet doit être généré de sorte que les contrôles personnalisés apparaissent dans la **boîte à outils**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-120">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="2f48b-121">Utilisez l’onglet **DemoControlHost** de la **boîte à outils** pour ajouter des instances de votre contrôle sur `Form1`.</span><span class="sxs-lookup"><span data-stu-id="2f48b-121">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>  
  
### <a name="to-author-a-control-class-library"></a><span data-ttu-id="2f48b-122">Pour créer une bibliothèque de classes de contrôle</span><span class="sxs-lookup"><span data-stu-id="2f48b-122">To author a control class library</span></span>  
  
1.  <span data-ttu-id="2f48b-123">Ouvrez un nouveau projet de **bibliothèque de contrôles Windows**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-123">Open a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="2f48b-124">Par défaut, le projet contient un contrôle composite.</span><span class="sxs-lookup"><span data-stu-id="2f48b-124">By default, the project contains a composite control.</span></span>  
  
2.  <span data-ttu-id="2f48b-125">Ajoutez des contrôles et du code, comme décrit dans la procédure ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="2f48b-125">Add controls and code as described in the procedure above.</span></span>  
  
3.  <span data-ttu-id="2f48b-126">Sélectionnez un contrôle dont vous ne souhaitez pas modifier les classes qui héritent, puis définissez la propriété **Modifiers** de ce contrôle sur **Private**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-126">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>  
  
4.  <span data-ttu-id="2f48b-127">Créez la DLL.</span><span class="sxs-lookup"><span data-stu-id="2f48b-127">Build the DLL.</span></span>  
  
### <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="2f48b-128">Pour hériter d’un contrôle composite dans une bibliothèque de classes de contrôle</span><span class="sxs-lookup"><span data-stu-id="2f48b-128">To inherit from a composite control in a control class library</span></span>  
  
1.  <span data-ttu-id="2f48b-129">Dans le menu **Fichier**, pointez sur **Ajouter** et sélectionnez **Nouveau projet** pour ajouter un nouveau projet d’**application Windows** à la solution.</span><span class="sxs-lookup"><span data-stu-id="2f48b-129">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>  
  
2.  <span data-ttu-id="2f48b-130">Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le dossier **References** du nouveau projet, puis sélectionnez **Ajouter une référence** pour ouvrir la boîte de dialogue **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-130">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
3.  <span data-ttu-id="2f48b-131">Sélectionnez l’onglet **Projets** et double-cliquez sur votre projet de bibliothèque de contrôles.</span><span class="sxs-lookup"><span data-stu-id="2f48b-131">Select the **Projects** tab and double-click your control library project.</span></span>  
  
4.  <span data-ttu-id="2f48b-132">Dans le menu **Générer** , cliquez sur **Générer la solution**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-132">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="2f48b-133">Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur votre projet de bibliothèque de contrôles, puis sélectionnez **Ajouter un nouvel élément** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="2f48b-133">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>  
  
6.  <span data-ttu-id="2f48b-134">Sélectionnez le modèle **Contrôle utilisateur hérité** dans la boîte de dialogue **Ajouter un nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-134">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>  
  
7.  <span data-ttu-id="2f48b-135">Dans la boîte de dialogue **Sélecteur d’héritage**, double-cliquez sur le contrôle dont vous voulez hériter.</span><span class="sxs-lookup"><span data-stu-id="2f48b-135">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>  
  
     <span data-ttu-id="2f48b-136">Un nouveau contrôle est ajouté à votre projet.</span><span class="sxs-lookup"><span data-stu-id="2f48b-136">A new control is added to your project.</span></span>  
  
8.  <span data-ttu-id="2f48b-137">Ouvrez le concepteur visuel du nouveau contrôle et ajoutez d’autres contrôles constitutifs.</span><span class="sxs-lookup"><span data-stu-id="2f48b-137">Open the visual designer for the new control and add additional constituent controls.</span></span>  
  
     <span data-ttu-id="2f48b-138">Vous pouvez voir les contrôles constitutifs hérités du contrôle composite dans votre DLL, et vous pouvez modifier les propriétés des contrôles dont la propriété **Modifiers** est définie sur **Public**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-138">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="2f48b-139">Vous ne pouvez pas modifier les propriétés du contrôle dont la propriété **Modifiers** est définie sur **Private**.</span><span class="sxs-lookup"><span data-stu-id="2f48b-139">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f48b-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f48b-140">See Also</span></span>  
 [<span data-ttu-id="2f48b-141">Procédure pas à pas : création d'un contrôle composite à l'aide de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f48b-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="2f48b-142">Procédure pas à pas : création d'un contrôle composite à l'aide de Visual C#</span><span class="sxs-lookup"><span data-stu-id="2f48b-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="2f48b-143">Procédure pas à pas : héritage à partir d'un contrôle Windows Forms à l'aide de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f48b-143">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="2f48b-144">Procédure pas à pas : héritage d’un contrôle Windows Forms à l’aide de Visual C#</span><span class="sxs-lookup"><span data-stu-id="2f48b-144">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 [<span data-ttu-id="2f48b-145">Recommandations relatives au type de contrôle</span><span class="sxs-lookup"><span data-stu-id="2f48b-145">Control Type Recommendations</span></span>](../../../../docs/framework/winforms/controls/control-type-recommendations.md)  
 [<span data-ttu-id="2f48b-146">Guide pratique pour créer des contrôles pour des Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f48b-146">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="2f48b-147">Variétés de contrôles personnalisés</span><span class="sxs-lookup"><span data-stu-id="2f48b-147">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)

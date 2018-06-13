---
title: 'Comment : ancrer des contrôles aux Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: 6cb4c982cb4c9e2df8d0335738ca087733209bdc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532314"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="018c1-102">Comment : ancrer des contrôles aux Windows Forms</span><span class="sxs-lookup"><span data-stu-id="018c1-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="018c1-103">Vous pouvez ancrer des contrôles sur les bords de votre formulaire ou demander qu’ils remplissent le conteneur du contrôle (un formulaire ou un contrôle conteneur).</span><span class="sxs-lookup"><span data-stu-id="018c1-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="018c1-104">Par exemple, l’Explorateur Windows ancre son <xref:System.Windows.Forms.TreeView> contrôle sur le côté gauche de la fenêtre et son <xref:System.Windows.Forms.ListView> contrôle sur le côté droit de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="018c1-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="018c1-105">Utilisez le <xref:System.Windows.Forms.Control.Dock%2A> propriété pour tous les contrôles Windows Forms visibles définir le mode d’ancrage.</span><span class="sxs-lookup"><span data-stu-id="018c1-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="018c1-106">Les contrôles sont ancrés dans l’ordre z inverse.</span><span class="sxs-lookup"><span data-stu-id="018c1-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="018c1-107">Le <xref:System.Windows.Forms.Control.Dock%2A> propriété interagit avec le <xref:System.Windows.Forms.Control.AutoSize%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="018c1-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="018c1-108">Pour plus d’informations, consultez [vue d’ensemble de la propriété AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="018c1-108">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="018c1-109">Pour ancrer un contrôle</span><span class="sxs-lookup"><span data-stu-id="018c1-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="018c1-110">Sélectionnez le contrôle que vous souhaitez ancrer.</span><span class="sxs-lookup"><span data-stu-id="018c1-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="018c1-111">Dans la fenêtre Propriétés, cliquez sur la flèche située à droite de la <xref:System.Windows.Forms.Control.Dock%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="018c1-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="018c1-112">Un éditeur s’affiche qui affiche une série de zones représentant les bords et le centre de l’écran.</span><span class="sxs-lookup"><span data-stu-id="018c1-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="018c1-113">Cliquez sur le bouton qui représente le bord de l’écran où vous souhaitez ancrer le contrôle.</span><span class="sxs-lookup"><span data-stu-id="018c1-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="018c1-114">Pour remplir le contenu du formulaire du contrôle ou le contrôle conteneur, cliquez sur la zone centrale.</span><span class="sxs-lookup"><span data-stu-id="018c1-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="018c1-115">Cliquez sur **(aucun)** pour désactiver l’ancrage.</span><span class="sxs-lookup"><span data-stu-id="018c1-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="018c1-116">Le contrôle est automatiquement redimensionné pour s’ajuster les limites du bord ancré.</span><span class="sxs-lookup"><span data-stu-id="018c1-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="018c1-117">Les contrôles hérités doivent être `Protected` pour pouvoir être ancrée.</span><span class="sxs-lookup"><span data-stu-id="018c1-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="018c1-118">Pour modifier le niveau d’accès d’un contrôle, définissez son **modificateur** propriété dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="018c1-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018c1-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="018c1-119">See Also</span></span>  
 [<span data-ttu-id="018c1-120">Contrôles Windows Forms</span><span class="sxs-lookup"><span data-stu-id="018c1-120">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="018c1-121">Disposition des contrôles dans les Windows Forms</span><span class="sxs-lookup"><span data-stu-id="018c1-121">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="018c1-122">Création d'étiquettes et de raccourcis pour les contrôles Windows Forms</span><span class="sxs-lookup"><span data-stu-id="018c1-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="018c1-123">Contrôles à utiliser dans les Windows Forms</span><span class="sxs-lookup"><span data-stu-id="018c1-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="018c1-124">Classement par fonction des contrôles Windows Forms</span><span class="sxs-lookup"><span data-stu-id="018c1-124">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="018c1-125">Guide pratique pour ancrer des contrôles enfants dans un contrôle FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="018c1-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="018c1-126">Guide pratique pour ancrer et arrimer des contrôles enfants dans un contrôle TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="018c1-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="018c1-127">Vue d’ensemble de la propriété AutoSize</span><span class="sxs-lookup"><span data-stu-id="018c1-127">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="018c1-128">Guide pratique pour ancrer des contrôles sur des Windows Forms</span><span class="sxs-lookup"><span data-stu-id="018c1-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)

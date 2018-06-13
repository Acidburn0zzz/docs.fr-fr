---
title: Intégration de l'aide d'utilisateur dans les Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: b16ba14eea68083cd7bdfc91c88375406137f450
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527221"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="f34ed-102">Intégration de l'aide d'utilisateur dans les Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f34ed-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="f34ed-103">Un aspect essentiel mais souvent négligé, de créer des applications Windows est le système d’aide, car il s’agit où les utilisateurs ont activé pour vous aider à la fois de confusion.</span><span class="sxs-lookup"><span data-stu-id="f34ed-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="f34ed-104">Windows Forms prend en charge deux types différents d’aide, fourni par le [HelpProvider, composant](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f34ed-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="f34ed-105">Le premier consiste à pointer vers un fichier d’aide de code HTML ou HTML Help 1 le. *x* format ou ultérieur.</span><span class="sxs-lookup"><span data-stu-id="f34ed-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="f34ed-106">La seconde peut afficher brièvement « Qu’est-ce »-tapez Help sur chacun des contrôles. Ceci est particulièrement utile sur les boîtes de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f34ed-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="f34ed-107">Les deux types d’aide peuvent être utilisés sur le même formulaire.</span><span class="sxs-lookup"><span data-stu-id="f34ed-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="f34ed-108">En outre, le [composant ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) peut être utilisé pour fournir une aide individuelle pour les contrôles dans les Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f34ed-108">Additionally, the [ToolTip Component](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f34ed-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f34ed-109">In This Section</span></span>  
 [<span data-ttu-id="f34ed-110">Guide pratique pour fournir de l'aide dans une application Windows</span><span class="sxs-lookup"><span data-stu-id="f34ed-110">How to: Provide Help in a Windows Application</span></span>](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="f34ed-111">Explique comment utiliser le `HelpProvider` composant à lier des contrôles à des fichiers dans un système d’aide.</span><span class="sxs-lookup"><span data-stu-id="f34ed-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="f34ed-112">Guide pratique pour afficher l’aide contextuelle</span><span class="sxs-lookup"><span data-stu-id="f34ed-112">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 <span data-ttu-id="f34ed-113">Explique comment utiliser le `HelpProvider` composant pour afficher l’aide contextuelle dans les Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f34ed-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="f34ed-114">Affichage sous forme d’info-bulles de l’aide relative aux contrôles</span><span class="sxs-lookup"><span data-stu-id="f34ed-114">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 <span data-ttu-id="f34ed-115">Décrit l’utilisation de la `ToolTip` composant pour afficher l’aide spécifique du contrôle.</span><span class="sxs-lookup"><span data-stu-id="f34ed-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f34ed-116">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f34ed-116">Related Sections</span></span>  
 [<span data-ttu-id="f34ed-117">HelpProvider, composant</span><span class="sxs-lookup"><span data-stu-id="f34ed-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="f34ed-118">Explique les principes fondamentaux de la `HelpProvider` composant.</span><span class="sxs-lookup"><span data-stu-id="f34ed-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="f34ed-119">ToolTip, composant</span><span class="sxs-lookup"><span data-stu-id="f34ed-119">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="f34ed-120">Explique les principes fondamentaux de la `ToolTip` composant.</span><span class="sxs-lookup"><span data-stu-id="f34ed-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="f34ed-121">Vue d'ensemble des Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f34ed-121">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 <span data-ttu-id="f34ed-122">Explique les notions de base des Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f34ed-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="f34ed-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f34ed-123">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)  
 <span data-ttu-id="f34ed-124">Fournit une vue d’ensemble des Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f34ed-124">Provides an overview of Windows Forms.</span></span>

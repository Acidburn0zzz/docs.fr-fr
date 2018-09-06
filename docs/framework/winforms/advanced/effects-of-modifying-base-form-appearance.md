---
title: Conséquences de la modification de l’aspect d’un formulaire de base
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: adaf9224fd340c6ea4342e2591806a7c877e83ff
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43746170"
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a><span data-ttu-id="e52f3-102">Conséquences de la modification de l’aspect d’un formulaire de base</span><span class="sxs-lookup"><span data-stu-id="e52f3-102">Effects of Modifying a Base Form&#39;s Appearance</span></span>
<span data-ttu-id="e52f3-103">Pendant le développement d’applications, vous êtes souvent amené à modifier l’apparence du formulaire de base dont héritent d’autres formulaires du projet (ou d’autres projets).</span><span class="sxs-lookup"><span data-stu-id="e52f3-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="e52f3-104">Au moment du design, les modifications apportées à l’aspect du formulaire de base (qu’il s’agisse de la définition de propriétés ou de l’addition et de la soustraction de contrôles) sont répercutées dans les formulaires hérités lors de la génération du projet contenant le formulaire de base.</span><span class="sxs-lookup"><span data-stu-id="e52f3-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="e52f3-105">Il ne suffit pas d’enregistrer les modifications apportées au formulaire de base.</span><span class="sxs-lookup"><span data-stu-id="e52f3-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="e52f3-106">Pour générer un projet, sélectionnez **Générer** dans le menu **Générer**.</span><span class="sxs-lookup"><span data-stu-id="e52f3-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e52f3-107">Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée.</span><span class="sxs-lookup"><span data-stu-id="e52f3-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e52f3-108">Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="e52f3-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e52f3-109">Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e52f3-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
 <span data-ttu-id="e52f3-110">Les modifications apportées au formulaire à l’exécution n’ont aucune incidence sur les formulaires hérités déjà instanciés.</span><span class="sxs-lookup"><span data-stu-id="e52f3-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e52f3-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e52f3-111">See Also</span></span>  
 [<span data-ttu-id="e52f3-112">base</span><span class="sxs-lookup"><span data-stu-id="e52f3-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="e52f3-113">Comment : hériter des Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e52f3-113">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="e52f3-114">Héritage visuel des Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e52f3-114">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)

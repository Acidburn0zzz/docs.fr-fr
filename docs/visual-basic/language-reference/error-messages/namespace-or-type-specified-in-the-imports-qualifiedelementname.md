---
title: Namespace ou le type spécifié dans les Imports &#39; &lt;nom_élément_qualifié&gt; &#39; ne&#39;t contient aucun membre public ou est introuvable
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 8be0df5cbe4b8d4a640c9b6c2e126b3828254fd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595103"
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="58bc2-102">Namespace ou le type spécifié dans les Imports &#39; &lt;nom_élément_qualifié&gt; &#39; ne&#39;t contient aucun membre public ou est introuvable</span><span class="sxs-lookup"><span data-stu-id="58bc2-102">Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found</span></span>
<span data-ttu-id="58bc2-103">Namespace ou le type spécifié dans les Imports'\<nom_élément_qualifié >' ne contient aucun membre public ou est introuvable.</span><span class="sxs-lookup"><span data-stu-id="58bc2-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="58bc2-104">Assurez-vous que l’espace de noms ou le type est défini et qu’il contient au moins un membre public.</span><span class="sxs-lookup"><span data-stu-id="58bc2-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="58bc2-105">Assurez-vous que le nom d’alias ne contient d’autres alias.</span><span class="sxs-lookup"><span data-stu-id="58bc2-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="58bc2-106">Un `Imports` instruction spécifie un élément conteneur qui ne peut pas être trouvé ou ne définit pas `Public` membres.</span><span class="sxs-lookup"><span data-stu-id="58bc2-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="58bc2-107">A *contenant l’élément* peut être un espace de noms, une classe, une structure, un module, une interface ou une énumération.</span><span class="sxs-lookup"><span data-stu-id="58bc2-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="58bc2-108">L’élément conteneur contient des membres, tels que des variables, des procédures ou d’autres éléments qui le contient.</span><span class="sxs-lookup"><span data-stu-id="58bc2-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="58bc2-109">L’objectif de l’importation est pour permettre à votre code pour accéder aux membres de type ou espace de noms sans avoir à les inclure.</span><span class="sxs-lookup"><span data-stu-id="58bc2-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="58bc2-110">Votre projet devrez peut-être également ajouter une référence à l’espace de noms ou type.</span><span class="sxs-lookup"><span data-stu-id="58bc2-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="58bc2-111">Pour plus d’informations, consultez « Importation d’éléments conteneurs » dans [références aux éléments de déclaré](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="58bc2-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="58bc2-112">Si le compilateur ne peut pas trouver l’élément conteneur spécifié, il ne peut pas résoudre les références qui l’utilisent.</span><span class="sxs-lookup"><span data-stu-id="58bc2-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="58bc2-113">Si elle recherche l’élément, mais l’élément n’expose pas `Public` membres, aucune référence peut être réussie.</span><span class="sxs-lookup"><span data-stu-id="58bc2-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="58bc2-114">Dans les deux cas, il est sans signification pour importer l’élément.</span><span class="sxs-lookup"><span data-stu-id="58bc2-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="58bc2-115">Gardez à l’esprit que si vous importez un élément de conteneur et lui assignez un alias d’importation, puis vous ne pouvez pas utiliser cet alias d’importation pour importer un autre élément.</span><span class="sxs-lookup"><span data-stu-id="58bc2-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="58bc2-116">Le code suivant génère une erreur du compilateur.</span><span class="sxs-lookup"><span data-stu-id="58bc2-116">The following code generates a compiler error.</span></span>  
  
 <span data-ttu-id="58bc2-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span><span class="sxs-lookup"><span data-stu-id="58bc2-117">`Imports`   `winfrm`   `= System.Windows.Forms`</span></span>  
  
 <span data-ttu-id="58bc2-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span><span class="sxs-lookup"><span data-stu-id="58bc2-118">`' The following statement is`   `INVALID`   `because it reuses an import alias.`</span></span>  
  
 <span data-ttu-id="58bc2-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span><span class="sxs-lookup"><span data-stu-id="58bc2-119">`Imports behav =`   `winfrm`  `.Design.Behavior`</span></span>  
  
 <span data-ttu-id="58bc2-120">**ID d’erreur :** BC40056</span><span class="sxs-lookup"><span data-stu-id="58bc2-120">**Error ID:** BC40056</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="58bc2-121">Pour corriger cette erreur</span><span class="sxs-lookup"><span data-stu-id="58bc2-121">To correct this error</span></span>  
  
1.  <span data-ttu-id="58bc2-122">Vérifiez que l’élément conteneur est accessible à partir de votre projet.</span><span class="sxs-lookup"><span data-stu-id="58bc2-122">Verify that the containing element is accessible from your project.</span></span>  
  
2.  <span data-ttu-id="58bc2-123">Vérifiez que la spécification de l’élément conteneur n’inclut pas les alias d’importation à partir d’une autre importation.</span><span class="sxs-lookup"><span data-stu-id="58bc2-123">Verify that the specification of the containing element does not include any import alias from another import.</span></span>  
  
3.  <span data-ttu-id="58bc2-124">Vérifiez que l’élément conteneur expose au moins un `Public` membre.</span><span class="sxs-lookup"><span data-stu-id="58bc2-124">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58bc2-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58bc2-125">See Also</span></span>  
 [<span data-ttu-id="58bc2-126">Imports (instruction) (espace de noms et type .NET)</span><span class="sxs-lookup"><span data-stu-id="58bc2-126">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="58bc2-127">Namespace (instruction)</span><span class="sxs-lookup"><span data-stu-id="58bc2-127">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="58bc2-128">Public</span><span class="sxs-lookup"><span data-stu-id="58bc2-128">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="58bc2-129">Espaces de noms dans Visual Basic</span><span class="sxs-lookup"><span data-stu-id="58bc2-129">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="58bc2-130">Références aux éléments déclarés</span><span class="sxs-lookup"><span data-stu-id="58bc2-130">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

---
title: -définir (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4de37c58543aed9ed13be8b0d2bcec9830ca9082
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656098"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="b2f89-102">-définir (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2f89-102">-define (Visual Basic)</span></span>
<span data-ttu-id="b2f89-103">Définit des constantes conditionnelles du compilateur.</span><span class="sxs-lookup"><span data-stu-id="b2f89-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2f89-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b2f89-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2f89-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="b2f89-105">Arguments</span></span>  
  
|<span data-ttu-id="b2f89-106">Terme</span><span class="sxs-lookup"><span data-stu-id="b2f89-106">Term</span></span>|<span data-ttu-id="b2f89-107">Définition</span><span class="sxs-lookup"><span data-stu-id="b2f89-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="b2f89-108">Requis.</span><span class="sxs-lookup"><span data-stu-id="b2f89-108">Required.</span></span> <span data-ttu-id="b2f89-109">Symbole à définir.</span><span class="sxs-lookup"><span data-stu-id="b2f89-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="b2f89-110">Facultatif.</span><span class="sxs-lookup"><span data-stu-id="b2f89-110">Optional.</span></span> <span data-ttu-id="b2f89-111">Valeur à affecter au `symbol`.</span><span class="sxs-lookup"><span data-stu-id="b2f89-111">The value to assign `symbol`.</span></span> <span data-ttu-id="b2f89-112">Si `value` est une chaîne, elle doit être entourée par des séquences de barre oblique inverse/guillemets (\\») au lieu des guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="b2f89-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="b2f89-113">Si aucune valeur n'est spécifiée, il prend la valeur True.</span><span class="sxs-lookup"><span data-stu-id="b2f89-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2f89-114">Notes</span><span class="sxs-lookup"><span data-stu-id="b2f89-114">Remarks</span></span>  
 <span data-ttu-id="b2f89-115">L'option `-define` revient à utiliser la directive de préprocesseur `#Const` dans votre fichier source, excepté que les constantes définies avec `-define` sont publiques et s'appliquent à tous les fichiers du projet.</span><span class="sxs-lookup"><span data-stu-id="b2f89-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="b2f89-116">Vous pouvez utiliser les symboles créés par cette option avec la directive `#If`...`Then`...`#Else` pour effectuer une compilation conditionnelle des fichiers sources.</span><span class="sxs-lookup"><span data-stu-id="b2f89-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="b2f89-117">`-d` est la forme abrégée de `-define`.</span><span class="sxs-lookup"><span data-stu-id="b2f89-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="b2f89-118">Vous pouvez définir plusieurs symboles avec `-define` en utilisant une virgule pour séparer les définitions de symbole.</span><span class="sxs-lookup"><span data-stu-id="b2f89-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="b2f89-119">Pour définir /define dans l'environnement de développement intégré Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2f89-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="b2f89-120">1.  Sélectionnez un projet dans l' **Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="b2f89-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b2f89-121">Dans le menu **Projet**, cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b2f89-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="b2f89-122">2.  Cliquez sur l’onglet **Compiler**.</span><span class="sxs-lookup"><span data-stu-id="b2f89-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="b2f89-123">3.  Cliquez sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="b2f89-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="b2f89-124">4.  Modifiez la valeur dans la **constantes personnalisées** boîte.</span><span class="sxs-lookup"><span data-stu-id="b2f89-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2f89-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="b2f89-125">Example</span></span>  
 <span data-ttu-id="b2f89-126">Le code suivant définit deux constantes de compilation conditionnelle, puis les utilise.</span><span class="sxs-lookup"><span data-stu-id="b2f89-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b2f89-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2f89-127">See Also</span></span>  
 [<span data-ttu-id="b2f89-128">Compilateur de ligne de commande de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2f89-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b2f89-129">#If...Then...#Else, directives</span><span class="sxs-lookup"><span data-stu-id="b2f89-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="b2f89-130">#Const (directive)</span><span class="sxs-lookup"><span data-stu-id="b2f89-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="b2f89-131">Exemples de lignes de commande de compilation</span><span class="sxs-lookup"><span data-stu-id="b2f89-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

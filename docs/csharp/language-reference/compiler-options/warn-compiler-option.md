---
title: -warn (Options du compilateur C#)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 14656fa25ea1d01339bd63efb999e938e1243db8
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43331939"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="351a7-102">-warn (Options du compilateur C#)</span><span class="sxs-lookup"><span data-stu-id="351a7-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="351a7-103">L’option **-warn** spécifie le niveau d’avertissement que le compilateur doit afficher.</span><span class="sxs-lookup"><span data-stu-id="351a7-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="351a7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="351a7-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="351a7-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="351a7-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="351a7-106">Niveau d’avertissement que vous souhaitez afficher pour la compilation : les nombres inférieurs affichent uniquement les avertissements ayant un niveau de gravité élevé ; les nombres supérieurs affichent davantage d’avertissements.</span><span class="sxs-lookup"><span data-stu-id="351a7-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="351a7-107">Les valeurs valides vont de 0 à 4 :</span><span class="sxs-lookup"><span data-stu-id="351a7-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="351a7-108">Niveau d’avertissement</span><span class="sxs-lookup"><span data-stu-id="351a7-108">Warning level</span></span>|<span data-ttu-id="351a7-109">Signification</span><span class="sxs-lookup"><span data-stu-id="351a7-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="351a7-110">0</span><span class="sxs-lookup"><span data-stu-id="351a7-110">0</span></span>|<span data-ttu-id="351a7-111">Désactive l’émission de tous les messages d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="351a7-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="351a7-112">1</span><span class="sxs-lookup"><span data-stu-id="351a7-112">1</span></span>|<span data-ttu-id="351a7-113">Affiche les messages d’avertissement graves.</span><span class="sxs-lookup"><span data-stu-id="351a7-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="351a7-114">2</span><span class="sxs-lookup"><span data-stu-id="351a7-114">2</span></span>|<span data-ttu-id="351a7-115">Affiche les avertissements de niveau 1, ainsi que certains avertissements moins graves, tels que les avertissements concernant le masquage de membres de classe.</span><span class="sxs-lookup"><span data-stu-id="351a7-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="351a7-116">3</span><span class="sxs-lookup"><span data-stu-id="351a7-116">3</span></span>|<span data-ttu-id="351a7-117">Affiche les avertissements de niveau 2, ainsi que certains avertissements moins graves, tels que les avertissements concernant les expressions toujours évaluées à `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="351a7-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="351a7-118">4 (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="351a7-118">4 (the default)</span></span>|<span data-ttu-id="351a7-119">Affiche les avertissements de niveau 3, ainsi que les avertissements d’information.</span><span class="sxs-lookup"><span data-stu-id="351a7-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="351a7-120">Notes</span><span class="sxs-lookup"><span data-stu-id="351a7-120">Remarks</span></span>  
 <span data-ttu-id="351a7-121">Pour obtenir des informations sur une erreur ou un avertissement, vous pouvez rechercher le code d’erreur dans l’index de l’aide.</span><span class="sxs-lookup"><span data-stu-id="351a7-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="351a7-122">Il existe d’autres façons d’obtenir des informations sur une erreur ou un avertissement, qui sont décrites dans [Erreurs du compilateur C#](../../../csharp/language-reference/compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="351a7-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="351a7-123">Utilisez [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) pour traiter tous les avertissements comme des erreurs.</span><span class="sxs-lookup"><span data-stu-id="351a7-123">Use [-warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="351a7-124">Utilisez [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) pour désactiver certains avertissements.</span><span class="sxs-lookup"><span data-stu-id="351a7-124">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="351a7-125">**-w** est la forme abrégée de **-warn**.</span><span class="sxs-lookup"><span data-stu-id="351a7-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="351a7-126">Pour définir cette option du compilateur dans l'environnement de développement Visual Studio</span><span class="sxs-lookup"><span data-stu-id="351a7-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="351a7-127">Ouvrez la page **Propriétés** du projet.</span><span class="sxs-lookup"><span data-stu-id="351a7-127">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="351a7-128">Cliquez sur la page de propriétés **Générer**.</span><span class="sxs-lookup"><span data-stu-id="351a7-128">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="351a7-129">Modifiez la propriété **Niveau d’avertissement**.</span><span class="sxs-lookup"><span data-stu-id="351a7-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="351a7-130">Pour plus d’informations sur la façon de définir cette option du compilateur par programmation, consultez <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="351a7-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="351a7-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="351a7-131">Example</span></span>  
 <span data-ttu-id="351a7-132">Compilez `in.cs` et faites en sorte que le compilateur n’affiche que les avertissements de niveau 1 :</span><span class="sxs-lookup"><span data-stu-id="351a7-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="351a7-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="351a7-133">See Also</span></span>  

- [<span data-ttu-id="351a7-134">Options du compilateur C#</span><span class="sxs-lookup"><span data-stu-id="351a7-134">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="351a7-135">Gestion des propriétés des projets et des solutions</span><span class="sxs-lookup"><span data-stu-id="351a7-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

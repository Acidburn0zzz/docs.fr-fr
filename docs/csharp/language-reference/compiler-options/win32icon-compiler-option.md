---
title: "-win32icon (Options du compilateur C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2ec19bacb975732f2ae04b8cefbfaeaa518b6f15
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="21af4-102">-win32icon (Options du compilateur C#)</span><span class="sxs-lookup"><span data-stu-id="21af4-102">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="21af4-103">L’option **-win32icon** insère un fichier .ico dans le fichier de sortie, ce qui lui donne l’apparence souhaitée dans l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="21af4-103">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21af4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="21af4-104">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="21af4-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="21af4-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="21af4-106">Fichier .ico que vous voulez ajouter à votre fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="21af4-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21af4-107">Notes</span><span class="sxs-lookup"><span data-stu-id="21af4-107">Remarks</span></span>  
 <span data-ttu-id="21af4-108">Un fichier .ico peut être créé avec le [compilateur de ressources](https://msdn.microsoft.com/library/aa381042.aspx).</span><span class="sxs-lookup"><span data-stu-id="21af4-108">An .ico file can be created with the [Resource Compiler](https://msdn.microsoft.com/library/aa381042.aspx).</span></span> <span data-ttu-id="21af4-109">Le compilateur de ressources est appelé quand vous compilez un programme Visual C++ ; un fichier .ico est alors créé à partir du fichier .rc.</span><span class="sxs-lookup"><span data-stu-id="21af4-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="21af4-110">Consultez [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) pour référencer ou [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) pour attacher un fichier de ressources .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21af4-110">See [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="21af4-111">Consultez [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) pour importer un fichier .res.</span><span class="sxs-lookup"><span data-stu-id="21af4-111">See [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="21af4-112">Pour définir cette option du compilateur dans l'environnement de développement Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21af4-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="21af4-113">Ouvrez les pages **Propriétés** du projet.</span><span class="sxs-lookup"><span data-stu-id="21af4-113">Open the project's **Properties** pages.</span></span>  
  
2.  <span data-ttu-id="21af4-114">Cliquez sur la page de propriétés **Application**.</span><span class="sxs-lookup"><span data-stu-id="21af4-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="21af4-115">Modifiez la propriété **Icône d’application**.</span><span class="sxs-lookup"><span data-stu-id="21af4-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="21af4-116">Pour plus d’informations sur la façon de définir cette option du compilateur par programmation, consultez <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="21af4-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21af4-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="21af4-117">Example</span></span>  
 <span data-ttu-id="21af4-118">Compilez `in.cs` et attachez un fichier .ico `rf.ico` afin de générer le fichier `in.exe` :</span><span class="sxs-lookup"><span data-stu-id="21af4-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="21af4-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21af4-119">See Also</span></span>  
 [<span data-ttu-id="21af4-120">Options du compilateur C#</span><span class="sxs-lookup"><span data-stu-id="21af4-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="21af4-121">Gestion des propriétés des projets et des solutions</span><span class="sxs-lookup"><span data-stu-id="21af4-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

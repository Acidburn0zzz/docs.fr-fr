---
title: Guide pratique pour générer un assembly à fichier unique
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: ''
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80fa584a21a3bdfb9392021959d777139daafd04
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="d2364-102">Guide pratique pour générer un assembly à fichier unique</span><span class="sxs-lookup"><span data-stu-id="d2364-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="d2364-103">Un assembly à fichier unique, qui est le type d’assembly le plus simple, contient l’implémentation et les informations de type, ainsi que le [manifeste d’assembly](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="d2364-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="d2364-104">Vous pouvez utiliser des compilateurs de ligne de commande ou [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] pour créer un assembly à fichier unique.</span><span class="sxs-lookup"><span data-stu-id="d2364-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="d2364-105">Par défaut, le compilateur crée un fichier d’assembly avec une extension .exe.</span><span class="sxs-lookup"><span data-stu-id="d2364-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]<span data-ttu-id="d2364-106"> pour C# et Visual Basic peut être utilisé uniquement pour créer des assemblys à fichier unique.</span><span class="sxs-lookup"><span data-stu-id="d2364-106"> for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="d2364-107">Si vous souhaitez créer des assemblys multifichiers, vous devez utiliser les compilateurs de ligne de commande ou [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] pour Visual C++.</span><span class="sxs-lookup"><span data-stu-id="d2364-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="d2364-108">Les procédures suivantes montrent comment créer des assemblys à fichier unique à l’aide des compilateurs de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="d2364-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="d2364-109">Pour créer un assembly avec une extension .exe</span><span class="sxs-lookup"><span data-stu-id="d2364-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="d2364-110">À l'invite de commandes, tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d2364-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="d2364-111">\<*commande_du_compilateur*> \<*nom_du_module*></span><span class="sxs-lookup"><span data-stu-id="d2364-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="d2364-112">Dans cette commande, *commande_du_compilateur* est la commande du compilateur pour le langage utilisé dans votre module de code, et *nom_du_module* est le nom du module de code à compiler dans l’assembly.</span><span class="sxs-lookup"><span data-stu-id="d2364-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="d2364-113">L’exemple suivant crée un assembly nommé `myCode.exe` à partir d’un module de code nommé `myCode`.</span><span class="sxs-lookup"><span data-stu-id="d2364-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```console
csc myCode.cs  
```  

```console
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="d2364-114">Pour créer un assembly avec une extension .exe et spécifier le nom du fichier de sortie</span><span class="sxs-lookup"><span data-stu-id="d2364-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="d2364-115">À l'invite de commandes, tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d2364-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="d2364-116">\<*commande_du_compilateur*> **/out:**\<*nom_du_fichier*> \<*nom_du_module*></span><span class="sxs-lookup"><span data-stu-id="d2364-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="d2364-117">Dans cette commande, *commande_du_compilateur* est la commande du compilateur pour le langage utilisé dans votre module de code, *nom_du_fichier* est le nom du fichier de sortie, et *nom_du_module* est le nom du module de code à compiler dans l’assembly.</span><span class="sxs-lookup"><span data-stu-id="d2364-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="d2364-118">L’exemple suivant crée un assembly nommé `myAssembly.exe` à partir d’un module de code nommé `myCode`.</span><span class="sxs-lookup"><span data-stu-id="d2364-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myAssembly.exe myCode.cs  
```  
  
```console
vbc -out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="d2364-119">Création d’assemblys de bibliothèque</span><span class="sxs-lookup"><span data-stu-id="d2364-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="d2364-120">Un assembly de bibliothèque est similaire à une bibliothèque de classes.</span><span class="sxs-lookup"><span data-stu-id="d2364-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="d2364-121">Il contient des types qui seront référencés par d’autres assemblys, mais n’a aucun point d’entrée pour commencer l’exécution.</span><span class="sxs-lookup"><span data-stu-id="d2364-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="d2364-122">Pour créer un assembly de bibliothèque</span><span class="sxs-lookup"><span data-stu-id="d2364-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="d2364-123">À l'invite de commandes, tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d2364-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="d2364-124">\<*commande_du_compilateur*> **-t:library** \<*nom_du_module*></span><span class="sxs-lookup"><span data-stu-id="d2364-124">\<*compiler command*> **-t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="d2364-125">Dans cette commande, *commande_du_compilateur* est la commande du compilateur pour le langage utilisé dans votre module de code, et *nom_du_module* est le nom du module de code à compiler dans l’assembly.</span><span class="sxs-lookup"><span data-stu-id="d2364-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="d2364-126">Vous pouvez également utiliser d’autres options du compilateur, telles que l’option **-out:**.</span><span class="sxs-lookup"><span data-stu-id="d2364-126">You can also use other compiler options, such as the **-out:** option.</span></span>  
  
 <span data-ttu-id="d2364-127">L’exemple suivant crée un assembly de bibliothèque nommé `myCodeAssembly.dll` à partir d’un module de code nommé `myCode`.</span><span class="sxs-lookup"><span data-stu-id="d2364-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myCodeLibrary.dll -t:library myCode.cs  
```  
  
```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2364-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2364-128">See Also</span></span>  
 [<span data-ttu-id="d2364-129">Création d’assemblys</span><span class="sxs-lookup"><span data-stu-id="d2364-129">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="d2364-130">Assemblys multifichiers</span><span class="sxs-lookup"><span data-stu-id="d2364-130">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 [<span data-ttu-id="d2364-131">Guide pratique pour générer un assembly multifichier</span><span class="sxs-lookup"><span data-stu-id="d2364-131">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="d2364-132">Programmation à l’aide d’assemblys</span><span class="sxs-lookup"><span data-stu-id="d2364-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)

---
title: Contenu d'un assembly
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aed7e1e9e85f746c4b55b10c59dd82e85565b00
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194837"
---
# <a name="assembly-contents"></a><span data-ttu-id="4ca39-102">Contenu d'un assembly</span><span class="sxs-lookup"><span data-stu-id="4ca39-102">Assembly Contents</span></span>
<span data-ttu-id="4ca39-103">En général, un assembly statique peut comporter les quatre éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4ca39-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="4ca39-104">Le [manifeste d’assembly](../../../docs/framework/app-domains/assembly-manifest.md), qui contient les métadonnées de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="4ca39-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="4ca39-105">les métadonnées des types ;</span><span class="sxs-lookup"><span data-stu-id="4ca39-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="4ca39-106">le code MSIL (Microsoft Intermediate Language) qui implémente les types ;</span><span class="sxs-lookup"><span data-stu-id="4ca39-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="4ca39-107">un ensemble de ressources.</span><span class="sxs-lookup"><span data-stu-id="4ca39-107">A set of resources.</span></span>  
  
 <span data-ttu-id="4ca39-108">Seul le manifeste d'assembly est requis, mais soit les types, soit les ressources sont nécessaires pour donner à l'assembly des fonctionnalités significatives.</span><span class="sxs-lookup"><span data-stu-id="4ca39-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="4ca39-109">Il existe plusieurs modes de regroupement de ces éléments dans un assembly.</span><span class="sxs-lookup"><span data-stu-id="4ca39-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="4ca39-110">Vous pouvez regrouper tous les éléments dans un seul fichier physique, comme dans l'illustration ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4ca39-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 <span data-ttu-id="4ca39-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span><span class="sxs-lookup"><span data-stu-id="4ca39-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span></span>  
<span data-ttu-id="4ca39-112">Assembly monofichier</span><span class="sxs-lookup"><span data-stu-id="4ca39-112">Single-file assembly</span></span>  
  
 <span data-ttu-id="4ca39-113">Les éléments d'un assembly peuvent également figurer dans plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="4ca39-113">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="4ca39-114">Ces fichiers peuvent être des modules de code compilé (.netmodule), des ressources (telles que des fichiers .bmp ou .jpg) ou d'autres fichiers requis par l'application.</span><span class="sxs-lookup"><span data-stu-id="4ca39-114">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="4ca39-115">Créez un assembly multifichier lorsque vous souhaitez associer des modules écrits dans différents langages et optimiser le téléchargement d'une application en mettant les types rarement utilisés dans un module qui n'est téléchargé qu'en cas de nécessité.</span><span class="sxs-lookup"><span data-stu-id="4ca39-115">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="4ca39-116">Dans l'illustration ci-dessous, le développeur d'une application hypothétique a choisi de placer le code d'utilitaire dans un module distinct et de conserver un fichier de ressources volumineux (dans ce cas une image .bmp) dans son fichier d'origine.</span><span class="sxs-lookup"><span data-stu-id="4ca39-116">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="4ca39-117">Le .NET Framework ne télécharge un fichier que lorsqu'il est référencé ; le maintien du code peu référencé dans un fichier distinct de l'application optimise le téléchargement du code.</span><span class="sxs-lookup"><span data-stu-id="4ca39-117">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 <span data-ttu-id="4ca39-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span><span class="sxs-lookup"><span data-stu-id="4ca39-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span></span>  
<span data-ttu-id="4ca39-119">Assembly multifichier</span><span class="sxs-lookup"><span data-stu-id="4ca39-119">Multifile assembly</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ca39-120">Les fichiers qui composent un assembly multifichier ne sont pas physiquement reliés par le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="4ca39-120">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="4ca39-121">Ils sont à la place reliés par le manifeste d'assembly et le Common Language Runtime les manage en tant qu'unité.</span><span class="sxs-lookup"><span data-stu-id="4ca39-121">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="4ca39-122">Dans cette illustration, les trois fichiers appartiennent à un assembly, comme décrit dans le manifeste de l'assembly contenu dans MyAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="4ca39-122">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="4ca39-123">Pour le système de fichiers, il s'agit de trois fichiers distincts.</span><span class="sxs-lookup"><span data-stu-id="4ca39-123">To the file system, they are three separate files.</span></span> <span data-ttu-id="4ca39-124">Notez que le fichier Util.netmodule a été compilé comme un module car il ne contient pas d'information sur l'assembly.</span><span class="sxs-lookup"><span data-stu-id="4ca39-124">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="4ca39-125">Lorsque l'assembly a été créé, le manifeste de l'assembly a été ajouté à MyAssembly.dll, en indiquant sa relation avec Util.netmodule et Graphic.bmp.</span><span class="sxs-lookup"><span data-stu-id="4ca39-125">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="4ca39-126">Actuellement, à mesure que vous concevez votre code source, vous prenez des décisions explicites concernant le mode de partition des fonctionnalités de votre application dans un ou plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="4ca39-126">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="4ca39-127">Lors du design de code .NET Framework, vous prendrez des décisions similaires sur le mode de partition des fonctionnalités dans un ou plusieurs assemblys.</span><span class="sxs-lookup"><span data-stu-id="4ca39-127">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca39-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ca39-128">See Also</span></span>  
- [<span data-ttu-id="4ca39-129">Assemblys dans le Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="4ca39-129">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
- [<span data-ttu-id="4ca39-130">Manifeste d’assembly</span><span class="sxs-lookup"><span data-stu-id="4ca39-130">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)  
- [<span data-ttu-id="4ca39-131">Aspects de la sécurité des assemblys</span><span class="sxs-lookup"><span data-stu-id="4ca39-131">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)

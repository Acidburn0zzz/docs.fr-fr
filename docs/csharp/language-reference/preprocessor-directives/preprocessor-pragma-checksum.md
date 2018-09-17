---
title: '##pragma checksum (référence C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 28a9ccfb9d36e648304a177294904ab1b7f18892
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45614501"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="a4776-102">#pragma checksum (Référence C#)</span><span class="sxs-lookup"><span data-stu-id="a4776-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="a4776-103">Génère des sommes de contrôle pour les fichiers sources afin de faciliter le débogage des pages [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4776-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4776-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a4776-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4776-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a4776-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="a4776-106">Nom du fichier dont les modifications ou les mises à jour doivent faire l’objet d’une surveillance.</span><span class="sxs-lookup"><span data-stu-id="a4776-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="a4776-107">Identificateur global unique (GUID) du fichier pour l’algorithme de hachage.</span><span class="sxs-lookup"><span data-stu-id="a4776-107">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="a4776-108">Chaîne de chiffres hexadécimaux représentant les octets de la somme de contrôle.</span><span class="sxs-lookup"><span data-stu-id="a4776-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="a4776-109">Doit être un nombre pair de chiffres hexadécimaux.</span><span class="sxs-lookup"><span data-stu-id="a4776-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="a4776-110">S’il y a un nombre impair de chiffres, un avertissement est généré au moment de la compilation et la directive est ignorée.</span><span class="sxs-lookup"><span data-stu-id="a4776-110">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4776-111">Notes</span><span class="sxs-lookup"><span data-stu-id="a4776-111">Remarks</span></span>  
 <span data-ttu-id="a4776-112">Le débogueur Visual Studio utilise une somme de contrôle pour s’assurer de toujours trouver la bonne source.</span><span class="sxs-lookup"><span data-stu-id="a4776-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="a4776-113">Le compilateur calcule la somme de contrôle pour un fichier source, puis envoie la sortie vers le fichier de base de données du programme (PDB).</span><span class="sxs-lookup"><span data-stu-id="a4776-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="a4776-114">Le débogueur utilise ensuite le fichier PDB à comparer avec la somme de contrôle qu’il calcule pour le fichier source.</span><span class="sxs-lookup"><span data-stu-id="a4776-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="a4776-115">Cette solution n’est pas possible pour les projets [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)], car la somme de contrôle est calculée pour le fichier source généré, au lieu du fichier .aspx.</span><span class="sxs-lookup"><span data-stu-id="a4776-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="a4776-116">Pour résoudre ce problème, `#pragma checksum` fournit une prise en charge de la somme de contrôle pour les pages [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4776-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="a4776-117">Quand vous créez un projet [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] dans Visual C#, le fichier source généré contient une somme de contrôle pour le fichier .aspx, à partir duquel la source est générée.</span><span class="sxs-lookup"><span data-stu-id="a4776-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="a4776-118">Le compilateur écrit ensuite ces informations dans le fichier PDB.</span><span class="sxs-lookup"><span data-stu-id="a4776-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="a4776-119">Si le compilateur ne rencontre aucune directive `#pragma checksum` dans le fichier, il calcule la somme de contrôle et écrit la valeur dans le fichier PDB.</span><span class="sxs-lookup"><span data-stu-id="a4776-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4776-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="a4776-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4776-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4776-121">See Also</span></span>

- [<span data-ttu-id="a4776-122">Référence C#</span><span class="sxs-lookup"><span data-stu-id="a4776-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a4776-123">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="a4776-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a4776-124">Directives de préprocesseur C#</span><span class="sxs-lookup"><span data-stu-id="a4776-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

---
title: Guide pratique pour lire un fichier texte (Guide de programmation C#)
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: a42f98a81ff9e9bdbbf6c61554667aa223c7c269
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331670"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="d8fb1-102">Guide pratique pour lire un fichier texte (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="d8fb1-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="d8fb1-103">Cet exemple lit le contenu d’un fichier texte à l’aide des méthodes statiques <xref:System.IO.File.ReadAllText%2A> et <xref:System.IO.File.ReadAllLines%2A> de la classe <xref:System.IO.File?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d8fb1-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="d8fb1-104">Pour obtenir un exemple qui utilise <xref:System.IO.StreamReader>, consultez [Guide pratique pour lire un fichier texte ligne par ligne](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span><span class="sxs-lookup"><span data-stu-id="d8fb1-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8fb1-105">Les fichiers qui sont utilisés dans cet exemple sont créés dans la rubrique [Guide pratique pour écrire dans un fichier texte](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span><span class="sxs-lookup"><span data-stu-id="d8fb1-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8fb1-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="d8fb1-106">Example</span></span>  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d8fb1-107">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="d8fb1-107">Compiling the Code</span></span>  
 <span data-ttu-id="d8fb1-108">Copiez le code et collez-le dans une application console C#.</span><span class="sxs-lookup"><span data-stu-id="d8fb1-108">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="d8fb1-109">Si vous n’utilisez pas les fichiers texte de la rubrique [Guide pratique pour écrire dans un fichier texte](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), remplacez l’argument par `ReadAllText` et `ReadAllLines`, en fournissant le chemin et le nom correspondants sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d8fb1-109">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d8fb1-110">Programmation fiable</span><span class="sxs-lookup"><span data-stu-id="d8fb1-110">Robust Programming</span></span>  
 <span data-ttu-id="d8fb1-111">Les conditions ci-dessous peuvent générer une exception.</span><span class="sxs-lookup"><span data-stu-id="d8fb1-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="d8fb1-112">Le fichier n’existe pas ou ne se trouve pas à l’emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="d8fb1-112">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="d8fb1-113">Vérifiez le chemin et l’orthographe du nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="d8fb1-113">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d8fb1-114">Sécurité .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d8fb1-114">.NET Framework Security</span></span>  
 <span data-ttu-id="d8fb1-115">Ne comptez pas sur le nom d’un fichier pour en déduire le contenu.</span><span class="sxs-lookup"><span data-stu-id="d8fb1-115">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="d8fb1-116">Par exemple, le fichier `myFile.cs` peut ne pas être un fichier source C#.</span><span class="sxs-lookup"><span data-stu-id="d8fb1-116">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fb1-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8fb1-117">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="d8fb1-118">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="d8fb1-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d8fb1-119">Système de fichiers et Registre (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="d8fb1-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

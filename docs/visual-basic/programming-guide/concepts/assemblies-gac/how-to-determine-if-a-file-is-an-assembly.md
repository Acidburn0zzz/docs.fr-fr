---
title: 'Comment : déterminer si un fichier est un Assembly (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: ced41279e7e192d6d5bed53dbce7378395b32e6d
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45745589"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="282cc-102">Comment : déterminer si un fichier est un Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="282cc-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="282cc-103">Un fichier est un assembly si et seulement s’il est managé et s’il contient une entrée d’assembly dans ses métadonnées.</span><span class="sxs-lookup"><span data-stu-id="282cc-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="282cc-104">Pour plus d’informations sur les assemblys et les métadonnées, consultez la rubrique [Manifeste d’assembly](../../../../framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="282cc-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../framework/app-domains/assembly-manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="282cc-105">Comment déterminer manuellement si un fichier est un assembly</span><span class="sxs-lookup"><span data-stu-id="282cc-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="282cc-106">Démarrez [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="282cc-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2.  <span data-ttu-id="282cc-107">Chargez le fichier que vous souhaitez tester.</span><span class="sxs-lookup"><span data-stu-id="282cc-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="282cc-108">Si **ILDASM** indique que le fichier n’est pas un fichier exécutable portable (PE), alors il ne s’agit pas d’un assembly.</span><span class="sxs-lookup"><span data-stu-id="282cc-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="282cc-109">Pour plus d’informations, consultez la rubrique [Guide pratique pour afficher le contenu d’un assembly](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="282cc-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="282cc-110">Comment déterminer par programmation si un fichier est un assembly</span><span class="sxs-lookup"><span data-stu-id="282cc-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="282cc-111">Appelez la méthode <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> en passant le chemin complet et le nom du fichier que vous testez.</span><span class="sxs-lookup"><span data-stu-id="282cc-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="282cc-112">Si une exception <xref:System.BadImageFormatException> est levée, le fichier n’est pas un assembly.</span><span class="sxs-lookup"><span data-stu-id="282cc-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="282cc-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="282cc-113">Example</span></span>  
 <span data-ttu-id="282cc-114">Cet exemple teste une DLL pour voir s’il s’agit d’un assembly.</span><span class="sxs-lookup"><span data-stu-id="282cc-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 <span data-ttu-id="282cc-115">La méthode <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> charge le fichier de test, puis le libère une fois que les informations sont lues.</span><span class="sxs-lookup"><span data-stu-id="282cc-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282cc-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="282cc-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>  
- [<span data-ttu-id="282cc-117">Concepts de programmation</span><span class="sxs-lookup"><span data-stu-id="282cc-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
- [<span data-ttu-id="282cc-118">Assemblys et le Global Assembly Cache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="282cc-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](index.md)

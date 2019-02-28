---
title: 'Procédure : Recherche dans une chaîne (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: c150299efe07809d0d33edf882771f552c3e5b63
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982009"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="6121a-102">Procédure : Recherche dans une chaîne (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6121a-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="6121a-103">Cet exemple appelle la <xref:System.String.IndexOf%2A> méthode sur un <xref:System.String> objet pour signaler l’index de la première occurrence d’une sous-chaîne.</span><span class="sxs-lookup"><span data-stu-id="6121a-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6121a-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="6121a-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6121a-105">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="6121a-105">Compiling the Code</span></span>  
 <span data-ttu-id="6121a-106">Cet exemple nécessite :</span><span class="sxs-lookup"><span data-stu-id="6121a-106">This example requires:</span></span>  
  
-   <span data-ttu-id="6121a-107">Un `Imports` instruction spécifiant le <xref:System> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="6121a-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="6121a-108">Pour plus d’informations, consultez [Instruction Imports (espace de noms et type .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="6121a-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6121a-109">Programmation fiable</span><span class="sxs-lookup"><span data-stu-id="6121a-109">Robust Programming</span></span>  
 <span data-ttu-id="6121a-110">Le <xref:System.String.IndexOf%2A> méthode signale l’emplacement du premier caractère de la première occurrence de la sous-chaîne.</span><span class="sxs-lookup"><span data-stu-id="6121a-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="6121a-111">L’index est basé sur 0, ce qui signifie que le premier caractère d’une chaîne a un index de 0.</span><span class="sxs-lookup"><span data-stu-id="6121a-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="6121a-112">Si <xref:System.String.IndexOf%2A> ne trouve pas la sous-chaîne, elle retourne -1.</span><span class="sxs-lookup"><span data-stu-id="6121a-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="6121a-113">Le <xref:System.String.IndexOf%2A> méthode respecte la casse et utilise la culture actuelle.</span><span class="sxs-lookup"><span data-stu-id="6121a-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="6121a-114">Pour un contrôle optimal des erreurs, vous souhaiterez peut-être placer la chaîne de recherche dans les `Try` de blocs à un [essayez... Catch... Instruction finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span><span class="sxs-lookup"><span data-stu-id="6121a-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6121a-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6121a-115">See also</span></span>
- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="6121a-116">Try...Catch...Finally (instruction)</span><span class="sxs-lookup"><span data-stu-id="6121a-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="6121a-117">Introduction aux chaînes en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6121a-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="6121a-118">Chaînes</span><span class="sxs-lookup"><span data-stu-id="6121a-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)

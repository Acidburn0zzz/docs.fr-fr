---
title: 'Comment : convertir une chaîne en tableau de caractères en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: cc12b70cddcb93a72b4421a8ddd93542ef84f55b
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845188"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="e8a8f-102">Comment : convertir une chaîne en tableau de caractères en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8a8f-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="e8a8f-103">Il est parfois utile de disposer de données sur les caractères de votre chaîne et les positions de ces caractères dans votre chaîne, comme lorsque vous analysez une chaîne.</span><span class="sxs-lookup"><span data-stu-id="e8a8f-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="e8a8f-104">Cet exemple montre comment vous pouvez obtenir un tableau de caractères dans une chaîne en appelant la chaîne <xref:System.String.ToCharArray%2A> (méthode).</span><span class="sxs-lookup"><span data-stu-id="e8a8f-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8a8f-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="e8a8f-105">Example</span></span>  
 <span data-ttu-id="e8a8f-106">Cet exemple montre comment fractionner une chaîne en un `Char` tableau et comment fractionner une chaîne en un `String` tableau de ses caractères de texte Unicode.</span><span class="sxs-lookup"><span data-stu-id="e8a8f-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="e8a8f-107">La raison de cette distinction est que les caractères de texte Unicode peuvent être composés de deux ou plusieurs `Char` caractères (par exemple une paire de substitution ou une combinaison séquence de caractères).</span><span class="sxs-lookup"><span data-stu-id="e8a8f-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="e8a8f-108">Pour plus d’informations, consultez <xref:System.Globalization.TextElementEnumerator> et [la norme Unicode](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="e8a8f-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="e8a8f-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="e8a8f-109">Example</span></span>  
 <span data-ttu-id="e8a8f-110">Il est plus difficile de fractionner une chaîne en ses caractères de texte Unicode, mais cela est nécessaire si vous avez besoin d’informations sur la représentation visuelle d’une chaîne.</span><span class="sxs-lookup"><span data-stu-id="e8a8f-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="e8a8f-111">Cet exemple utilise le <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> méthode pour obtenir des informations sur les caractères de texte Unicode qui composent une chaîne.</span><span class="sxs-lookup"><span data-stu-id="e8a8f-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e8a8f-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8a8f-112">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [<span data-ttu-id="e8a8f-113">Guide pratique : accéder aux caractères dans les chaînes</span><span class="sxs-lookup"><span data-stu-id="e8a8f-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [<span data-ttu-id="e8a8f-114">Conversion entre chaînes et d’autres types de données en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8a8f-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="e8a8f-115">Chaînes</span><span class="sxs-lookup"><span data-stu-id="e8a8f-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)

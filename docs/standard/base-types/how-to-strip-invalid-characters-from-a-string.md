---
title: "Comment : supprimer des caractères non valides d'une chaîne"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- cleaning input
- user input, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 030fc003c54e122362d7ecc71675a8b197b68e48
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a><span data-ttu-id="7d083-102">Comment : supprimer des caractères non valides d'une chaîne</span><span class="sxs-lookup"><span data-stu-id="7d083-102">How to: Strip Invalid Characters from a String</span></span>
<span data-ttu-id="7d083-103">L’exemple suivant utilise la méthode <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> statique pour supprimer des caractères non valides d’une chaîne.</span><span class="sxs-lookup"><span data-stu-id="7d083-103">The following example uses the static <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to strip invalid characters from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d083-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="7d083-104">Example</span></span>  
 <span data-ttu-id="7d083-105">Vous pouvez utiliser la méthode `CleanInput` définie dans cet exemple pour supprimer des caractères potentiellement nuisibles entrés dans un champ de texte qui accepte une entrée d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7d083-105">You can use the `CleanInput` method defined in this example to strip potentially harmful characters that have been entered into a text field that accepts user input.</span></span> <span data-ttu-id="7d083-106">Dans ce cas, `CleanInput` supprime tous les caractères non alphanumériques à l’exception des points (.), des arrobases (@) et des traits d’union (-), puis retourne la chaîne restante.</span><span class="sxs-lookup"><span data-stu-id="7d083-106">In this case, `CleanInput` strips out all nonalphanumeric characters except periods (.), at symbols (@), and hyphens (-), and returns the remaining string.</span></span> <span data-ttu-id="7d083-107">Toutefois, vous pouvez modifier le modèle d’expression régulière afin qu’il supprime tous les caractères qui ne doivent pas être inclus dans une chaîne d’entrée.</span><span class="sxs-lookup"><span data-stu-id="7d083-107">However, you can modify the regular expression pattern so that it strips out any characters that should not be included in an input string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 <span data-ttu-id="7d083-108">Le modèle d’expression régulière `[^\w\.@-]` recherche tout caractère qui n’est pas un caractère de mot, un point, un symbole @ ou un trait d’union.</span><span class="sxs-lookup"><span data-stu-id="7d083-108">The regular expression pattern `[^\w\.@-]` matches any character that is not a word character, a period, an @ symbol, or a hyphen.</span></span> <span data-ttu-id="7d083-109">Un caractère de mot correspond aux lettres, chiffres décimaux ou connecteurs de ponctuation tel qu’un trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="7d083-109">A word character is any letter, decimal digit, or punctuation connector such as an underscore.</span></span> <span data-ttu-id="7d083-110">Tout caractère qui correspond à ce modèle est remplacé par <xref:System.String.Empty?displayProperty=nameWithType>, qui est la chaîne définie par le modèle de remplacement.</span><span class="sxs-lookup"><span data-stu-id="7d083-110">Any character that matches this pattern is replaced by <xref:System.String.Empty?displayProperty=nameWithType>, which is the string defined by the replacement pattern.</span></span> <span data-ttu-id="7d083-111">Pour autoriser des caractères supplémentaires dans une entrée d’utilisateur, ajoutez-les à la classe de caractères dans le modèle d’expression régulière.</span><span class="sxs-lookup"><span data-stu-id="7d083-111">To allow additional characters in user input, add those characters to the character class in the regular expression pattern.</span></span> <span data-ttu-id="7d083-112">Par exemple, le modèle d’expression régulière `[^\w\.@-\\%]` autorise également un symbole de pourcentage et une barre oblique inverse dans une chaîne d’entrée.</span><span class="sxs-lookup"><span data-stu-id="7d083-112">For example, the regular expression pattern `[^\w\.@-\\%]` also allows a percentage symbol and a backslash in an input string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d083-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d083-113">See Also</span></span>  
 [<span data-ttu-id="7d083-114">Expressions régulières .NET</span><span class="sxs-lookup"><span data-stu-id="7d083-114">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)

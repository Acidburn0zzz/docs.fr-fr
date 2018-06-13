---
title: Chaînes (F#)
description: "Découvrez comment le type 'string') (F # représente le texte immuable en tant que séquence de caractères Unicode."
ms.date: 05/16/2016
ms.openlocfilehash: bdd1d1a542e70bcd95fce51e75d0c1ddffceb008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564857"
---
# <a name="strings"></a><span data-ttu-id="5b49a-103">Chaînes</span><span class="sxs-lookup"><span data-stu-id="5b49a-103">Strings</span></span>

> [!NOTE]
<span data-ttu-id="5b49a-104">Les liens des informations de référence sur les API qui figurent dans cet article pointent vers MSDN.</span><span class="sxs-lookup"><span data-stu-id="5b49a-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="5b49a-105">Les informations de référence sur les API docs.microsoft.com ne sont pas terminées.</span><span class="sxs-lookup"><span data-stu-id="5b49a-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="5b49a-106">Le `string` type représente le texte immuable en tant que séquence de caractères Unicode.</span><span class="sxs-lookup"><span data-stu-id="5b49a-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="5b49a-107">`string` est un alias pour `System.String` dans le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5b49a-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b49a-108">Notes</span><span class="sxs-lookup"><span data-stu-id="5b49a-108">Remarks</span></span>
<span data-ttu-id="5b49a-109">Littéraux de chaîne sont délimités par le caractère guillemet (").</span><span class="sxs-lookup"><span data-stu-id="5b49a-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="5b49a-110">Le caractère barre oblique inverse (\) est utilisé pour encoder certains caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="5b49a-110">The backslash character (\) is used to encode certain special characters.</span></span> <span data-ttu-id="5b49a-111">La barre oblique inverse et le caractère suivant forment sont appelés un *séquence d’échappement*.</span><span class="sxs-lookup"><span data-stu-id="5b49a-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="5b49a-112">Prise en charge dans les littéraux sont affichés dans le tableau suivant de chaîne F # de séquences d’échappement.</span><span class="sxs-lookup"><span data-stu-id="5b49a-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="5b49a-113">Caractère</span><span class="sxs-lookup"><span data-stu-id="5b49a-113">Character</span></span>|<span data-ttu-id="5b49a-114">Séquence d'échappement</span><span class="sxs-lookup"><span data-stu-id="5b49a-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="5b49a-115">Retour arrière</span><span class="sxs-lookup"><span data-stu-id="5b49a-115">Backspace</span></span>|<span data-ttu-id="5b49a-116">\b</span><span class="sxs-lookup"><span data-stu-id="5b49a-116">\b</span></span>|
|<span data-ttu-id="5b49a-117">Saut de ligne</span><span class="sxs-lookup"><span data-stu-id="5b49a-117">Newline</span></span>|<span data-ttu-id="5b49a-118">\n</span><span class="sxs-lookup"><span data-stu-id="5b49a-118">\n</span></span>|
|<span data-ttu-id="5b49a-119">Retour chariot</span><span class="sxs-lookup"><span data-stu-id="5b49a-119">Carriage return</span></span>|<span data-ttu-id="5b49a-120">\r</span><span class="sxs-lookup"><span data-stu-id="5b49a-120">\r</span></span>|
|<span data-ttu-id="5b49a-121">Onglet</span><span class="sxs-lookup"><span data-stu-id="5b49a-121">Tab</span></span>|<span data-ttu-id="5b49a-122">\t</span><span class="sxs-lookup"><span data-stu-id="5b49a-122">\t</span></span>|
|<span data-ttu-id="5b49a-123">Barre oblique inverse</span><span class="sxs-lookup"><span data-stu-id="5b49a-123">Backslash</span></span>|\\|
|<span data-ttu-id="5b49a-124">Guillemet</span><span class="sxs-lookup"><span data-stu-id="5b49a-124">Quotation mark</span></span>|\"|
|<span data-ttu-id="5b49a-125">Apostrophe</span><span class="sxs-lookup"><span data-stu-id="5b49a-125">Apostrophe</span></span>|\'|
|<span data-ttu-id="5b49a-126">caractère Unicode</span><span class="sxs-lookup"><span data-stu-id="5b49a-126">Unicode character</span></span>|<span data-ttu-id="5b49a-127">\u*XXXX* ou \U*XXXXXXXX* (où *X* indique un chiffre hexadécimal)</span><span class="sxs-lookup"><span data-stu-id="5b49a-127">\u*XXXX* or \U*XXXXXXXX* (where *X* indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="5b49a-128">Si précédé par le symbole @, le littéral est une chaîne textuelle.</span><span class="sxs-lookup"><span data-stu-id="5b49a-128">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="5b49a-129">Cela signifie que les séquences d’échappement sont ignorés, sauf que deux caractères de guillemet sont interprétés comme un guillemet.</span><span class="sxs-lookup"><span data-stu-id="5b49a-129">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="5b49a-130">En outre, une chaîne peut être placé entre guillemets triples.</span><span class="sxs-lookup"><span data-stu-id="5b49a-130">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="5b49a-131">Dans ce cas, toutes les séquences d’échappement sont ignorés, y compris les caractères de guillemet double.</span><span class="sxs-lookup"><span data-stu-id="5b49a-131">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="5b49a-132">Pour spécifier une chaîne qui contient un élément incorporé chaîne entre guillemets, vous pouvez utiliser une chaîne textuelle ou une chaîne à guillemets triples.</span><span class="sxs-lookup"><span data-stu-id="5b49a-132">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="5b49a-133">Si vous utilisez une chaîne textuelle, vous devez spécifier deux guillemets pour indiquer un caractère de guillemet.</span><span class="sxs-lookup"><span data-stu-id="5b49a-133">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="5b49a-134">Si vous utilisez une chaîne à guillemets triples, vous pouvez utiliser les caractères de guillemet simple sans les analysé en tant que la fin de la chaîne.</span><span class="sxs-lookup"><span data-stu-id="5b49a-134">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="5b49a-135">Cette technique peut être utile lorsque vous travaillez avec XML ou d’autres structures qui incluent des guillemets incorporés.</span><span class="sxs-lookup"><span data-stu-id="5b49a-135">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="5b49a-136">Dans le code, les chaînes qui ont des sauts de ligne sont acceptées et les sauts de ligne sont interprétées littéralement en tant que nouvelles lignes, sauf si un caractère de barre oblique inverse est le dernier caractère avant le saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="5b49a-136">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="5b49a-137">Espaces de début de la ligne suivante est ignoré lorsque le caractère de barre oblique inverse est utilisé.</span><span class="sxs-lookup"><span data-stu-id="5b49a-137">Leading whitespace on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="5b49a-138">Le code suivant produit une chaîne `str1` qui a la valeur `"abc\n     def"` et une chaîne `str2` qui a la valeur `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="5b49a-138">The following code produces a string `str1` that has value `"abc\n     def"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="5b49a-139">Vous pouvez accéder à des caractères individuels dans une chaîne à l’aide de la syntaxe de type tableau, comme suit.</span><span class="sxs-lookup"><span data-stu-id="5b49a-139">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="5b49a-140">Le résultat est `b`.</span><span class="sxs-lookup"><span data-stu-id="5b49a-140">The output is `b`.</span></span>

<span data-ttu-id="5b49a-141">Ou vous pouvez extraire des sous-chaînes à l’aide de la syntaxe de tranche tableau, comme indiqué dans le code suivant.</span><span class="sxs-lookup"><span data-stu-id="5b49a-141">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="5b49a-142">La sortie est la suivante.</span><span class="sxs-lookup"><span data-stu-id="5b49a-142">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="5b49a-143">Vous pouvez représenter les chaînes ASCII par des tableaux d’octets non signés, de type `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="5b49a-143">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="5b49a-144">Vous ajoutez le suffixe `B` à un littéral de chaîne pour indiquer qu’il s’agit d’une chaîne ASCII.</span><span class="sxs-lookup"><span data-stu-id="5b49a-144">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="5b49a-145">Les littéraux de chaîne ASCII utilisés avec les tableaux d’octets prend en charge les séquences d’échappement même sous forme de chaînes Unicode à l’exception des séquences d’échappement Unicode.</span><span class="sxs-lookup"><span data-stu-id="5b49a-145">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a><span data-ttu-id="5b49a-146">Opérateurs de chaîne</span><span class="sxs-lookup"><span data-stu-id="5b49a-146">String Operators</span></span>
<span data-ttu-id="5b49a-147">Il existe deux façons de concaténer des chaînes : à l’aide de la `+` opérateur ou à l’aide de la `^` opérateur.</span><span class="sxs-lookup"><span data-stu-id="5b49a-147">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="5b49a-148">Le `+` opérateur assure la compatibilité avec la chaîne .NET Framework de la gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="5b49a-148">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="5b49a-149">L’exemple suivant illustre la concaténation de chaînes.</span><span class="sxs-lookup"><span data-stu-id="5b49a-149">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a><span data-ttu-id="5b49a-150">Classe de chaîne</span><span class="sxs-lookup"><span data-stu-id="5b49a-150">String Class</span></span>
<span data-ttu-id="5b49a-151">Car le type de chaîne en F # est réellement un .NET Framework `System.String` de type, tous les `System.String` membres sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="5b49a-151">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="5b49a-152">Cela inclut la `+` opérateur, qui est utilisé pour concaténer des chaînes, la `Length` propriété et le `Chars` propriété, qui retourne la chaîne sous la forme d’un tableau de caractères Unicode.</span><span class="sxs-lookup"><span data-stu-id="5b49a-152">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="5b49a-153">Pour plus d’informations sur les chaînes, consultez `System.String`.</span><span class="sxs-lookup"><span data-stu-id="5b49a-153">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="5b49a-154">À l’aide de la `Chars` propriété du `System.String`, vous pouvez accéder à des caractères individuels dans une chaîne en spécifiant un index, comme indiqué dans le code suivant.</span><span class="sxs-lookup"><span data-stu-id="5b49a-154">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a><span data-ttu-id="5b49a-155">Module de chaîne</span><span class="sxs-lookup"><span data-stu-id="5b49a-155">String Module</span></span>
<span data-ttu-id="5b49a-156">Fonctionnalités supplémentaires pour la gestion des chaînes sont incluses dans le `String` module dans le `FSharp.Core` espace de noms.</span><span class="sxs-lookup"><span data-stu-id="5b49a-156">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="5b49a-157">Pour plus d’informations, consultez [Core.String, Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="5b49a-157">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b49a-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b49a-158">See Also</span></span>
[<span data-ttu-id="5b49a-159">Informations de référence du langage F#</span><span class="sxs-lookup"><span data-stu-id="5b49a-159">F# Language Reference</span></span>](index.md)

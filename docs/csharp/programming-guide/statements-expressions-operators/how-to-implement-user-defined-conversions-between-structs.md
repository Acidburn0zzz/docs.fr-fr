---
title: "Comment : implémenter des conversions définies par l'utilisateur entre des structs (Guide de programmation C#)"
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: cff85d60c1b59f4d1ca028f8fc02fee5728fa3d6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44251971"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="0bd86-102">Comment : implémenter des conversions définies par l'utilisateur entre des structs (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="0bd86-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="0bd86-103">L’exemple suivant définit deux structs, `RomanNumeral` et `BinaryNumeral`, et décrit les conversions entre ces deux structs.</span><span class="sxs-lookup"><span data-stu-id="0bd86-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bd86-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="0bd86-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="0bd86-105">Programmation fiable</span><span class="sxs-lookup"><span data-stu-id="0bd86-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="0bd86-106">Dans l’exemple précédent, l’instruction :</span><span class="sxs-lookup"><span data-stu-id="0bd86-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     <span data-ttu-id="0bd86-107">convertit un `RomanNumeral` en `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="0bd86-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="0bd86-108">Étant donné qu’il n’existe pas de conversion directe de `RomanNumeral` en `BinaryNumeral`, un cast est utilisé pour convertir un `RomanNumeral` en un `int`, et un autre cast est utilisé pour convertir un `int` en un `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="0bd86-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="0bd86-109">L’instruction</span><span class="sxs-lookup"><span data-stu-id="0bd86-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     <span data-ttu-id="0bd86-110">convertit un `BinaryNumeral` en `RomanNumeral`.</span><span class="sxs-lookup"><span data-stu-id="0bd86-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="0bd86-111">Étant donné que `RomanNumeral` définit une conversion implicite d’un `BinaryNumeral`, aucun cast n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="0bd86-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd86-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0bd86-112">See Also</span></span>

- [<span data-ttu-id="0bd86-113">Référence C#</span><span class="sxs-lookup"><span data-stu-id="0bd86-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0bd86-114">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="0bd86-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0bd86-115">Opérateurs de conversion</span><span class="sxs-lookup"><span data-stu-id="0bd86-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

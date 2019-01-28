---
title: Comparaison de pointeurs - Guide de programmation C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: a2cbbabdad1d79c82bb5b3ec02a391727e552c98
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718635"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="3343b-102">Comparaison de pointeurs (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="3343b-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="3343b-103">Vous pouvez appliquer les opérateurs suivants pour comparer des pointeurs de tout type :</span><span class="sxs-lookup"><span data-stu-id="3343b-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="3343b-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="3343b-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="3343b-105">Les opérateurs de comparaison comparent les adresses des deux opérandes comme s’il s’agissait d’entiers non signés.</span><span class="sxs-lookup"><span data-stu-id="3343b-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3343b-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="3343b-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a><span data-ttu-id="3343b-107">Résultat de l'exemple</span><span class="sxs-lookup"><span data-stu-id="3343b-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="3343b-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3343b-108">See also</span></span>

- [<span data-ttu-id="3343b-109">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="3343b-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3343b-110">Expressions de pointeur</span><span class="sxs-lookup"><span data-stu-id="3343b-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="3343b-111">Opérateurs C#</span><span class="sxs-lookup"><span data-stu-id="3343b-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="3343b-112">Manipulation de pointeurs</span><span class="sxs-lookup"><span data-stu-id="3343b-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="3343b-113">Types de pointeur</span><span class="sxs-lookup"><span data-stu-id="3343b-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="3343b-114">Types</span><span class="sxs-lookup"><span data-stu-id="3343b-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="3343b-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="3343b-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="3343b-116">fixed, instruction</span><span class="sxs-lookup"><span data-stu-id="3343b-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="3343b-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="3343b-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

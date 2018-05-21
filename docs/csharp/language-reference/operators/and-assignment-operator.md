---
title: '&amp;=, opérateur (référence C#)'
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 092f46ddd8ca52e2d705200768c93a3473f1520f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2018
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="67137-102">&amp;=, opérateur (référence C#)</span><span class="sxs-lookup"><span data-stu-id="67137-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="67137-103">Opérateur d’assignation AND.</span><span class="sxs-lookup"><span data-stu-id="67137-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67137-104">Notes</span><span class="sxs-lookup"><span data-stu-id="67137-104">Remarks</span></span>  
 <span data-ttu-id="67137-105">Une expression qui utilise l’opérateur d’assignation `&=`, telle que</span><span class="sxs-lookup"><span data-stu-id="67137-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```csharp  
x &= y  
```  
  
 <span data-ttu-id="67137-106">est équivalent à</span><span class="sxs-lookup"><span data-stu-id="67137-106">is equivalent to</span></span>  
  
```csharp  
x = x & y  
```  
  
 <span data-ttu-id="67137-107">sauf que `x` n’est évalué qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="67137-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="67137-108">L’[opérateur &](../../../csharp/language-reference/operators/and-operator.md) effectue une opération AND logique au niveau du bit sur les opérandes de type intégral et une opération AND logique sur les opérandes de type `bool`.</span><span class="sxs-lookup"><span data-stu-id="67137-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="67137-109">L’opérateur `&=` ne peut pas être surchargé directement, mais les types définis par l’utilisateur peuvent surcharger l’[opérateur &](../../../csharp/language-reference/operators/and-operator.md) binaire (voir [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="67137-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="67137-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="67137-110">Example</span></span>  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="67137-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67137-111">See Also</span></span>  
 [<span data-ttu-id="67137-112">Référence C#</span><span class="sxs-lookup"><span data-stu-id="67137-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="67137-113">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="67137-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="67137-114">Opérateurs C#</span><span class="sxs-lookup"><span data-stu-id="67137-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

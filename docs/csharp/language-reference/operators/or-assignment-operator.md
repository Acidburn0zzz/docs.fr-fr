---
title: '|=, opérateur (référence C#)'
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: fe56005ce94656b5e8a075cddfb91dc0da096cf7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45653367"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3e878-102">|=, opérateur (référence C#)</span><span class="sxs-lookup"><span data-stu-id="3e878-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="3e878-103">Opérateur d’assignation OR.</span><span class="sxs-lookup"><span data-stu-id="3e878-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e878-104">Notes</span><span class="sxs-lookup"><span data-stu-id="3e878-104">Remarks</span></span>  
 <span data-ttu-id="3e878-105">Une expression qui utilise l’opérateur d’assignation `|=`, telle que</span><span class="sxs-lookup"><span data-stu-id="3e878-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```csharp  
x |= y  
```  
  
 <span data-ttu-id="3e878-106">est équivalent à</span><span class="sxs-lookup"><span data-stu-id="3e878-106">is equivalent to</span></span>  
  
```csharp  
x = x | y  
```  
  
 <span data-ttu-id="3e878-107">sauf que `x` n’est évalué qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="3e878-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="3e878-108">L’[opérateur &#124](../../../csharp/language-reference/operators/or-operator.md) effectue une opération OR logique au niveau du bit sur les opérandes intégraux et une opération OR logique sur les opérandes de type bool.</span><span class="sxs-lookup"><span data-stu-id="3e878-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="3e878-109">L’opérateur `|=` ne peut pas être surchargé directement, mais les types définis par l’utilisateur peuvent surcharger l’[opérateur &#124;](../../../csharp/language-reference/operators/or-operator.md) (consultez [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="3e878-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e878-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="3e878-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3e878-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e878-111">See Also</span></span>

- [<span data-ttu-id="3e878-112">Référence C#</span><span class="sxs-lookup"><span data-stu-id="3e878-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3e878-113">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="3e878-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3e878-114">Opérateurs C#</span><span class="sxs-lookup"><span data-stu-id="3e878-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

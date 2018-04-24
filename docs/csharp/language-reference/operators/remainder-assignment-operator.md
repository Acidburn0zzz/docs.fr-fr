---
title: '%=, opérateur (référence C#)'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 864b96dcf16e4756cd0e74a6e02297660e72357e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="dd1c9-102">%=, opérateur (référence C#)</span><span class="sxs-lookup"><span data-stu-id="dd1c9-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="dd1c9-103">Opérateur d’assignation de reste.</span><span class="sxs-lookup"><span data-stu-id="dd1c9-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd1c9-104">Notes</span><span class="sxs-lookup"><span data-stu-id="dd1c9-104">Remarks</span></span>  
 <span data-ttu-id="dd1c9-105">Une expression qui utilise l’opérateur d’assignation `%=`, telle que</span><span class="sxs-lookup"><span data-stu-id="dd1c9-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="dd1c9-106">est équivalent à</span><span class="sxs-lookup"><span data-stu-id="dd1c9-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="dd1c9-107">sauf que `x` n’est évalué qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="dd1c9-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="dd1c9-108">L’[opérateur %](../../../csharp/language-reference/operators/remainder-operator.md) est prédéfini pour les types numériques de façon à calculer le reste d’une division.</span><span class="sxs-lookup"><span data-stu-id="dd1c9-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="dd1c9-109">L’opérateur `%=` ne peut pas être surchargé directement, mais les types définis par l’utilisateur peuvent surcharger l’[opérateur %](../../../csharp/language-reference/operators/remainder-operator.md) (consultez [operator (informations de référence sur C#)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="dd1c9-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd1c9-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="dd1c9-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="dd1c9-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd1c9-111">See Also</span></span>  
 [<span data-ttu-id="dd1c9-112">Référence C#</span><span class="sxs-lookup"><span data-stu-id="dd1c9-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dd1c9-113">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="dd1c9-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dd1c9-114">Opérateurs C#</span><span class="sxs-lookup"><span data-stu-id="dd1c9-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

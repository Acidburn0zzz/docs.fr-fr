---
title: return (référence C#)
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 29d2b8e28ae6240b9d06b82695efe1736404c5cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="return-c-reference"></a><span data-ttu-id="d7366-102">return (référence C#)</span><span class="sxs-lookup"><span data-stu-id="d7366-102">return (C# Reference)</span></span>
<span data-ttu-id="d7366-103">L’instruction `return` met un terme à l’exécution de la méthode dans laquelle elle apparaît et retourne le contrôle à la méthode d’appel.</span><span class="sxs-lookup"><span data-stu-id="d7366-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="d7366-104">Elle peut également retourner une valeur facultative.</span><span class="sxs-lookup"><span data-stu-id="d7366-104">It can also return an optional value.</span></span> <span data-ttu-id="d7366-105">Si la méthode est un type `void`, l’instruction `return` peut être omise.</span><span class="sxs-lookup"><span data-stu-id="d7366-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="d7366-106">Si l’instruction return est à l’intérieur d’un bloc `try`, le bloc `finally`, le cas échéant, est exécuté avant que le contrôle retourne à la méthode d’appel.</span><span class="sxs-lookup"><span data-stu-id="d7366-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7366-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7366-107">Example</span></span>  
 <span data-ttu-id="d7366-108">Dans l’exemple suivant, la méthode `CalculateArea()` retourne la variable locale `area` en tant que valeur [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="d7366-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="d7366-109">Spécification du langage C#</span><span class="sxs-lookup"><span data-stu-id="d7366-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7366-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7366-110">See Also</span></span>  
 [<span data-ttu-id="d7366-111">Référence C#</span><span class="sxs-lookup"><span data-stu-id="d7366-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d7366-112">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="d7366-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d7366-113">Mots clés C#</span><span class="sxs-lookup"><span data-stu-id="d7366-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d7366-114">Instruction return</span><span class="sxs-lookup"><span data-stu-id="d7366-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="d7366-115">Instructions de saut</span><span class="sxs-lookup"><span data-stu-id="d7366-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

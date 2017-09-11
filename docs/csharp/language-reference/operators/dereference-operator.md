---
title: "-&gt;, opérateur (référence C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ->_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f42135e43bdfc58ee64fd3465074b3f8791f8ada
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="3dd68-102">-&gt;, opérateur (référence C#)</span><span class="sxs-lookup"><span data-stu-id="3dd68-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="3dd68-103">L’opérateur `->` allie l’annulation de la référence d’un pointeur et l’accès au membre.</span><span class="sxs-lookup"><span data-stu-id="3dd68-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dd68-104">Remarques</span><span class="sxs-lookup"><span data-stu-id="3dd68-104">Remarks</span></span>  
 <span data-ttu-id="3dd68-105">Une expression de forme</span><span class="sxs-lookup"><span data-stu-id="3dd68-105">An expression of the form,</span></span>  
  
```  
x->y  
```  
  
 <span data-ttu-id="3dd68-106">(où `x` est un pointeur de type `T*` et `y` un membre de `T`) est équivalente à</span><span class="sxs-lookup"><span data-stu-id="3dd68-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```  
(*x).y  
```  
  
 <span data-ttu-id="3dd68-107">L’opérateur `->` peut être utilisé uniquement dans du code marqué comme [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="3dd68-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="3dd68-108">L’opérateur `->` ne peut pas être surchargé.</span><span class="sxs-lookup"><span data-stu-id="3dd68-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dd68-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="3dd68-109">Example</span></span>  
 <span data-ttu-id="3dd68-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3dd68-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dd68-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3dd68-111">See Also</span></span>  
 <span data-ttu-id="3dd68-112">[Informations de référence sur C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3dd68-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3dd68-113">[Guide de programmation C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3dd68-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3dd68-114">Opérateurs C#</span><span class="sxs-lookup"><span data-stu-id="3dd68-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


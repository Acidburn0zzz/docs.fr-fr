---
title: . Opérateur - Référence C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: f5048761973e10bec9650469383e2f52cee74da4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235044"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8ba72-103">.</span><span class="sxs-lookup"><span data-stu-id="8ba72-103">.</span></span> <span data-ttu-id="8ba72-104">Opérateur (référence C#)</span><span class="sxs-lookup"><span data-stu-id="8ba72-104">Operator (C# Reference)</span></span>
<span data-ttu-id="8ba72-105">L’opérateur point (`.`) est l’opérateur d’accès aux membres .</span><span class="sxs-lookup"><span data-stu-id="8ba72-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="8ba72-106">L’opérateur point spécifie un membre d’un type ou d’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="8ba72-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="8ba72-107">Par exemple, l’opérateur point est utilisé pour accéder aux méthodes spécifiques figurant dans les bibliothèques de classes du .NET Framework :</span><span class="sxs-lookup"><span data-stu-id="8ba72-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 [!code-csharp[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]  
  
 <span data-ttu-id="8ba72-108">Par exemple, considérons la classe suivante :</span><span class="sxs-lookup"><span data-stu-id="8ba72-108">For example, consider the following class:</span></span>  
  
 [!code-csharp[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]  
  
 [!code-csharp[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]  
  
 <span data-ttu-id="8ba72-109">La variable `s` a deux membres, `a` et `b` ; pour y accéder, utilisez l’opérateur point :</span><span class="sxs-lookup"><span data-stu-id="8ba72-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 [!code-csharp[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]  
  
 <span data-ttu-id="8ba72-110">Le point est aussi utilisé pour former des noms qualifiés, c’est-à-dire des noms qui spécifient par exemple l’espace de noms ou une interface auquel ils appartiennent.</span><span class="sxs-lookup"><span data-stu-id="8ba72-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 [!code-csharp[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]  
  
 <span data-ttu-id="8ba72-111">La directive using rend la qualification de certains noms facultative :</span><span class="sxs-lookup"><span data-stu-id="8ba72-111">The using directive makes some name qualification optional:</span></span>  
  
 [!code-csharp[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]  
  
 <span data-ttu-id="8ba72-112">Cependant, quand un identificateur est ambigu, il doit être qualifié :</span><span class="sxs-lookup"><span data-stu-id="8ba72-112">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 [!code-csharp[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8ba72-113">Spécification du langage C#</span><span class="sxs-lookup"><span data-stu-id="8ba72-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ba72-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ba72-114">See Also</span></span>

- [<span data-ttu-id="8ba72-115">Référence C#</span><span class="sxs-lookup"><span data-stu-id="8ba72-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="8ba72-116">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="8ba72-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8ba72-117">Opérateurs C#</span><span class="sxs-lookup"><span data-stu-id="8ba72-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

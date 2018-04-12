---
title: Opérateur DirectCast (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="9cf4c-102">Opérateur DirectCast (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cf4c-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="9cf4c-103">Introduit une opération de conversion de type en fonction d’héritage ou d’implémentation.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cf4c-104">Remarques</span><span class="sxs-lookup"><span data-stu-id="9cf4c-104">Remarks</span></span>  
 <span data-ttu-id="9cf4c-105">`DirectCast`n’utilise pas les routines d’assistance d’exécution pour la conversion, donc il peut fournir un peu de meilleures performances que Visual Basic `CType` lors de la conversion vers et depuis le type de données `Object`.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="9cf4c-106">Vous utilisez la `DirectCast` mot-clé similaire à la façon dont vous utilisez la [CType (fonction)](../../../visual-basic/language-reference/functions/ctype-function.md) et le [opérateur TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) (mot clé).</span><span class="sxs-lookup"><span data-stu-id="9cf4c-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="9cf4c-107">Vous fournissez une expression comme premier argument et un type pour convertir comme deuxième argument.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="9cf4c-108">`DirectCast`requiert une relation d’héritage ou d’implémentation entre les types de données des deux arguments.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="9cf4c-109">Cela signifie qu’un type doit hériter ou l’implémenter l’autre.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="9cf4c-110">Erreurs et échecs</span><span class="sxs-lookup"><span data-stu-id="9cf4c-110">Errors and Failures</span></span>  
 <span data-ttu-id="9cf4c-111">`DirectCast`génère une erreur du compilateur s’il détecte qu’il n’existe aucune relation d’héritage ou d’implémentation.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="9cf4c-112">Mais l’absence d’une erreur du compilateur ne garantit pas une conversion réussie.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="9cf4c-113">Si la conversion souhaitée est restrictive, elle peut échouer au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="9cf4c-114">Si cela se produit, le runtime lève une <xref:System.InvalidCastException> erreur.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="9cf4c-115">Mots clés de conversion</span><span class="sxs-lookup"><span data-stu-id="9cf4c-115">Conversion Keywords</span></span>  
 <span data-ttu-id="9cf4c-116">Une comparaison de mots clés de conversion de type est la suivante.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="9cf4c-117">Mot clé</span><span class="sxs-lookup"><span data-stu-id="9cf4c-117">Keyword</span></span>|<span data-ttu-id="9cf4c-118">Types de données</span><span class="sxs-lookup"><span data-stu-id="9cf4c-118">Data types</span></span>|<span data-ttu-id="9cf4c-119">Relation d’argument</span><span class="sxs-lookup"><span data-stu-id="9cf4c-119">Argument relationship</span></span>|<span data-ttu-id="9cf4c-120">Échec d’exécution</span><span class="sxs-lookup"><span data-stu-id="9cf4c-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="9cf4c-121">CType (fonction)</span><span class="sxs-lookup"><span data-stu-id="9cf4c-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="9cf4c-122">Les types de données</span><span class="sxs-lookup"><span data-stu-id="9cf4c-122">Any data types</span></span>|<span data-ttu-id="9cf4c-123">Conversion restrictive ou étendue doit être défini entre les deux types de données</span><span class="sxs-lookup"><span data-stu-id="9cf4c-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="9cf4c-124">Lève une exception<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="9cf4c-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="9cf4c-125">Les types de données</span><span class="sxs-lookup"><span data-stu-id="9cf4c-125">Any data types</span></span>|<span data-ttu-id="9cf4c-126">Un type doit hériter ou implémenter l’autre type</span><span class="sxs-lookup"><span data-stu-id="9cf4c-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="9cf4c-127">Lève une exception<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="9cf4c-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="9cf4c-128">TryCast (opérateur)</span><span class="sxs-lookup"><span data-stu-id="9cf4c-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="9cf4c-129">Seuls les types référence</span><span class="sxs-lookup"><span data-stu-id="9cf4c-129">Reference types only</span></span>|<span data-ttu-id="9cf4c-130">Un type doit hériter ou implémenter l’autre type</span><span class="sxs-lookup"><span data-stu-id="9cf4c-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="9cf4c-131">Retourne [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="9cf4c-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9cf4c-132">Exemple</span><span class="sxs-lookup"><span data-stu-id="9cf4c-132">Example</span></span>  
 <span data-ttu-id="9cf4c-133">L’exemple suivant montre deux utilisations de `DirectCast`, une qui échoue au moment de l’exécution et l’une d’elles réussisse.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 <span data-ttu-id="9cf4c-134">Dans l’exemple précédent, la durée d’exécution de type de `q` est `Double`.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="9cf4c-135">`CType`réussit car `Double` peut être converti en `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="9cf4c-136">Toutefois, la première `DirectCast` échoue au moment de l’exécution, car le type de la durée d’exécution de `Double` n’a aucune relation d’héritage avec `Integer`, même s’il existe une conversion.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="9cf4c-137">La seconde `DirectCast` réussit car elle convertit depuis le type <xref:System.Windows.Forms.Form> au type <xref:System.Windows.Forms.Control>, à partir de laquelle <xref:System.Windows.Forms.Form> hérite.</span><span class="sxs-lookup"><span data-stu-id="9cf4c-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf4c-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9cf4c-138">See Also</span></span>  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9cf4c-139">Conversions étendues et restrictives</span><span class="sxs-lookup"><span data-stu-id="9cf4c-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="9cf4c-140">Conversions implicites et explicites</span><span class="sxs-lookup"><span data-stu-id="9cf4c-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)

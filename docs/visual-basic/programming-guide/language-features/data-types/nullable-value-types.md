---
title: Types valeur Nullable (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8734114b9d657066a0ef0b2d648f0290c03b1cbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="9df00-102">Types valeur Nullable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9df00-102">Nullable Value Types (Visual Basic)</span></span>
<span data-ttu-id="9df00-103">Parfois, vous travaillez avec un type valeur qui n’a pas une valeur définie dans certaines circonstances.</span><span class="sxs-lookup"><span data-stu-id="9df00-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="9df00-104">Par exemple, un champ dans une base de données peut-être faire la distinction entre une valeur assignée est explicite et n’ayant ne pas une valeur assignée.</span><span class="sxs-lookup"><span data-stu-id="9df00-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="9df00-105">Types de valeur peuvent être étendus pour prendre leurs valeurs normales ou une valeur null.</span><span class="sxs-lookup"><span data-stu-id="9df00-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="9df00-106">Cette extension est appelée un *type nullable*.</span><span class="sxs-lookup"><span data-stu-id="9df00-106">Such an extension is called a *nullable type*.</span></span>  
  
 <span data-ttu-id="9df00-107">Chaque type nullable est construit à partir de l’objet générique <xref:System.Nullable%601> structure.</span><span class="sxs-lookup"><span data-stu-id="9df00-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="9df00-108">Envisagez d’une base de données qui effectue le suivi des activités liées au travail.</span><span class="sxs-lookup"><span data-stu-id="9df00-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="9df00-109">L’exemple suivant construit nullable `Boolean` tapez et déclare une variable de ce type.</span><span class="sxs-lookup"><span data-stu-id="9df00-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="9df00-110">Vous pouvez écrire la déclaration de trois manières :</span><span class="sxs-lookup"><span data-stu-id="9df00-110">You can write the declaration in three ways:</span></span>  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 <span data-ttu-id="9df00-111">La variable `ridesBusToWork` peut contenir une valeur de `True`, une valeur de `False`, ou aucune valeur.</span><span class="sxs-lookup"><span data-stu-id="9df00-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="9df00-112">Sa valeur par défaut initiale n’est pas de valeur, qui dans ce cas activée peut signifier que les informations n’ont pas encore été obtenues pour cette personne.</span><span class="sxs-lookup"><span data-stu-id="9df00-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="9df00-113">En revanche, `False` peut signifier que les informations ont été obtenues et que la personne ne pas le bus pour aller au travail.</span><span class="sxs-lookup"><span data-stu-id="9df00-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>  
  
 <span data-ttu-id="9df00-114">Vous pouvez déclarer des variables et des propriétés avec des types nullables, et vous pouvez déclarer un tableau avec les éléments d’un type nullable.</span><span class="sxs-lookup"><span data-stu-id="9df00-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="9df00-115">Vous pouvez déclarer des procédures avec des types nullables comme paramètres, et vous pouvez retourner un type nullable à partir d’un `Function` procédure.</span><span class="sxs-lookup"><span data-stu-id="9df00-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>  
  
 <span data-ttu-id="9df00-116">Vous ne pouvez pas construire un type nullable sur un type référence tel qu’un tableau, un `String`, ou une classe.</span><span class="sxs-lookup"><span data-stu-id="9df00-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="9df00-117">Le type sous-jacent doit être un type valeur.</span><span class="sxs-lookup"><span data-stu-id="9df00-117">The underlying type must be a value type.</span></span> <span data-ttu-id="9df00-118">Pour plus d’informations, consultez [les Types valeur et Types référence](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="9df00-118">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="9df00-119">À l’aide d’une Variable de Type Nullable</span><span class="sxs-lookup"><span data-stu-id="9df00-119">Using a Nullable Type Variable</span></span>  
 <span data-ttu-id="9df00-120">Les membres les plus importants d’un type nullable sont ses <xref:System.Nullable%601.HasValue%2A> et <xref:System.Nullable%601.Value%2A> propriétés.</span><span class="sxs-lookup"><span data-stu-id="9df00-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="9df00-121">Pour une variable de type nullable, <xref:System.Nullable%601.HasValue%2A> vous indique si la variable contient une valeur définie.</span><span class="sxs-lookup"><span data-stu-id="9df00-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="9df00-122">Si <xref:System.Nullable%601.HasValue%2A> est `True`, vous pouvez lire la valeur de <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="9df00-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="9df00-123">Notez que les deux <xref:System.Nullable%601.HasValue%2A> et <xref:System.Nullable%601.Value%2A> sont `ReadOnly` propriétés.</span><span class="sxs-lookup"><span data-stu-id="9df00-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>  
  
### <a name="default-values"></a><span data-ttu-id="9df00-124">Valeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="9df00-124">Default Values</span></span>  
 <span data-ttu-id="9df00-125">Lorsque vous déclarez une variable avec un type nullable, sa <xref:System.Nullable%601.HasValue%2A> propriété a la valeur par défaut `False`.</span><span class="sxs-lookup"><span data-stu-id="9df00-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="9df00-126">Cela signifie que, par défaut, la variable n’a aucune valeur définie, au lieu de la valeur par défaut de son type valeur sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="9df00-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="9df00-127">Dans l’exemple suivant, la variable `numberOfChildren` a d’initialement aucune valeur définie, même si la valeur par défaut de la `Integer` type est 0.</span><span class="sxs-lookup"><span data-stu-id="9df00-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 <span data-ttu-id="9df00-128">Une valeur null est utile pour indiquer une valeur inconnue ou non définie.</span><span class="sxs-lookup"><span data-stu-id="9df00-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="9df00-129">Si `numberOfChildren` a été déclaré comme `Integer`, aucune valeur ne peuvent indiquer que les informations ne sont pas disponibles actuellement.</span><span class="sxs-lookup"><span data-stu-id="9df00-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>  
  
### <a name="storing-values"></a><span data-ttu-id="9df00-130">Stockage de valeurs</span><span class="sxs-lookup"><span data-stu-id="9df00-130">Storing Values</span></span>  
 <span data-ttu-id="9df00-131">Vous stockez une valeur dans une variable ou une propriété d’un type nullable de la manière habituelle.</span><span class="sxs-lookup"><span data-stu-id="9df00-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="9df00-132">L’exemple suivant assigne une valeur à la variable `numberOfChildren` déclaré dans l’exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="9df00-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 <span data-ttu-id="9df00-133">Si une variable ou une propriété d’un type nullable contient une valeur définie, vous pouvez provoquer pour rétablir l’état initial de n’ayant ne pas de valeur assignée.</span><span class="sxs-lookup"><span data-stu-id="9df00-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="9df00-134">Pour cela en définissant la variable ou la propriété `Nothing`, comme le montre l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="9df00-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="9df00-135">Bien que vous puissiez attribuer `Nothing` à une variable d’un type nullable, vous ne pouvez pas tester pour `Nothing` à l’aide du signe égal.</span><span class="sxs-lookup"><span data-stu-id="9df00-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="9df00-136">Comparaison qui utilise le signe égal, `someVar = Nothing`, a toujours la valeur `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9df00-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="9df00-137">Vous pouvez tester la variable <xref:System.Nullable%601.HasValue%2A> propriété `False`, ou de test à l’aide de la `Is` ou `IsNot` opérateur.</span><span class="sxs-lookup"><span data-stu-id="9df00-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>  
  
### <a name="retrieving-values"></a><span data-ttu-id="9df00-138">Extraction de valeurs</span><span class="sxs-lookup"><span data-stu-id="9df00-138">Retrieving Values</span></span>  
 <span data-ttu-id="9df00-139">Pour récupérer la valeur d’une variable d’un type nullable, vous devez d’abord tester son <xref:System.Nullable%601.HasValue%2A> pour confirmer qu’il possède une valeur de propriété.</span><span class="sxs-lookup"><span data-stu-id="9df00-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="9df00-140">Si vous essayez de lire la valeur lorsque <xref:System.Nullable%601.HasValue%2A> est `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] lève une <xref:System.InvalidOperationException> exception.</span><span class="sxs-lookup"><span data-stu-id="9df00-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="9df00-141">L’exemple suivant montre la méthode recommandée pour lire la variable `numberOfChildren` des exemples précédents.</span><span class="sxs-lookup"><span data-stu-id="9df00-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a><span data-ttu-id="9df00-142">Comparaison des Types Nullable</span><span class="sxs-lookup"><span data-stu-id="9df00-142">Comparing Nullable Types</span></span>  
 <span data-ttu-id="9df00-143">Lorsque nullable `Boolean` variables sont utilisées dans les expressions booléennes, le résultat peut être `True`, `False`, ou `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9df00-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="9df00-144">Voici la table de vérité pour `And` et `Or`.</span><span class="sxs-lookup"><span data-stu-id="9df00-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="9df00-145">Étant donné que `b1` et `b2` ont maintenant des trois valeurs possibles, il existe neuf combinaisons à évaluer.</span><span class="sxs-lookup"><span data-stu-id="9df00-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>  
  
|<span data-ttu-id="9df00-146">B1</span><span class="sxs-lookup"><span data-stu-id="9df00-146">b1</span></span>|<span data-ttu-id="9df00-147">B2</span><span class="sxs-lookup"><span data-stu-id="9df00-147">b2</span></span>|<span data-ttu-id="9df00-148">B1 et b2</span><span class="sxs-lookup"><span data-stu-id="9df00-148">b1 And b2</span></span>|<span data-ttu-id="9df00-149">B1 ou b2</span><span class="sxs-lookup"><span data-stu-id="9df00-149">b1 Or b2</span></span>|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 <span data-ttu-id="9df00-150">Lorsque la valeur d’une variable ou expression booléenne est `Nothing`, il n’est ni `true` ni `false`.</span><span class="sxs-lookup"><span data-stu-id="9df00-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="9df00-151">Prenons l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="9df00-151">Consider the following example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 <span data-ttu-id="9df00-152">Dans cet exemple, `b1 And b2` prend la valeur `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9df00-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="9df00-153">Par conséquent, le `Else` clause est exécutée dans chaque `If` instruction et la sortie est la suivante :</span><span class="sxs-lookup"><span data-stu-id="9df00-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  <span data-ttu-id="9df00-154">`AndAlso`et `OrElse`, qui utilisent l’évaluation de court-circuit doit évaluer leurs seconds opérandes lorsque le premier prend la valeur de `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9df00-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>  
  
## <a name="propagation"></a><span data-ttu-id="9df00-155">Propagation</span><span class="sxs-lookup"><span data-stu-id="9df00-155">Propagation</span></span>  
 <span data-ttu-id="9df00-156">Si un ou les deux opérandes d’une opération arithmétique, comparaison, MAJ ou d’une opération de type est nullable, le résultat de l’opération est également nullable.</span><span class="sxs-lookup"><span data-stu-id="9df00-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="9df00-157">Si les deux opérandes ont des valeurs qui ne sont pas `Nothing`, l’opération est effectuée sur les valeurs sous-jacentes des opérandes, comme si aucune n’était un type nullable.</span><span class="sxs-lookup"><span data-stu-id="9df00-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="9df00-158">Dans l’exemple suivant, les variables `compare1` et `sum1` sont implicitement typées.</span><span class="sxs-lookup"><span data-stu-id="9df00-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="9df00-159">Si vous placez le pointeur de la souris au-dessus d’eux, vous verrez que le compilateur déduit les types nullable pour les deux.</span><span class="sxs-lookup"><span data-stu-id="9df00-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 <span data-ttu-id="9df00-160">Si un ou deux opérandes ont la valeur `Nothing`, le résultat sera `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9df00-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a><span data-ttu-id="9df00-161">Utilisation des Types Nullable avec des données</span><span class="sxs-lookup"><span data-stu-id="9df00-161">Using Nullable Types with Data</span></span>  
 <span data-ttu-id="9df00-162">Une base de données est un des emplacements plus importants pour utiliser des types nullables.</span><span class="sxs-lookup"><span data-stu-id="9df00-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="9df00-163">Pas tous les objets de base de données charge actuellement les types nullable, mais les cartes générées par le concepteur.</span><span class="sxs-lookup"><span data-stu-id="9df00-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="9df00-164">Consultez « Prise en charge pour les Types Nullable le TableAdapter » dans [vue d’ensemble de TableAdapter](/visualstudio/data-tools/tableadapter-overview).</span><span class="sxs-lookup"><span data-stu-id="9df00-164">See "TableAdapter Support for Nullable Types" in [TableAdapter Overview](/visualstudio/data-tools/tableadapter-overview).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df00-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9df00-165">See Also</span></span>  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [<span data-ttu-id="9df00-166">Utilisation de types Nullable</span><span class="sxs-lookup"><span data-stu-id="9df00-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [<span data-ttu-id="9df00-167">Types de données</span><span class="sxs-lookup"><span data-stu-id="9df00-167">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="9df00-168">Types valeur et types référence</span><span class="sxs-lookup"><span data-stu-id="9df00-168">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="9df00-169">Dépannage des types de données</span><span class="sxs-lookup"><span data-stu-id="9df00-169">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="9df00-170">Vue d’ensemble de TableAdapter</span><span class="sxs-lookup"><span data-stu-id="9df00-170">TableAdapter Overview</span></span>](/visualstudio/data-tools/tableadapter-overview)  
 [<span data-ttu-id="9df00-171">If (opérateur)</span><span class="sxs-lookup"><span data-stu-id="9df00-171">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="9df00-172">Inférence de type local</span><span class="sxs-lookup"><span data-stu-id="9df00-172">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="9df00-173">Is (opérateur)</span><span class="sxs-lookup"><span data-stu-id="9df00-173">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="9df00-174">IsNot (opérateur)</span><span class="sxs-lookup"><span data-stu-id="9df00-174">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)

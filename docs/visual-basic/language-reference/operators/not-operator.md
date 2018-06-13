---
title: Not, opérateur (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 332cee57c8d25d7f51737e01e70ba515d50bd6e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604391"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="2c9b5-102">Not, opérateur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="2c9b5-103">Effectue une négation logique sur une `Boolean` expression ou une négation au niveau du bit sur une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c9b5-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2c9b5-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="2c9b5-105">Composants</span><span class="sxs-lookup"><span data-stu-id="2c9b5-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="2c9b5-106">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-106">Required.</span></span> <span data-ttu-id="2c9b5-107">N’importe quel `Boolean` ou expression numérique.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="2c9b5-108">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-108">Required.</span></span> <span data-ttu-id="2c9b5-109">N’importe quel `Boolean` ou expression numérique.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c9b5-110">Notes</span><span class="sxs-lookup"><span data-stu-id="2c9b5-110">Remarks</span></span>  
 <span data-ttu-id="2c9b5-111">Pour `Boolean` expressions, le tableau suivant illustre comment `result` est déterminée.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="2c9b5-112">Si `expression` est</span><span class="sxs-lookup"><span data-stu-id="2c9b5-112">If `expression` is</span></span>|<span data-ttu-id="2c9b5-113">La valeur de `result` est</span><span class="sxs-lookup"><span data-stu-id="2c9b5-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="2c9b5-114">Pour les expressions numériques, la `Not` opérateur inverse les valeurs de bits de toute expression numérique et définit le bit dans correspondant `result` conformément au tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="2c9b5-115">Si bit dans `expression` est</span><span class="sxs-lookup"><span data-stu-id="2c9b5-115">If bit in `expression` is</span></span>|<span data-ttu-id="2c9b5-116">Le bit `result` est</span><span class="sxs-lookup"><span data-stu-id="2c9b5-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="2c9b5-117">1</span><span class="sxs-lookup"><span data-stu-id="2c9b5-117">1</span></span>|<span data-ttu-id="2c9b5-118">0</span><span class="sxs-lookup"><span data-stu-id="2c9b5-118">0</span></span>|  
|<span data-ttu-id="2c9b5-119">0</span><span class="sxs-lookup"><span data-stu-id="2c9b5-119">0</span></span>|<span data-ttu-id="2c9b5-120">1</span><span class="sxs-lookup"><span data-stu-id="2c9b5-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="2c9b5-121">Étant donné que les opérateurs logiques et au niveau du bit ont une priorité inférieure à celle des opérateurs arithmétiques et relationnels, toutes les opérations de bits doivent être placées entre parenthèses pour garantir une exécution précise.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="2c9b5-122">Types de données</span><span class="sxs-lookup"><span data-stu-id="2c9b5-122">Data Types</span></span>  
 <span data-ttu-id="2c9b5-123">Pour une négation Boolean, le type de données du résultat est `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="2c9b5-124">Pour une négation au niveau du bit, le type de données de résultat est identique à celle de `expression`.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="2c9b5-125">Toutefois, si l’expression est `Decimal`, le résultat est `Long`.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2c9b5-126">Surcharge</span><span class="sxs-lookup"><span data-stu-id="2c9b5-126">Overloading</span></span>  
 <span data-ttu-id="2c9b5-127">Le `Not` opérateur peut être *surchargé*, ce qui signifie qu’une classe ou structure peut redéfinir son comportement lorsque son opérande a le type de cette classe ou structure.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="2c9b5-128">Si votre code utilise cet opérateur sur une telle classe ou structure, assurez-vous que vous comprenez son comportement redéfini.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2c9b5-129">Pour plus d’informations, consultez [procédures d’opérateur](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2c9b5-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c9b5-130">Exemple</span><span class="sxs-lookup"><span data-stu-id="2c9b5-130">Example</span></span>  
 <span data-ttu-id="2c9b5-131">L’exemple suivant utilise le `Not` opérateur effectue une négation logique sur une `Boolean` expression.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="2c9b5-132">Le résultat est un `Boolean` valeur qui représente l’inverse de la valeur de l’expression.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 <span data-ttu-id="2c9b5-133">L’exemple précédent produit des résultats de `False` et `True`, respectivement.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c9b5-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="2c9b5-134">Example</span></span>  
 <span data-ttu-id="2c9b5-135">L’exemple suivant utilise le `Not` opérateur effectue une négation logique des bits individuels d’une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="2c9b5-136">Le bit du modèle de résultat est défini à l’inverse du bit correspondant dans le modèle d’opérande, y compris le bit de signe.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 <span data-ttu-id="2c9b5-137">L’exemple précédent produit des résultats de – 11, -9 et -7, respectivement.</span><span class="sxs-lookup"><span data-stu-id="2c9b5-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9b5-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c9b5-138">See Also</span></span>  
 [<span data-ttu-id="2c9b5-139">Opérateurs logiques/de bits (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c9b5-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="2c9b5-140">Priorité des opérateurs en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c9b5-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="2c9b5-141">Opérateurs répertoriés par fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="2c9b5-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="2c9b5-142">Opérateurs logiques et au niveau du bit en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c9b5-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)

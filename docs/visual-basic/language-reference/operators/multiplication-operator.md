---
title: '* Opérateur (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 4e2d1000afcf8951e8914335f7b5a278b49f6277
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603624"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9101b-102">\*, opérateur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9101b-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="9101b-103">Multiplie deux nombres.</span><span class="sxs-lookup"><span data-stu-id="9101b-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9101b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9101b-104">Syntax</span></span>  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="9101b-105">Composants</span><span class="sxs-lookup"><span data-stu-id="9101b-105">Parts</span></span>  
  
|<span data-ttu-id="9101b-106">Terme</span><span class="sxs-lookup"><span data-stu-id="9101b-106">Term</span></span>|<span data-ttu-id="9101b-107">Définition</span><span class="sxs-lookup"><span data-stu-id="9101b-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="9101b-108">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="9101b-108">Required.</span></span> <span data-ttu-id="9101b-109">Toute expression numérique.</span><span class="sxs-lookup"><span data-stu-id="9101b-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="9101b-110">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="9101b-110">Required.</span></span> <span data-ttu-id="9101b-111">Toute expression numérique.</span><span class="sxs-lookup"><span data-stu-id="9101b-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="9101b-112">Résultat</span><span class="sxs-lookup"><span data-stu-id="9101b-112">Result</span></span>  
 <span data-ttu-id="9101b-113">Le résultat est le produit de `number1` et `number2`.</span><span class="sxs-lookup"><span data-stu-id="9101b-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="9101b-114">Types pris en charge</span><span class="sxs-lookup"><span data-stu-id="9101b-114">Supported Types</span></span>  
 <span data-ttu-id="9101b-115">Tous les types numériques, y compris les types non signés et à virgule flottante et `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="9101b-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9101b-116">Notes</span><span class="sxs-lookup"><span data-stu-id="9101b-116">Remarks</span></span>  
 <span data-ttu-id="9101b-117">Le type de données du résultat dépend des types des opérandes.</span><span class="sxs-lookup"><span data-stu-id="9101b-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="9101b-118">Le tableau suivant présente la manière dont le type de données du résultat est déterminé.</span><span class="sxs-lookup"><span data-stu-id="9101b-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="9101b-119">Types de données d’opérande</span><span class="sxs-lookup"><span data-stu-id="9101b-119">Operand data types</span></span>|<span data-ttu-id="9101b-120">Type de données de résultat</span><span class="sxs-lookup"><span data-stu-id="9101b-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="9101b-121">Les deux expressions sont des types de données intégraux ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [octets](../../../visual-basic/language-reference/data-types/byte-data-type.md), [court](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [entier](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="9101b-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="9101b-122">Un type de données numériques approprié pour les types de données de `number1` et `number2`.</span><span class="sxs-lookup"><span data-stu-id="9101b-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="9101b-123">Consultez les tableaux « Arithmétique sur les entiers » dans [Types de données de résultats de l’opérateur](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="9101b-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="9101b-124">Les deux expressions sont [décimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="9101b-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="9101b-125">Les deux expressions sont [unique](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="9101b-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="9101b-126">Des expressions sont un type de données à virgule flottante (`Single` ou [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) mais pas les deux `Single` (Remarque `Decimal` n’est pas un type de données à virgule flottante)</span><span class="sxs-lookup"><span data-stu-id="9101b-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="9101b-127">Si une expression [rien](../../../visual-basic/language-reference/nothing.md), il est traité en tant que zéro.</span><span class="sxs-lookup"><span data-stu-id="9101b-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9101b-128">Surcharge</span><span class="sxs-lookup"><span data-stu-id="9101b-128">Overloading</span></span>  
 <span data-ttu-id="9101b-129">Le `*` opérateur peut être *surchargé*, ce qui signifie qu’une classe ou structure peut redéfinir son comportement lorsqu’un opérande a le type de cette classe ou structure.</span><span class="sxs-lookup"><span data-stu-id="9101b-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9101b-130">Si votre code utilise cet opérateur sur une telle classe ou structure, assurez-vous que vous comprenez son comportement redéfini.</span><span class="sxs-lookup"><span data-stu-id="9101b-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9101b-131">Pour plus d’informations, consultez [procédures d’opérateur](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9101b-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9101b-132">Exemple</span><span class="sxs-lookup"><span data-stu-id="9101b-132">Example</span></span>  
 <span data-ttu-id="9101b-133">Cet exemple utilise le `*` opérateur pour multiplier deux nombres.</span><span class="sxs-lookup"><span data-stu-id="9101b-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="9101b-134">Le résultat est le produit des deux opérandes.</span><span class="sxs-lookup"><span data-stu-id="9101b-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9101b-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9101b-135">See Also</span></span>  
 [<span data-ttu-id="9101b-136">\*= (opérateur)</span><span class="sxs-lookup"><span data-stu-id="9101b-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="9101b-137">Opérateurs arithmétiques</span><span class="sxs-lookup"><span data-stu-id="9101b-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="9101b-138">Priorité des opérateurs en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9101b-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="9101b-139">Opérateurs répertoriés par fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="9101b-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="9101b-140">Opérateurs arithmétiques en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9101b-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)

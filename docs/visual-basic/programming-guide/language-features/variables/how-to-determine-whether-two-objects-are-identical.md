---
title: 'Comment : déterminer si deux objets sont identiques (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 266e878e7f5fa8deb1c8cd91795af8d63ded0177
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="2ef27-102">Comment : déterminer si deux objets sont identiques (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ef27-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="2ef27-103">En Visual Basic, deux références de variable sont considérés comme identiques si leurs pointeurs sont les mêmes, autrement dit, si les deux variables pointent vers la même instance de classe en mémoire.</span><span class="sxs-lookup"><span data-stu-id="2ef27-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="2ef27-104">Par exemple, dans une application Windows Forms, vous souhaiterez effectuer une comparaison pour déterminer si l’instance actuelle (`Me`) est identique à une instance particulière, tel que `Form2`.</span><span class="sxs-lookup"><span data-stu-id="2ef27-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="2ef27-105">Visual Basic fournit deux opérateurs pour comparer des pointeurs.</span><span class="sxs-lookup"><span data-stu-id="2ef27-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="2ef27-106">Le [est un opérateur](../../../../visual-basic/language-reference/operators/is-operator.md) retourne `True` si les objets sont identiques et le [opérateur IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) retourne `True` si elles ne sont pas.</span><span class="sxs-lookup"><span data-stu-id="2ef27-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="2ef27-107">Comment déterminer si deux objets sont identiques</span><span class="sxs-lookup"><span data-stu-id="2ef27-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="2ef27-108">Pour déterminer si deux objets sont identiques</span><span class="sxs-lookup"><span data-stu-id="2ef27-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="2ef27-109">Configurer un `Boolean` expression pour tester les deux objets.</span><span class="sxs-lookup"><span data-stu-id="2ef27-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="2ef27-110">Dans votre expression de test, utilisez le `Is` (opérateur) avec les deux objets comme opérandes.</span><span class="sxs-lookup"><span data-stu-id="2ef27-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="2ef27-111">`Is` Retourne `True` si les objets pointent vers la même instance de classe.</span><span class="sxs-lookup"><span data-stu-id="2ef27-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="2ef27-112">Déterminer si deux objets ne sont pas identiques</span><span class="sxs-lookup"><span data-stu-id="2ef27-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="2ef27-113">Vous souhaitez parfois exécuter une action si les deux objets ne sont pas identiques, et il peut s’avérer difficile de combiner `Not` et `Is`, par exemple `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="2ef27-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="2ef27-114">Dans ce cas, vous pouvez utiliser la `IsNot` opérateur.</span><span class="sxs-lookup"><span data-stu-id="2ef27-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="2ef27-115">Pour déterminer si deux objets ne sont pas identiques</span><span class="sxs-lookup"><span data-stu-id="2ef27-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="2ef27-116">Configurer un `Boolean` expression pour tester les deux objets.</span><span class="sxs-lookup"><span data-stu-id="2ef27-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="2ef27-117">Dans votre expression de test, utilisez le `IsNot` (opérateur) avec les deux objets comme opérandes.</span><span class="sxs-lookup"><span data-stu-id="2ef27-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="2ef27-118">`IsNot` Retourne `True` si les objets ne pointent pas vers la même instance de classe.</span><span class="sxs-lookup"><span data-stu-id="2ef27-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ef27-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="2ef27-119">Example</span></span>  
 <span data-ttu-id="2ef27-120">L’exemple suivant teste des paires de `Object` variables pour voir si elles pointent vers la même instance de classe.</span><span class="sxs-lookup"><span data-stu-id="2ef27-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 <span data-ttu-id="2ef27-121">L’exemple précédent affiche la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="2ef27-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="2ef27-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ef27-122">See Also</span></span>  
 [<span data-ttu-id="2ef27-123">Object (type de données)</span><span class="sxs-lookup"><span data-stu-id="2ef27-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="2ef27-124">Variables objets</span><span class="sxs-lookup"><span data-stu-id="2ef27-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="2ef27-125">Valeurs des variables objets</span><span class="sxs-lookup"><span data-stu-id="2ef27-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="2ef27-126">Is (opérateur)</span><span class="sxs-lookup"><span data-stu-id="2ef27-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="2ef27-127">IsNot (opérateur)</span><span class="sxs-lookup"><span data-stu-id="2ef27-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="2ef27-128">Guide pratique : déterminer si deux objets sont liés</span><span class="sxs-lookup"><span data-stu-id="2ef27-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="2ef27-129">Me, My, MyBase et MyClass</span><span class="sxs-lookup"><span data-stu-id="2ef27-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

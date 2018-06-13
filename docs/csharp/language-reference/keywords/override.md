---
title: override (référence C#)
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 8f692dfdf8bd34ddb62623d86ec3dadd2b8dead3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280151"
---
# <a name="override-c-reference"></a><span data-ttu-id="b4ae4-102">override (référence C#)</span><span class="sxs-lookup"><span data-stu-id="b4ae4-102">override (C# Reference)</span></span>
<span data-ttu-id="b4ae4-103">Le modificateur `override` est nécessaire pour étendre ou modifier l’implémentation abstraite ou virtuelle d’une méthode, d’une propriété, d’un indexeur ou d’un événement hérités.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4ae4-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="b4ae4-104">Example</span></span>  
 <span data-ttu-id="b4ae4-105">Dans cet exemple, la classe `Square` doit fournir une implémentation substituée de `Area`, car `Area` est héritée de la classe abstraite `ShapesClass` :</span><span class="sxs-lookup"><span data-stu-id="b4ae4-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 <span data-ttu-id="b4ae4-106">Une méthode `override` fournit une nouvelle implémentation d’un membre hérité d’une classe de base.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="b4ae4-107">La méthode substituée par une déclaration `override` est appelée méthode de base substituée.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="b4ae4-108">La méthode de base substituée doit avoir la même signature que la méthode `override`.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="b4ae4-109">Pour plus d’informations sur l’héritage, consultez [Héritage](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="b4ae4-109">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="b4ae4-110">Vous ne pouvez pas surcharger une méthode statique ou non virtuelle.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="b4ae4-111">La méthode de base substituée doit être `virtual`, `abstract` ou `override`.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="b4ae4-112">Une déclaration `override` ne peut pas changer l’accessibilité de la méthode `virtual`.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="b4ae4-113">Les deux méthodes `override` et `virtual` doivent avoir le même [modificateur de niveau d’accès](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="b4ae4-113">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="b4ae4-114">Vous ne pouvez pas utiliser les modificateurs `new`, `static` ou `virtual` pour modifier une méthode `override`.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="b4ae4-115">Une déclaration de propriété de substitution doit spécifier exactement les mêmes modificateur d’accès, type et nom que la propriété héritée, et la propriété substituée doit être `virtual`, `abstract` ou `override`.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="b4ae4-116">Pour plus d’informations sur l’utilisation du mot clé `override`, consultez [Gestion de version avec les mots clés override et new](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) et [Savoir quand utiliser les mots clés override et new](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="b4ae4-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4ae4-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="b4ae4-117">Example</span></span>  
 <span data-ttu-id="b4ae4-118">Cet exemple définit une classe de base nommée `Employee` et une classe dérivée nommée `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="b4ae4-119">La classe `SalesEmployee` inclut une propriété supplémentaire (`salesbonus`) et substitue la méthode `CalculatePay` afin de la prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="b4ae4-119">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b4ae4-120">Spécification du langage C#</span><span class="sxs-lookup"><span data-stu-id="b4ae4-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4ae4-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4ae4-121">See Also</span></span>  
 [<span data-ttu-id="b4ae4-122">Référence C#</span><span class="sxs-lookup"><span data-stu-id="b4ae4-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b4ae4-123">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="b4ae4-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b4ae4-124">Héritage</span><span class="sxs-lookup"><span data-stu-id="b4ae4-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [<span data-ttu-id="b4ae4-125">Mots clés C#</span><span class="sxs-lookup"><span data-stu-id="b4ae4-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b4ae4-126">Modificateurs</span><span class="sxs-lookup"><span data-stu-id="b4ae4-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="b4ae4-127">abstract</span><span class="sxs-lookup"><span data-stu-id="b4ae4-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="b4ae4-128">virtual</span><span class="sxs-lookup"><span data-stu-id="b4ae4-128">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="b4ae4-129">new</span><span class="sxs-lookup"><span data-stu-id="b4ae4-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="b4ae4-130">Polymorphisme</span><span class="sxs-lookup"><span data-stu-id="b4ae4-130">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)

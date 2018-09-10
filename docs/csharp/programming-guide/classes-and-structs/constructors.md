---
title: Constructeurs (guide de programmation C#)
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 3d07fe5f6164885a994838376887edccc260e291
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185335"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="a8a18-102">Constructeurs (guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="a8a18-102">Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="a8a18-103">Chaque fois qu’une [classe](../../../csharp/language-reference/keywords/class.md) ou un [struct](../../../csharp/language-reference/keywords/struct.md) est créé, son constructeur est appelé.</span><span class="sxs-lookup"><span data-stu-id="a8a18-103">Whenever a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="a8a18-104">Une classe ou un struct peut avoir plusieurs constructeurs qui prennent des arguments différents.</span><span class="sxs-lookup"><span data-stu-id="a8a18-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="a8a18-105">Les constructeurs permettent au programmeur de définir des valeurs par défaut, de limiter l’instanciation et d’écrire un code flexible et facile à lire.</span><span class="sxs-lookup"><span data-stu-id="a8a18-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="a8a18-106">Pour obtenir plus d’informations et d’exemples, consultez [Utilisation de constructeurs](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) et [Constructeurs d’instances](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a8a18-106">For more information and examples, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) and [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="default-constructors"></a><span data-ttu-id="a8a18-107">Constructeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="a8a18-107">Default constructors</span></span>
  
<span data-ttu-id="a8a18-108">Si vous ne fournissez pas de constructeur pour votre classe, C# en crée un par défaut qui instancie l’objet et affecte aux variables membres les valeurs par défaut listées dans le [Tableau des valeurs par défaut](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="a8a18-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="a8a18-109">Si vous ne fournissez pas de constructeur pour votre struct, C# s’appuie sur un *constructeur par défaut implicite* pour initialiser automatiquement chaque champ d’un type valeur à sa valeur par défaut listée dans le [Tableau des valeurs par défaut](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="a8a18-109">If you don't provide a constructor for your struct, C# relies on an *implicit default constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="a8a18-110">Pour obtenir plus d’informations et d’exemples, consultez [Constructeurs d’instances](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a8a18-110">For more information and examples, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="a8a18-111">Syntaxe du constructeur</span><span class="sxs-lookup"><span data-stu-id="a8a18-111">Constructor syntax</span></span>

<span data-ttu-id="a8a18-112">Un constructeur est une méthode dont le nom est le même que celui de son type.</span><span class="sxs-lookup"><span data-stu-id="a8a18-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="a8a18-113">Sa signature de méthode inclut uniquement le nom de la méthode et sa liste de paramètres ; elle n’inclut pas de type de retour.</span><span class="sxs-lookup"><span data-stu-id="a8a18-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="a8a18-114">L’exemple suivant affiche le constructeur d’une classe nommée `Person`.</span><span class="sxs-lookup"><span data-stu-id="a8a18-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="a8a18-115">Si un constructeur peut être implémenté comme une seule instruction, vous pouvez utiliser une [définition de corps d’expression](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="a8a18-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="a8a18-116">L’exemple suivant définit une classe `Location` dont le constructeur a un seul paramètre de chaîne nommé *name*.</span><span class="sxs-lookup"><span data-stu-id="a8a18-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="a8a18-117">La définition de corps d’expression assigne l’argument au champ `locationName`.</span><span class="sxs-lookup"><span data-stu-id="a8a18-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="a8a18-118">Constructeurs statiques</span><span class="sxs-lookup"><span data-stu-id="a8a18-118">Static constructors</span></span>

<span data-ttu-id="a8a18-119">Les exemples précédents ont tous montré des constructeurs d’instances qui permettent de créer un objet.</span><span class="sxs-lookup"><span data-stu-id="a8a18-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="a8a18-120">Une classe ou un struct peut également avoir un constructeur statique qui initialise les membres statiques du type.</span><span class="sxs-lookup"><span data-stu-id="a8a18-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="a8a18-121">Les constructeurs statiques sont sans paramètre.</span><span class="sxs-lookup"><span data-stu-id="a8a18-121">Static constructors are parameterless.</span></span> <span data-ttu-id="a8a18-122">Si vous ne fournissez pas de constructeur statique pour initialiser les champs statiques, le compilateur C# fournit un constructeur statique par défaut qui initialise les champs statiques à leur valeur par défaut listée dans le [Tableau des valeurs par défaut](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="a8a18-122">If you don't provide a static constructor to initialize static fields, the C# compiler will supply a default static constructor that initializes static fields to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 

<span data-ttu-id="a8a18-123">L’exemple suivant utilise un constructeur statique pour initialiser un champ statique.</span><span class="sxs-lookup"><span data-stu-id="a8a18-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="a8a18-124">Vous pouvez également définir un constructeur statique avec une définition de corps d’expression, comme l’illustre l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="a8a18-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="a8a18-125">Pour obtenir plus d’informations et d’exemples, consultez [Constructeurs statiques](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="a8a18-125">For more information and examples, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8a18-126">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a8a18-126">In This Section</span></span>  
 [<span data-ttu-id="a8a18-127">Utilisation de constructeurs</span><span class="sxs-lookup"><span data-stu-id="a8a18-127">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [<span data-ttu-id="a8a18-128">Constructeurs d’instances</span><span class="sxs-lookup"><span data-stu-id="a8a18-128">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [<span data-ttu-id="a8a18-129">Constructeurs privés</span><span class="sxs-lookup"><span data-stu-id="a8a18-129">Private Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [<span data-ttu-id="a8a18-130">Constructeurs statiques</span><span class="sxs-lookup"><span data-stu-id="a8a18-130">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [<span data-ttu-id="a8a18-131">Comment : écrire un constructeur de copie</span><span class="sxs-lookup"><span data-stu-id="a8a18-131">How to: Write a Copy Constructor</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="a8a18-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8a18-132">See Also</span></span>

- [<span data-ttu-id="a8a18-133">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="a8a18-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a8a18-134">Classes et structs</span><span class="sxs-lookup"><span data-stu-id="a8a18-134">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="a8a18-135">Finaliseurs</span><span class="sxs-lookup"><span data-stu-id="a8a18-135">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="a8a18-136">static</span><span class="sxs-lookup"><span data-stu-id="a8a18-136">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
- [<span data-ttu-id="a8a18-137">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span><span class="sxs-lookup"><span data-stu-id="a8a18-137">Why Do Initializers Run In The Opposite Order As Constructors? Part One</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)

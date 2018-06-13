---
title: Structures (Guide de programmation C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322986"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="78b0c-102">Structures (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="78b0c-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="78b0c-103">Les structs sont définis à l’aide du mot clé [struct](../../../csharp/language-reference/keywords/struct.md), par exemple :</span><span class="sxs-lookup"><span data-stu-id="78b0c-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 <span data-ttu-id="78b0c-104">Les structs partagent presque tous la même syntaxe que les classes, bien qu'ils soient plus limités que ces dernières :</span><span class="sxs-lookup"><span data-stu-id="78b0c-104">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="78b0c-105">Au sein d’une déclaration de struct, les champs ne peuvent pas être initialisés à moins d’être déclarés comme étant de type const ou static.</span><span class="sxs-lookup"><span data-stu-id="78b0c-105">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="78b0c-106">Un struct ne peut pas déclarer de constructeur par défaut (un constructeur sans paramètre) ni de finaliseur.</span><span class="sxs-lookup"><span data-stu-id="78b0c-106">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="78b0c-107">Les structs sont copiés lors de l'assignation.</span><span class="sxs-lookup"><span data-stu-id="78b0c-107">Structs are copied on assignment.</span></span> <span data-ttu-id="78b0c-108">Lorsqu'un struct est assigné à une nouvelle variable, toutes les données sont copiées et les modifications apportées à la nouvelle copie ne changent pas les données de la copie d'origine.</span><span class="sxs-lookup"><span data-stu-id="78b0c-108">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="78b0c-109">Il est important de s’en souvenir lors de l’utilisation de collections de types valeur comme Dictionary\<string, myStruct>.</span><span class="sxs-lookup"><span data-stu-id="78b0c-109">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="78b0c-110">Les structs sont des types valeur et les classes des types référence.</span><span class="sxs-lookup"><span data-stu-id="78b0c-110">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="78b0c-111">Contrairement aux classes, il est possible d’instancier les structs sans avoir recours à un opérateur `new`.</span><span class="sxs-lookup"><span data-stu-id="78b0c-111">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="78b0c-112">Les structs peuvent déclarer des constructeurs qui ont des paramètres.</span><span class="sxs-lookup"><span data-stu-id="78b0c-112">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="78b0c-113">Un struct ne peut pas hériter d'un autre struct ou d'une classe ; il ne peut pas non plus servir de base à une classe.</span><span class="sxs-lookup"><span data-stu-id="78b0c-113">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="78b0c-114">Tous les structs héritent directement de `System.ValueType`, qui hérite de `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="78b0c-114">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="78b0c-115">Un struct peut implémenter des interfaces.</span><span class="sxs-lookup"><span data-stu-id="78b0c-115">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="78b0c-116">Un struct peut être utilisé comme un type Nullable et peut avoir une valeur null.</span><span class="sxs-lookup"><span data-stu-id="78b0c-116">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="78b0c-117">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="78b0c-117">Related Sections</span></span>  
 <span data-ttu-id="78b0c-118">Pour plus d'informations :</span><span class="sxs-lookup"><span data-stu-id="78b0c-118">For more information:</span></span>  
  
-   [<span data-ttu-id="78b0c-119">Utilisation de structs</span><span class="sxs-lookup"><span data-stu-id="78b0c-119">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="78b0c-120">Constructeurs</span><span class="sxs-lookup"><span data-stu-id="78b0c-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="78b0c-121">Types Nullable</span><span class="sxs-lookup"><span data-stu-id="78b0c-121">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="78b0c-122">Comment : différencier le passage d’un struct et le passage d’une référence de classe à une méthode</span><span class="sxs-lookup"><span data-stu-id="78b0c-122">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="78b0c-123">Guide pratique pour implémenter des conversions définies par l’utilisateur entre des structs</span><span class="sxs-lookup"><span data-stu-id="78b0c-123">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="78b0c-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="78b0c-124">See Also</span></span>  
 [<span data-ttu-id="78b0c-125">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="78b0c-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="78b0c-126">Classes et structs</span><span class="sxs-lookup"><span data-stu-id="78b0c-126">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="78b0c-127">Classes</span><span class="sxs-lookup"><span data-stu-id="78b0c-127">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

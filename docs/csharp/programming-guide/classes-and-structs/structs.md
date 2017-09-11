---
title: Structures (Guide de programmation C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
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
ms.openlocfilehash: ce12f402c0748ea6729c82e3f188c0a58f63d628
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="9b3a8-102">Structures (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="9b3a8-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="9b3a8-103">Les structs sont définis à l’aide du mot clé [struct](../../../csharp/language-reference/keywords/struct.md), par exemple :</span><span class="sxs-lookup"><span data-stu-id="9b3a8-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 <span data-ttu-id="9b3a8-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9b3a8-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span></span>  
  
 <span data-ttu-id="9b3a8-105">Les structs partagent presque tous la même syntaxe que les classes, bien qu'ils soient plus limités que ces dernières :</span><span class="sxs-lookup"><span data-stu-id="9b3a8-105">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="9b3a8-106">Au sein d’une déclaration de struct, les champs ne peuvent pas être initialisés à moins d’être déclarés comme étant de type const ou static.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-106">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="9b3a8-107">Un struct ne peut pas déclarer de constructeur par défaut (un constructeur sans paramètre) ni de finaliseur.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-107">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="9b3a8-108">Les structs sont copiés lors de l'assignation.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-108">Structs are copied on assignment.</span></span> <span data-ttu-id="9b3a8-109">Lorsqu'un struct est assigné à une nouvelle variable, toutes les données sont copiées et les modifications apportées à la nouvelle copie ne changent pas les données de la copie d'origine.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-109">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="9b3a8-110">Il est important de s’en souvenir lors de l’utilisation de collections de types valeur comme Dictionary\<string, myStruct>.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-110">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="9b3a8-111">Les structs sont des types valeur et les classes des types référence.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-111">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="9b3a8-112">Contrairement aux classes, il est possible d’instancier les structs sans avoir recours à un opérateur `new`.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-112">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="9b3a8-113">Les structs peuvent déclarer des constructeurs qui ont des paramètres.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-113">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="9b3a8-114">Un struct ne peut pas hériter d'un autre struct ou d'une classe ; il ne peut pas non plus servir de base à une classe.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-114">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="9b3a8-115">Tous les structs héritent directement de `System.ValueType`, qui hérite de `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-115">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="9b3a8-116">Un struct peut implémenter des interfaces.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-116">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="9b3a8-117">Un struct peut être utilisé comme un type Nullable et peut avoir une valeur null.</span><span class="sxs-lookup"><span data-stu-id="9b3a8-117">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9b3a8-118">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9b3a8-118">Related Sections</span></span>  
 <span data-ttu-id="9b3a8-119">Pour plus d'informations :</span><span class="sxs-lookup"><span data-stu-id="9b3a8-119">For more information:</span></span>  
  
-   [<span data-ttu-id="9b3a8-120">Utilisation de structs</span><span class="sxs-lookup"><span data-stu-id="9b3a8-120">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="9b3a8-121">Constructeurs</span><span class="sxs-lookup"><span data-stu-id="9b3a8-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="9b3a8-122">Types Nullable</span><span class="sxs-lookup"><span data-stu-id="9b3a8-122">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="9b3a8-123">Comment : différencier le passage d’un struct et le passage d’une référence de classe à une méthode</span><span class="sxs-lookup"><span data-stu-id="9b3a8-123">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="9b3a8-124">Comment : implémenter des conversions définies par l’utilisateur entre des structs</span><span class="sxs-lookup"><span data-stu-id="9b3a8-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="9b3a8-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b3a8-125">See Also</span></span>  
 <span data-ttu-id="9b3a8-126">[Guide de programmation C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9b3a8-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9b3a8-127">[Classes et structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="9b3a8-127">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="9b3a8-128">Classes</span><span class="sxs-lookup"><span data-stu-id="9b3a8-128">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)


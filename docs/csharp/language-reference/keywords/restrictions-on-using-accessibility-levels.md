---
title: Limitations sur l'utilisation des niveaux d'accessibilité (référence C#)
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: fd2f9b11523aac1cb720559db44aa36029d52ddb
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172407"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="ede26-102">Limitations sur l'utilisation des niveaux d'accessibilité (référence C#)</span><span class="sxs-lookup"><span data-stu-id="ede26-102">Restrictions on Using Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="ede26-103">Lorsque vous spécifiez un type dans une déclaration, vérifiez si le niveau d’accessibilité du type dépend du niveau d’accessibilité d’un membre ou d’un autre type.</span><span class="sxs-lookup"><span data-stu-id="ede26-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="ede26-104">Par exemple, la classe de base directe doit être au moins aussi accessible que la classe dérivée.</span><span class="sxs-lookup"><span data-stu-id="ede26-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="ede26-105">Les déclarations suivantes entraînent une erreur du compilateur, car la classe de base `BaseClass` est moins accessible que `MyClass` :</span><span class="sxs-lookup"><span data-stu-id="ede26-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>  
  
```csharp  
class BaseClass {...}  
public class MyClass: BaseClass {...} // Error  
```  
  
 <span data-ttu-id="ede26-106">Le tableau suivant résume les limitations sur les niveaux d’accessibilité déclarés.</span><span class="sxs-lookup"><span data-stu-id="ede26-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>  
  
|<span data-ttu-id="ede26-107">Contexte</span><span class="sxs-lookup"><span data-stu-id="ede26-107">Context</span></span>|<span data-ttu-id="ede26-108">Notes</span><span class="sxs-lookup"><span data-stu-id="ede26-108">Remarks</span></span>|  
|-------------|-------------|  
|[<span data-ttu-id="ede26-109">Classes</span><span class="sxs-lookup"><span data-stu-id="ede26-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="ede26-110">La classe de base directe d’un type de classe doit être au moins aussi accessible que le type de classe lui-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|  
|[<span data-ttu-id="ede26-111">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ede26-111">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)|<span data-ttu-id="ede26-112">Les interfaces de base explicites d’un type d’interface doivent être au moins aussi accessibles que le type d’interface lui-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|  
|[<span data-ttu-id="ede26-113">Délégués</span><span class="sxs-lookup"><span data-stu-id="ede26-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)|<span data-ttu-id="ede26-114">Le type de retour et les types de paramètres d’un type délégué doivent être au moins aussi accessibles que le type délégué lui-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|  
|[<span data-ttu-id="ede26-115">Constantes</span><span class="sxs-lookup"><span data-stu-id="ede26-115">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="ede26-116">Le type d’une constante doit être au moins aussi accessible que la constante elle-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|  
|[<span data-ttu-id="ede26-117">Champs</span><span class="sxs-lookup"><span data-stu-id="ede26-117">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="ede26-118">Le type d’un champ doit être au moins aussi accessible que le champ lui-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-118">The type of a field must be at least as accessible as the field itself.</span></span>|  
|[<span data-ttu-id="ede26-119">Méthodes</span><span class="sxs-lookup"><span data-stu-id="ede26-119">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="ede26-120">Le type de retour et les types de paramètres d’une méthode doivent être au moins aussi accessibles que la méthode elle-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|  
|[<span data-ttu-id="ede26-121">Propriétés</span><span class="sxs-lookup"><span data-stu-id="ede26-121">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="ede26-122">Le type d’une propriété doit être au moins aussi accessible que la propriété elle-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-122">The type of a property must be at least as accessible as the property itself.</span></span>|  
|[<span data-ttu-id="ede26-123">Événements</span><span class="sxs-lookup"><span data-stu-id="ede26-123">Events</span></span>](../../../csharp/programming-guide/events/index.md)|<span data-ttu-id="ede26-124">Le type d’un événement doit être au moins aussi accessible que l’événement lui-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-124">The type of an event must be at least as accessible as the event itself.</span></span>|  
|[<span data-ttu-id="ede26-125">Indexeurs</span><span class="sxs-lookup"><span data-stu-id="ede26-125">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)|<span data-ttu-id="ede26-126">Le type et les types de paramètres d’un indexeur doivent être au moins aussi accessibles que l’indexeur lui-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|  
|[<span data-ttu-id="ede26-127">Opérateurs</span><span class="sxs-lookup"><span data-stu-id="ede26-127">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|<span data-ttu-id="ede26-128">Le type de retour et les types de paramètres d’un opérateur doivent être au moins aussi accessibles que l’opérateur lui-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|  
|[<span data-ttu-id="ede26-129">Constructeurs</span><span class="sxs-lookup"><span data-stu-id="ede26-129">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="ede26-130">Les types de paramètres d’un constructeur doivent être au moins aussi accessibles que le constructeur lui-même.</span><span class="sxs-lookup"><span data-stu-id="ede26-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ede26-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="ede26-131">Example</span></span>  
 <span data-ttu-id="ede26-132">L’exemple suivant contient des déclarations erronées de différents types.</span><span class="sxs-lookup"><span data-stu-id="ede26-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="ede26-133">Le commentaire qui suit chaque déclaration indique l’erreur du compilateur à attendre.</span><span class="sxs-lookup"><span data-stu-id="ede26-133">The comment following each declaration indicates the expected compiler error.</span></span>  
  
```csharp  
// Restrictions on Using Accessibility Levels  
// CS0052 expected as well as CS0053, CS0056, and CS0057  
// To make the program work, change access level of both class B  
// and MyPrivateMethod() to public.  
  
using System;  
  
// A delegate:  
delegate int MyDelegate();  
  
class B  
{  
    // A private method:  
    static int MyPrivateMethod()  
    {  
        return 0;  
    }  
}  
  
public class A  
{  
    // Error: The type B is less accessible than the field A.myField.  
    public B myField = new B();  
  
    // Error: The type B is less accessible  
    // than the constant A.myConst.  
    public readonly B myConst = new B();  
  
    public B MyMethod()  
    {  
        // Error: The type B is less accessible   
        // than the method A.MyMethod.  
        return new B();  
    }  
  
    // Error: The type B is less accessible than the property A.MyProp  
    public B MyProp  
    {  
        set  
        {  
        }  
    }  
  
    MyDelegate d = new MyDelegate(B.MyPrivateMethod);  
    // Even when B is declared public, you still get the error:   
    // "The parameter B.MyPrivateMethod is not accessible due to   
    // protection level."  
  
    public static B operator +(A m1, B m2)  
    {  
        // Error: The type B is less accessible  
        // than the operator A.operator +(A,B)  
        return new B();  
    }  
  
    static void Main()  
    {  
        Console.Write("Compiled successfully");  
    }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="ede26-134">Spécification du langage C#</span><span class="sxs-lookup"><span data-stu-id="ede26-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ede26-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ede26-135">See Also</span></span>  
 [<span data-ttu-id="ede26-136">Référence C#</span><span class="sxs-lookup"><span data-stu-id="ede26-136">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ede26-137">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="ede26-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ede26-138">Mots clés C#</span><span class="sxs-lookup"><span data-stu-id="ede26-138">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ede26-139">Modificateurs d’accès</span><span class="sxs-lookup"><span data-stu-id="ede26-139">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="ede26-140">Domaine d’accessibilité</span><span class="sxs-lookup"><span data-stu-id="ede26-140">Accessibility Domain</span></span>](../../../csharp/language-reference/keywords/accessibility-domain.md)  
 [<span data-ttu-id="ede26-141">Niveaux d’accessibilité</span><span class="sxs-lookup"><span data-stu-id="ede26-141">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="ede26-142">Modificateurs d’accès</span><span class="sxs-lookup"><span data-stu-id="ede26-142">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="ede26-143">public</span><span class="sxs-lookup"><span data-stu-id="ede26-143">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="ede26-144">private</span><span class="sxs-lookup"><span data-stu-id="ede26-144">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="ede26-145">protected</span><span class="sxs-lookup"><span data-stu-id="ede26-145">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="ede26-146">internal</span><span class="sxs-lookup"><span data-stu-id="ede26-146">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

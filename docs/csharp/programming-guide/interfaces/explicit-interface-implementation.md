---
title: Implémentation d’interface explicite - Guide de programmation C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: e985da878ca4160938f29911d4313ee6cd731aeb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244828"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="68d7d-102">Implémentation d’interface explicite (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="68d7d-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="68d7d-103">Si une [classe](../../../csharp/language-reference/keywords/class.md) implémente deux interfaces qui contiennent un membre avec la même signature, l’implémentation de ce membre sur la classe a pour conséquence que les deux interfaces utilisent ce membre comme leur implémentation.</span><span class="sxs-lookup"><span data-stu-id="68d7d-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="68d7d-104">Dans l’exemple suivant, tous les appels à `Paint` appellent la même méthode.</span><span class="sxs-lookup"><span data-stu-id="68d7d-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 <span data-ttu-id="68d7d-105">Toutefois, si les deux membres d’[interface](../../../csharp/language-reference/keywords/interface.md) n’exécutent pas la même fonction, cela peut engendrer une implémentation incorrecte d’une interface ou des deux.</span><span class="sxs-lookup"><span data-stu-id="68d7d-105">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="68d7d-106">Il est possible d’implémenter un membre d’interface explicitement, en créant un membre de classe qui n’est appelé que via l’interface et qui est spécifique à cette interface.</span><span class="sxs-lookup"><span data-stu-id="68d7d-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="68d7d-107">Pour ce faire, vous devez nommer le membre de classe avec le nom de l’interface et un point.</span><span class="sxs-lookup"><span data-stu-id="68d7d-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="68d7d-108">Exemple :</span><span class="sxs-lookup"><span data-stu-id="68d7d-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 <span data-ttu-id="68d7d-109">Le membre de classe `IControl.Paint` est disponible uniquement via l’interface `IControl` et `ISurface.Paint` est disponible uniquement via `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="68d7d-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="68d7d-110">Les deux implémentations de méthode sont distinctes, et aucune n’est directement disponible sur la classe.</span><span class="sxs-lookup"><span data-stu-id="68d7d-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="68d7d-111">Exemple :</span><span class="sxs-lookup"><span data-stu-id="68d7d-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 <span data-ttu-id="68d7d-112">L’implémentation explicite est également utilisée pour résoudre les cas où deux interfaces déclarent chacune des membres différents du même nom, comme une propriété et une méthode :</span><span class="sxs-lookup"><span data-stu-id="68d7d-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 <span data-ttu-id="68d7d-113">Pour implémenter les deux interfaces, une classe doit utiliser l’implémentation explicite pour la propriété P, la méthode P, ou les deux, pour éviter une erreur du compilateur.</span><span class="sxs-lookup"><span data-stu-id="68d7d-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="68d7d-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="68d7d-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="68d7d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68d7d-115">See Also</span></span>

- [<span data-ttu-id="68d7d-116">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="68d7d-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="68d7d-117">Classes et structs</span><span class="sxs-lookup"><span data-stu-id="68d7d-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="68d7d-118">Interfaces</span><span class="sxs-lookup"><span data-stu-id="68d7d-118">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
- [<span data-ttu-id="68d7d-119">Héritage</span><span class="sxs-lookup"><span data-stu-id="68d7d-119">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

---
title: Modèles de programmation asynchrone
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e399a512d2bee636aec35e008c0632ce9c5fa781
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44249034"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="0e2d6-102">Modèles de programmation asynchrone</span><span class="sxs-lookup"><span data-stu-id="0e2d6-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="0e2d6-103">Le .NET Framework propose trois modèles d’exécution d’opérations asynchrones :</span><span class="sxs-lookup"><span data-stu-id="0e2d6-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="0e2d6-104">Le **modèle de programmation asynchrone (APM)** (également appelé modèle <xref:System.IAsyncResult>), dans lequel les opérations asynchrones nécessitent les méthodes `Begin` et `End` (par exemple, `BeginWrite` et `EndWrite` pour les opérations d'écriture asynchrones).</span><span class="sxs-lookup"><span data-stu-id="0e2d6-104">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="0e2d6-105">Ce modèle n’est plus recommandé pour un futur développement.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="0e2d6-106">Pour plus d’informations sur la programmation asynchrone, consultez [Modèle de programmation asynchrone (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="0e2d6-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="0e2d6-107">Le **modèle asynchrone basé sur les événements (EAP)**, qui nécessite une méthode avec le suffixe `Async`, ainsi qu'un ou plusieurs événements, des types de délégués de gestionnaire d'événements et des types dérivés de `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-107">**Event-based Asynchronous Pattern (EAP)**, which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="0e2d6-108">Ce modèle a été introduit avec le .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="0e2d6-109">Il n'est plus recommandé pour un futur développement.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="0e2d6-110">Pour plus d'informations, consultez [Modèle asynchrone basé sur des événements (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="0e2d6-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="0e2d6-111">Le **modèle asynchrone basé sur les tâches (TAP)**, qui utilise une méthode unique pour représenter le lancement et l’achèvement d’une opération asynchrone.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-111">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="0e2d6-112">Ce modèle a été introduit avec le .NET Framework 4. Il s'agit de la méthode recommandée pour la programmation asynchrone dans le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="0e2d6-113">Les mots clés [async](~/docs/csharp/language-reference/keywords/async.md) et [await](~/docs/csharp/language-reference/keywords/await.md) en C#, ainsi que les opérateurs [Async](~/docs/visual-basic/language-reference/modifiers/async.md) et [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en Visual Basic ajoutent au modèle TAP la prise en charge des langages.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="0e2d6-114">Pour plus d’informations, consultez [Modèle asynchrone basé sur des tâches (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="0e2d6-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="0e2d6-115">Comparaison des modèles</span><span class="sxs-lookup"><span data-stu-id="0e2d6-115">Comparing Patterns</span></span>  

<span data-ttu-id="0e2d6-116">Pour comprendre rapidement la façon dont chacun des trois modèles modélise les opérations asynchrones, prenons une méthode `Read` qui lit une quantité de données spécifiée dans une mémoire tampon fournie, en commençant à l'offset spécifié :</span><span class="sxs-lookup"><span data-stu-id="0e2d6-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="0e2d6-117">Le modèle APM de cette méthode exposerait les méthodes `BeginRead` et `EndRead` :</span><span class="sxs-lookup"><span data-stu-id="0e2d6-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="0e2d6-118">Le modèle EAP exposerait l'ensemble de types et de membres suivant :</span><span class="sxs-lookup"><span data-stu-id="0e2d6-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="0e2d6-119">Le modèle TAP exposerait l'unique méthode `ReadAsync` suivante :</span><span class="sxs-lookup"><span data-stu-id="0e2d6-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="0e2d6-120">Pour plus d'informations sur les modèles TAP, APM et EAP, consultez les liens fournis dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="0e2d6-121">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0e2d6-121">Related topics</span></span>

| <span data-ttu-id="0e2d6-122">Titre</span><span class="sxs-lookup"><span data-stu-id="0e2d6-122">Title</span></span> | <span data-ttu-id="0e2d6-123">Description</span><span class="sxs-lookup"><span data-stu-id="0e2d6-123">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="0e2d6-124">Modèle de programmation asynchrone</span><span class="sxs-lookup"><span data-stu-id="0e2d6-124">Asynchronous Programming Model (APM)</span></span>](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | <span data-ttu-id="0e2d6-125">Décrit le modèle hérité qui utilise l'interface <xref:System.IAsyncResult> pour fournir un comportement asynchrone.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="0e2d6-126">Ce modèle n'est plus recommandé pour un futur développement.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-126">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="0e2d6-127">Modèle asynchrone basé sur les événements (EAP)</span><span class="sxs-lookup"><span data-stu-id="0e2d6-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | <span data-ttu-id="0e2d6-128">Décrit le modèle hérité basé sur les événements qui fournit un comportement asynchrone.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="0e2d6-129">Ce modèle n'est plus recommandé pour un futur développement.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-129">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="0e2d6-130">Modèle asynchrone basé sur les tâches (TAP, Task-based Asynchronous Pattern)</span><span class="sxs-lookup"><span data-stu-id="0e2d6-130">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | <span data-ttu-id="0e2d6-131">Décrit le nouveau modèle asynchrone basé sur l'espace de noms <xref:System.Threading.Tasks>.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="0e2d6-132">Ce modèle est recommandé pour la programmation asynchrone dans le .NET Framework 4 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="0e2d6-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0e2d6-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e2d6-133">See also</span></span>

- [<span data-ttu-id="0e2d6-134">Programmation asynchrone en C#</span><span class="sxs-lookup"><span data-stu-id="0e2d6-134">Asynchronous programming in C#</span></span>](~/docs/csharp/async.md)   
- [<span data-ttu-id="0e2d6-135">Programmation asynchrone en F#</span><span class="sxs-lookup"><span data-stu-id="0e2d6-135">Async Programming in F#</span></span>](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)   
- [<span data-ttu-id="0e2d6-136">Programmation asynchrone avec Async et Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e2d6-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)

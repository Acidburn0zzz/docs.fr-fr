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
# <a name="asynchronous-programming-patterns"></a>Modèles de programmation asynchrone

Le .NET Framework propose trois modèles d’exécution d’opérations asynchrones :  
  
- Le **modèle de programmation asynchrone (APM)** (également appelé modèle <xref:System.IAsyncResult>), dans lequel les opérations asynchrones nécessitent les méthodes `Begin` et `End` (par exemple, `BeginWrite` et `EndWrite` pour les opérations d'écriture asynchrones). Ce modèle n’est plus recommandé pour un futur développement. Pour plus d’informations sur la programmation asynchrone, consultez [Modèle de programmation asynchrone (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).  
  
- Le **modèle asynchrone basé sur les événements (EAP)**, qui nécessite une méthode avec le suffixe `Async`, ainsi qu'un ou plusieurs événements, des types de délégués de gestionnaire d'événements et des types dérivés de `EventArg`. Ce modèle a été introduit avec le .NET Framework 2.0. Il n'est plus recommandé pour un futur développement. Pour plus d'informations, consultez [Modèle asynchrone basé sur des événements (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).  
  
- Le **modèle asynchrone basé sur les tâches (TAP)**, qui utilise une méthode unique pour représenter le lancement et l’achèvement d’une opération asynchrone. Ce modèle a été introduit avec le .NET Framework 4. Il s'agit de la méthode recommandée pour la programmation asynchrone dans le .NET Framework. Les mots clés [async](~/docs/csharp/language-reference/keywords/async.md) et [await](~/docs/csharp/language-reference/keywords/await.md) en C#, ainsi que les opérateurs [Async](~/docs/visual-basic/language-reference/modifiers/async.md) et [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en Visual Basic ajoutent au modèle TAP la prise en charge des langages. Pour plus d’informations, consultez [Modèle asynchrone basé sur des tâches (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).  
  
## <a name="comparing-patterns"></a>Comparaison des modèles  

Pour comprendre rapidement la façon dont chacun des trois modèles modélise les opérations asynchrones, prenons une méthode `Read` qui lit une quantité de données spécifiée dans une mémoire tampon fournie, en commençant à l'offset spécifié :  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
Le modèle APM de cette méthode exposerait les méthodes `BeginRead` et `EndRead` :  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
Le modèle EAP exposerait l'ensemble de types et de membres suivant :  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
Le modèle TAP exposerait l'unique méthode `ReadAsync` suivante :  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
Pour plus d'informations sur les modèles TAP, APM et EAP, consultez les liens fournis dans la section suivante.  
  
## <a name="related-topics"></a>Rubriques connexes

| Titre | Description |
| ----- | ----------- |
| [Modèle de programmation asynchrone](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | Décrit le modèle hérité qui utilise l'interface <xref:System.IAsyncResult> pour fournir un comportement asynchrone. Ce modèle n'est plus recommandé pour un futur développement. |
| [Modèle asynchrone basé sur les événements (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | Décrit le modèle hérité basé sur les événements qui fournit un comportement asynchrone. Ce modèle n'est plus recommandé pour un futur développement. |
| [Modèle asynchrone basé sur les tâches (TAP, Task-based Asynchronous Pattern)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | Décrit le nouveau modèle asynchrone basé sur l'espace de noms <xref:System.Threading.Tasks>. Ce modèle est recommandé pour la programmation asynchrone dans le .NET Framework 4 et versions ultérieures. |

## <a name="see-also"></a>Voir aussi

- [Programmation asynchrone en C#](~/docs/csharp/async.md)   
- [Programmation asynchrone en F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)   
- [Programmation asynchrone avec Async et Await (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/async/index.md)

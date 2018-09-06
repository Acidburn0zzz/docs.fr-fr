---
title: Threads (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 704bb04b-ff23-471d-ab12-3cec1c2bca59
ms.openlocfilehash: f477a36c6ffa0b5a809c8ba899b21d19a8c9a2d8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861944"
---
# <a name="threading-visual-basic"></a>Threads (Visual Basic)
Les threads donnent la possibilité à votre programme Visual Basic d’effectuer des traitements simultanés, ce qui vous permet de faire plusieurs opérations à la fois. Par exemple, vous pouvez utiliser les threads pour surveiller les entrées de l’utilisateur, effectuer des tâches en arrière-plan et gérer des flux d’entrée simultanés.  
  
 Les threads ont les propriétés suivantes :  
  
-   Les threads permettent à votre programme d’effectuer un traitement simultané.  
  
-   L’espace de noms <xref:System.Threading> du .NET Framework facilite l’utilisation des threads.  
  
-   Les threads partagent les ressources de l’application. Pour plus d’informations, consultez [Using Threads and Threading](../../../../standard/threading/using-threads-and-threading.md).  
  
 Par défaut, un programme Visual Basic a un seul thread. Cependant, vous pouvez créer et utiliser des threads auxiliaires pour exécuter du code en parallèle avec le thread principal. Ces threads sont souvent appelés des *threads de travail*.  
  
 Les threads de travail peuvent être utilisés pour effectuer des tâches longues ou à durée critique sans bloquer le thread principal. Par exemple, les threads de travail sont souvent utilisés dans les applications serveur pour répondre à des demandes entrantes sans attendre que la demande précédente soit terminée. Les threads de travail sont également utilisés pour effectuer des tâches « en arrière-plan » dans les applications de poste de travail pour que le thread principal, qui pilote les éléments de l’interface utilisateur, continue de répondre aux actions de l’utilisateur.  
  
 Les threads résolvent les problèmes de débit et de réactivité, mais ils peuvent aussi introduire des problèmes de partage des ressources, comme des interblocages et des situations de concurrence. Les threads multiples conviennent mieux pour les tâches qui nécessitent des ressources différentes, comme les descripteurs de fichiers et les connexions réseau. L’affectation de plusieurs threads à une même ressource risque de provoquer des problèmes de synchronisation et d’aboutir au blocage fréquent des threads dans l’attente d’autres threads, ce qui est contraire à l’objectif poursuivi par l’utilisation de plusieurs threads.  
  
 Une stratégie courante consiste à utiliser des threads de travail pour effectuer des tâches longues ou à durée critique qui nécessitent peu les ressources utilisées par d’autres threads. Naturellement, plusieurs threads doivent accéder à certaines ressources de votre programme. Pour ces situations, l’espace de noms <xref:System.Threading> fournit des classes pour la synchronisation des threads. Ces classes sont <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> et <xref:System.Threading.ManualResetEvent>.  
  
 Vous pouvez utiliser tout ou partie de ces classes pour synchroniser les activités de plusieurs threads, mais le langage Visual Basic offre lui-même une certaine prise en charge des threads. Par exemple, l’[instruction SyncLock](../../../../visual-basic/language-reference/statements/synclock-statement.md) fournit des fonctionnalités de synchronisation via l’utilisation implicite de <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  À compter du [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], la programmation multithread est considérablement simplifiée avec les classes <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> et <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../../standard/parallel-programming/parallel-linq-plinq.md), de nouvelles classes de collections simultanées dans l’espace de noms <xref:System.Collections.Concurrent?displayProperty=nameWithType>, et un nouveau modèle de programmation basé sur le concept de tâche au lieu de celui de thread. Pour plus d’informations, consultez la page [Programmation parallèle](../../../../standard/parallel-programming/index.md).  
  
## <a name="related-topics"></a>Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Synchronisation des threads (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)|Décrit comment contrôler les interactions des threads.|  
|[Thread](../../../../standard/threading/index.md)|Décrit comment implémenter des threads dans le .NET Framework.|

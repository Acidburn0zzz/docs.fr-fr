---
title: Réglage de votre Application Async (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: 88b26aea0740bb4a5c5e9d87790746a708bf45a1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838005"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Réglage de votre Application Async (Visual Basic)
Vous pouvez ajouter de la précision et de la flexibilité à vos applications asynchrones en utilisant les méthodes et les propriétés qui sont mises à disposition par le type <xref:System.Threading.Tasks.Task>. Les rubriques de cette section présentent des exemples qui utilisent <xref:System.Threading.CancellationToken> et des méthodes `Task` importantes telles que <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> et <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 En utilisant `WhenAny` et `WhenAll`, vous pouvez plus facilement démarrer plusieurs tâches et attendre leur achèvement en ne surveillant qu’une seule tâche.  
  
-   `WhenAny` retourne une tâche qui se termine lorsque l’une des tâches d’une collection est terminée.  
  
     Pour obtenir des exemples qui utilisent `WhenAny`, consultez [annuler les tâches Async restantes après elles est terminée (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)et [démarrer plusieurs tâches Async et processus les terminées (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
-   `WhenAll` retourne une tâche qui se termine lorsque toutes les tâches d’une collection sont terminées.  
  
     Pour obtenir des informations supplémentaires et un exemple de code qui utilise `WhenAll`, consultez [Guide pratique pour Étendre la procédure pas à pas Async à l’aide de Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Cette section comprend les exemples suivants :  
  
-   [Annuler une tâche asynchrone ou une liste de tâches (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).  
  
-   [Annuler des tâches Asynch après une période de temps (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [Annuler les tâches Asynch restantes après une est terminée (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [Démarrer plusieurs tâches Asynch et les traiter une fois terminées (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  Pour exécuter les exemples, Visual Studio version 2012 ou ultérieure et le .NET Framework version 4.5 ou ultérieure doivent être installés sur votre ordinateur.  
  
 Les projets créent une interface utilisateur qui contient un bouton permettant de démarrer le processus et un autre permettant de l’annuler, comme dans l’image suivante. Ces boutons se nomment `startButton` et `cancelButton`.  
  
 ![Fenêtre WPF avec bouton Annuler](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Boîte de dialogue avec bouton Démarrer et Arrêter")  
  
 Vous pouvez télécharger l’intégralité des projets WPF (Windows Presentation Foundation) à partir de la page [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Exemple Async : Réglage précis de votre application).  
  
## <a name="see-also"></a>Voir aussi

- [Programmation asynchrone avec Async et Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)

---
title: "Comment : retourner une valeur à partir d’une tâche"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4497f7f9c6802a9b3d4edca66ceb4a894a59646a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-return-a-value-from-a-task"></a>Comment : retourner une valeur à partir d’une tâche
Cet exemple montre comment utiliser le type <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> pour retourner une valeur à partir de la propriété <xref:System.Threading.Tasks.Task%601.Result%2A>. Il nécessite que le répertoire C:\Users\Public\Pictures\Sample Pictures\ existe et qu'il contienne des fichiers.  
  
## <a name="example"></a>Exemple  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 La propriété <xref:System.Threading.Tasks.Task%601.Result%2A> bloque le thread appelant jusqu'à ce que la tâche se termine.  
  
 Pour savoir comment passer le résultat d’une <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> à une tâche de continuation, consultez [Chaînage des tâches à l’aide de tâches de continuation](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation asynchrone basée sur les tâches](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [Expressions lambda en PLINQ et dans la bibliothèque parallèle de tâches](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)

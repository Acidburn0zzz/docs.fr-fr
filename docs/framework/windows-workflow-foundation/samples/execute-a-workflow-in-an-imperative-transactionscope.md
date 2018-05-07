---
title: Exécuter un workflow dans un TransactionScope impératif
ms.date: 03/30/2017
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
ms.openlocfilehash: 44efc13efaa45274068fb44cc154b515bd774a35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a>Exécuter un workflow dans un TransactionScope impératif
Cet exemple montre comment exécuter un workflow à l'aide de <xref:System.Activities.WorkflowInvoker> sous un <xref:System.Transactions.Transaction> à partir de code C# impératif.  
  
## <a name="sample-details"></a>Détails de l'exemple  
 Dans le code C# impératif, le <xref:System.Transactions.TransactionScope> est utilisé pour encapsuler un jeu de travail qui est exécuté sous la même transaction. Le <xref:System.Transactions.TransactionScope> fonctionne en créant une transaction ambiante et en initialisant la propriété <xref:System.Transactions.Transaction.Current%2A>, qui est ensuite accessible par tout travail qui est exécuté sur ce thread.  
  
 Pour obtenir un comportement équivalent dans le workflow, l'exécution doit effectuer le travail supplémentaire d'initialisation de <xref:System.Transactions.Transaction.Current%2A> avant d'exécuter chaque activité parce qu'un workflow ne gère pas l'affinité de thread entre les activités. Le comportement résultant est avec cette prise en charge de l'exécution est que, lors de l'exécution d'un workflow avec <xref:System.Activities.WorkflowInvoker> à l'intérieur d'un <xref:System.Transactions.TransactionScope>, l'exécution de toutes les activités est garantie sous le contexte de la transaction ambiante créée par le <xref:System.Transactions.TransactionScope>.  
  
 Un workflow peut avoir uniquement une transaction ambiante unique pour chaque instance de workflow ; les transactions imbriquées ne sont pas disponibles. Même si le workflow contient une activité <xref:System.Activities.Statements.TransactionScope>, cela ne crée pas de transaction interne. À la place, la transaction ambiante créée à l'extérieur du workflow est réutilisée.  
  
 L'exemple commence un nouveau <xref:System.Transactions.TransactionScope>, imprime l'ID de transaction et démarre un workflow à l'aide de <xref:System.Activities.WorkflowInvoker>. Le workflow imprime à nouveau l'ID de transaction, ce qui montre qu'il s'agit de la même transaction, exécute un <xref:System.Activities.Statements.TransactionScope>, puis se termine. L'appel <xref:System.Activities.WorkflowInvoker.Invoke%2A> sur <xref:System.Activities.WorkflowInvoker> étant synchrone, le thread d'origine se bloque jusqu'à ce que le workflow soit terminé. Une fois le workflow terminé, la transaction est effectuée et les ressources supprimées.  
  
#### <a name="to-use-this-sample"></a>Pour utiliser cet exemple  
  
1.  À l'aide de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ouvrez le fichier solution ImperativeTransactionSample.sln.  
  
2.  Pour générer la solution, appuyez sur Ctrl+Maj+B.  
  
3.  Pour exécuter la solution, appuyez sur F5.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples Windows Workflow Foundation (WF) pour .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`
---
title: Exceptions, transactions et compensation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e83661ba66ca6a71f26c11172902d5bc602a2f6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="59251-102">Exceptions, transactions et compensation</span><span class="sxs-lookup"><span data-stu-id="59251-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="59251-103"> fournit plusieurs mécanismes différents pour gérer les conditions d'erreur d'exécution dans les workflows.</span><span class="sxs-lookup"><span data-stu-id="59251-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="59251-104">Les workflows peuvent utiliser une combinaison de gestionnaires d’exceptions, transactions, annulation et compensation pour gérer et effectuer une récupération normale à partir des conditions d’erreur.</span><span class="sxs-lookup"><span data-stu-id="59251-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59251-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="59251-105">In This Section</span></span>  
 [<span data-ttu-id="59251-106">Exceptions</span><span class="sxs-lookup"><span data-stu-id="59251-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="59251-107">Montre comment utiliser l'activité <xref:System.Activities.Statements.TryCatch> pour gérer des exceptions dans un workflow.</span><span class="sxs-lookup"><span data-stu-id="59251-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="59251-108">Transactions</span><span class="sxs-lookup"><span data-stu-id="59251-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="59251-109">Montre comment utiliser l'activité <xref:System.Activities.Statements.TransactionScope> pour utiliser des transactions dans un workflow.</span><span class="sxs-lookup"><span data-stu-id="59251-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="59251-110">Compensation</span><span class="sxs-lookup"><span data-stu-id="59251-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="59251-111">Décrit la compensation dans les workflows et montre comment utiliser des activités de compensation telles que <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> et <xref:System.Activities.Statements.Confirm>.</span><span class="sxs-lookup"><span data-stu-id="59251-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="59251-112">Annulation</span><span class="sxs-lookup"><span data-stu-id="59251-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="59251-113">Explique comment effectuer la gestion des annulations dans les workflows à l'aide d'activités intégrées ainsi que d'activités personnalisées.</span><span class="sxs-lookup"><span data-stu-id="59251-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="59251-114">Débogage de workflows</span><span class="sxs-lookup"><span data-stu-id="59251-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="59251-115">Décrit comment déboguer des workflows.</span><span class="sxs-lookup"><span data-stu-id="59251-115">Describes how to debug workflows.</span></span>

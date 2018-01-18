---
title: "Retourner le premier élément d'une séquence"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bbdfe78f15490ce2c6722c83a4615ca29cbc5863
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/17/2018
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="8f97b-102">Retourner le premier élément d'une séquence</span><span class="sxs-lookup"><span data-stu-id="8f97b-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="8f97b-103">Utilisez l'opérateur <xref:System.Linq.Enumerable.First%2A> pour retourner le premier élément d'une séquence.</span><span class="sxs-lookup"><span data-stu-id="8f97b-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="8f97b-104">Les requêtes qui utilisent <xref:System.Linq.Enumerable.First%2A> sont exécutées immédiatement.</span><span class="sxs-lookup"><span data-stu-id="8f97b-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="8f97b-105"> ne prend pas en charge l'opérateur <xref:System.Linq.Enumerable.Last%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f97b-105"> does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f97b-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="8f97b-106">Example</span></span>  
 <span data-ttu-id="8f97b-107">Le code suivant recherche le premier `Shipper` dans une table :</span><span class="sxs-lookup"><span data-stu-id="8f97b-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="8f97b-108">Si vous exécutez cette requête sur l'exemple de base de données Northwind, vous obtenez le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="8f97b-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="8f97b-109">`ID = 1, Company = Speedy Express`.</span><span class="sxs-lookup"><span data-stu-id="8f97b-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="8f97b-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="8f97b-110">Example</span></span>  
 <span data-ttu-id="8f97b-111">Le code suivant recherche le seul `Customer` qui a BONAP comme `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="8f97b-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="8f97b-112">Si vous exécutez cette requête sur l'exemple de base de données Northwind, vous obtenez `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="8f97b-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="8f97b-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f97b-113">See Also</span></span>  
 [<span data-ttu-id="8f97b-114">Exemples de requêtes</span><span class="sxs-lookup"><span data-stu-id="8f97b-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="8f97b-115">Téléchargement d’exemples de base de données</span><span class="sxs-lookup"><span data-stu-id="8f97b-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)

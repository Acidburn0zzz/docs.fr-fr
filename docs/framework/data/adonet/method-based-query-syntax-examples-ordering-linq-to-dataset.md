---
title: 'Exemples de syntaxe de requête fondée sur une méthode : Classement (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 5e8a0669525e78f025d96b00edbaaf25486f339a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632866"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="e27e7-102">Exemples de syntaxe de requête fondée sur une méthode : Classement (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e27e7-102">Method-Based Query Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="e27e7-103">Les exemples de cette rubrique montrent comment utiliser les méthodes <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Reverse%2A> et <xref:System.Linq.Enumerable.ThenBy%2A> pour interroger un <xref:System.Data.DataSet> et classer les résultats à l'aide de la syntaxe d'interrogation de méthode.</span><span class="sxs-lookup"><span data-stu-id="e27e7-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenBy%2A> methods to query a <xref:System.Data.DataSet> and order the results using the method query syntax.</span></span>  
  
 <span data-ttu-id="e27e7-104">Le `FillDataSet` méthode utilisé dans ces exemples est spécifiée dans [chargement des données dans un jeu de données](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="e27e7-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e27e7-105">Les exemples de cette rubrique utilisent les tables Contact, Address, Product, SalesOrderHeader et SalesOrderDetail de l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e27e7-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e27e7-106">Les exemples de cette rubrique utilisent les éléments suivants `using` / `Imports` instructions :</span><span class="sxs-lookup"><span data-stu-id="e27e7-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="e27e7-107">Pour plus d'informations, voir [Procédure : Créer un projet LINQ to DataSet dans Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e27e7-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="e27e7-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="e27e7-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="e27e7-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="e27e7-109">Example</span></span>  
 <span data-ttu-id="e27e7-110">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.OrderBy%2A> avec un comparateur personnalisé pour effectuer un tri des noms ne respectant pas la casse.</span><span class="sxs-lookup"><span data-stu-id="e27e7-110">This example uses the <xref:System.Linq.Enumerable.OrderBy%2A> method with a custom comparer to do a case-insensitive sort of last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a><span data-ttu-id="e27e7-111">Reverse</span><span class="sxs-lookup"><span data-stu-id="e27e7-111">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="e27e7-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="e27e7-112">Example</span></span>  
 <span data-ttu-id="e27e7-113">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.Reverse%2A> pour créer une liste des commandes où `OrderDate` est antérieure au 20 février 2002.</span><span class="sxs-lookup"><span data-stu-id="e27e7-113">This example uses the <xref:System.Linq.Enumerable.Reverse%2A> method to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a><span data-ttu-id="e27e7-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="e27e7-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="e27e7-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="e27e7-115">Example</span></span>  
 <span data-ttu-id="e27e7-116">Cet exemple utilise les méthodes <xref:System.Linq.Enumerable.OrderBy%2A> et <xref:System.Linq.Enumerable.ThenBy%2A> avec un comparateur personnalisé pour effectuer un premier tri par prix courant, puis un tri décroissant ne respectant pas la casse des noms de produits.</span><span class="sxs-lookup"><span data-stu-id="e27e7-116">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.ThenBy%2A> methods with a custom comparer to first sort by list price, and then perform a case-insensitive descending sort of the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="e27e7-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e27e7-117">See also</span></span>
- [<span data-ttu-id="e27e7-118">Chargement de données dans un DataSet</span><span class="sxs-lookup"><span data-stu-id="e27e7-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="e27e7-119">Exemples LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e27e7-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="e27e7-120">Vue d’ensemble des opérateurs de requête standard</span><span class="sxs-lookup"><span data-stu-id="e27e7-120">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)

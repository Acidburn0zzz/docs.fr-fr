---
title: "Exemples de syntaxe de requête d'expression de requête : restriction (LINQ to DataSet)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 556b1cc31f42cecc19492412120b31da83eff609
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43733834"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="2c93c-102">Exemples de syntaxe de requête d'expression de requête : restriction (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="2c93c-102">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>
<span data-ttu-id="2c93c-103">Les exemples de cette rubrique montrent comment utiliser la méthode <xref:System.Linq.Enumerable.Where%2A> pour interroger un <xref:System.Data.DataSet> à l'aide de la syntaxe d'expression de requête.</span><span class="sxs-lookup"><span data-stu-id="2c93c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="2c93c-104">Le `FillDataSet` méthode utilisé dans ces exemples est spécifiée dans [chargement des données dans un jeu de données](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="2c93c-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="2c93c-105">Les exemples de cette rubrique utilisent les tables Contact, Address, Product, SalesOrderHeader et SalesOrderDetail de l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2c93c-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="2c93c-106">Les exemples de cette rubrique utilisent les éléments suivants `using` / `Imports` instructions :</span><span class="sxs-lookup"><span data-stu-id="2c93c-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 <span data-ttu-id="2c93c-107">Pour plus d’informations, consultez [Comment : créer un LINQ to DataSet Project dans Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2c93c-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="2c93c-108">Où</span><span class="sxs-lookup"><span data-stu-id="2c93c-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="2c93c-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="2c93c-109">Example</span></span>  
 <span data-ttu-id="2c93c-110">Cet exemple retourne toutes les commandes en ligne.</span><span class="sxs-lookup"><span data-stu-id="2c93c-110">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a><span data-ttu-id="2c93c-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="2c93c-111">Example</span></span>  
 <span data-ttu-id="2c93c-112">Cet exemple retourne les commandes où la quantité commandée est supérieure à 2 et inférieure à 6.</span><span class="sxs-lookup"><span data-stu-id="2c93c-112">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a><span data-ttu-id="2c93c-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="2c93c-113">Example</span></span>  
 <span data-ttu-id="2c93c-114">Cet exemple retourne tous les produits de couleur rouge.</span><span class="sxs-lookup"><span data-stu-id="2c93c-114">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a><span data-ttu-id="2c93c-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="2c93c-115">Example</span></span>  
 <span data-ttu-id="2c93c-116">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.Where%2A> pour rechercher des commandes qui ont été passées après le 1er décembre 2002, puis utilise la méthode <xref:System.Data.DataRow.GetChildRows%2A> pour obtenir les détails de chaque commande.</span><span class="sxs-lookup"><span data-stu-id="2c93c-116">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="2c93c-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c93c-117">See Also</span></span>  
 [<span data-ttu-id="2c93c-118">Chargement de données dans un DataSet</span><span class="sxs-lookup"><span data-stu-id="2c93c-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="2c93c-119">Exemples LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2c93c-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="2c93c-120">Vue d’ensemble des opérateurs de requête standard</span><span class="sxs-lookup"><span data-stu-id="2c93c-120">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)

---
title: 'Exemples de syntaxe de requête fondée sur une méthode : projection (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0fc2c8f0-1967-4f30-8b20-39b8dccfb82f
ms.openlocfilehash: 5887ae58c142cb4c1835599e6a7b34bf200d7071
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757747"
---
# <a name="method-based-query-syntax-examples-projection-linq-to-dataset"></a><span data-ttu-id="bc503-102">Exemples de syntaxe de requête fondée sur une méthode : projection (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="bc503-102">Method-Based Query Syntax Examples: Projection (LINQ to DataSet)</span></span>
<span data-ttu-id="bc503-103">Les exemples de cette rubrique montrent comment utiliser les méthodes <xref:System.Linq.Enumerable.Select%2A> et <xref:System.Linq.Enumerable.SelectMany%2A> pour interroger un <xref:System.Data.DataSet> à l'aide de la syntaxe de requête fondée sur une méthode.</span><span class="sxs-lookup"><span data-stu-id="bc503-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet> using the method-based query syntax.</span></span>  
  
 <span data-ttu-id="bc503-104">Le `FillDataSet` méthode utilisé dans ces exemples est spécifiée dans [chargement des données dans un groupe de données](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="bc503-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="bc503-105">Les exemples de cette rubrique utilisent les tables Contact, Address, Product, SalesOrderHeader et SalesOrderDetail de l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="bc503-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="bc503-106">Les exemples de cette rubrique utilisent les éléments suivants `using` / `Imports` instructions :</span><span class="sxs-lookup"><span data-stu-id="bc503-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="bc503-107">Pour plus d’informations, consultez [Comment : créer une LINQ to DataSet Project dans Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="bc503-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="select"></a><span data-ttu-id="bc503-108">Sélectionner</span><span class="sxs-lookup"><span data-stu-id="bc503-108">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="bc503-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="bc503-109">Example</span></span>  
 <span data-ttu-id="bc503-110">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.Select%2A> pour projeter les propriétés `Name`, `ProductNumber` et `ListPrice` dans une séquence de types anonymes.</span><span class="sxs-lookup"><span data-stu-id="bc503-110">This example uses the <xref:System.Linq.Enumerable.Select%2A> method to project the `Name`, `ProductNumber`, and `ListPrice` properties to a sequence of anonymous types.</span></span>  <span data-ttu-id="bc503-111">La propriété `ListPrice` est également renommée en `Price` dans le type résultant.</span><span class="sxs-lookup"><span data-stu-id="bc503-111">The `ListPrice` property is also renamed to `Price` in the resulting type.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="bc503-112">SelectMany</span><span class="sxs-lookup"><span data-stu-id="bc503-112">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="bc503-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="bc503-113">Example</span></span>  
 <span data-ttu-id="bc503-114">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.SelectMany%2A> pour sélectionner toutes les commandes où `TotalDue` est inférieur à 500.</span><span class="sxs-lookup"><span data-stu-id="bc503-114">This example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="bc503-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="bc503-115">Example</span></span>  
 <span data-ttu-id="bc503-116">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.SelectMany%2A> pour sélectionner toutes les commandes qui ont été passées le 1er octobre 2002 ou après.</span><span class="sxs-lookup"><span data-stu-id="bc503-116">This example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="bc503-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc503-117">See Also</span></span>  
 [<span data-ttu-id="bc503-118">Chargement de données dans un DataSet</span><span class="sxs-lookup"><span data-stu-id="bc503-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="bc503-119">Exemples LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="bc503-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="bc503-120">Vue d’ensemble des opérateurs de requête standard</span><span class="sxs-lookup"><span data-stu-id="bc503-120">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)

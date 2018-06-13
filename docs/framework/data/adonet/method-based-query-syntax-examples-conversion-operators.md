---
title: 'Exemples de syntaxe de requête fondée sur une méthode : opérateurs de conversion (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: 47e2a0a510af86055d93603c8c898b00c8d94c87
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763447"
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="2b987-102">Exemples de syntaxe de requête fondée sur une méthode : opérateurs de conversion (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="2b987-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="2b987-103">Les exemples de cette rubrique montrent comment utiliser les méthodes <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> et <xref:System.Linq.Enumerable.ToList%2A> pour exécuter immédiatement une expression de requête.</span><span class="sxs-lookup"><span data-stu-id="2b987-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="2b987-104">Le `FillDataSet` méthode utilisé dans ces exemples est spécifiée dans [chargement des données dans un groupe de données](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="2b987-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="2b987-105">Les exemples de cette rubrique utilisent les tables Contact, Address, Product, SalesOrderHeader et SalesOrderDetail de l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2b987-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="2b987-106">Les exemples de cette rubrique utilisent les éléments suivants `using` / `Imports` instructions :</span><span class="sxs-lookup"><span data-stu-id="2b987-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="2b987-107">Pour plus d’informations, consultez [Comment : créer une LINQ to DataSet Project dans Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2b987-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="2b987-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="2b987-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="2b987-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="2b987-109">Example</span></span>  
 <span data-ttu-id="2b987-110">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.ToArray%2A> pour évaluer immédiatement une séquence dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="2b987-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="2b987-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="2b987-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="2b987-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="2b987-112">Example</span></span>  
 <span data-ttu-id="2b987-113">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.ToDictionary%2A> pour évaluer immédiatement une séquence et une expression clé associée dans un dictionnaire.</span><span class="sxs-lookup"><span data-stu-id="2b987-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="2b987-114">ToList</span><span class="sxs-lookup"><span data-stu-id="2b987-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="2b987-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="2b987-115">Example</span></span>  
 <span data-ttu-id="2b987-116">Cet exemple utilise la méthode <xref:System.Linq.Enumerable.ToList%2A> pour évaluer immédiatement une séquence dans une <xref:System.Collections.Generic.List%601> où `T` est de type <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="2b987-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="2b987-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b987-117">See Also</span></span>  
 [<span data-ttu-id="2b987-118">Chargement de données dans un DataSet</span><span class="sxs-lookup"><span data-stu-id="2b987-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="2b987-119">Exemples LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2b987-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="2b987-120">Vue d’ensemble des opérateurs de requête standard</span><span class="sxs-lookup"><span data-stu-id="2b987-120">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)

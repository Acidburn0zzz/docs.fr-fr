---
title: Interrogation de DataSets typés
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 30a6512202615590a4b399b8ce7173b213a8873c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353483"
---
# <a name="querying-typed-datasets"></a><span data-ttu-id="6c6ed-102">Interrogation de DataSets typés</span><span class="sxs-lookup"><span data-stu-id="6c6ed-102">Querying Typed DataSets</span></span>
<span data-ttu-id="6c6ed-103">Si le schéma du <xref:System.Data.DataSet> est connu au moment du design de l'application, nous vous recommandons d'utiliser un <xref:System.Data.DataSet> typé lors de l'utilisation de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c6ed-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="6c6ed-104">Typé <xref:System.Data.DataSet> est une classe qui dérive d’un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6c6ed-105">De ce fait, il hérite de l'ensemble des méthodes, événements et propriétés d'un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6c6ed-106">En outre, un typé <xref:System.Data.DataSet> fournit des méthodes fortement typées, propriétés et événements.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="6c6ed-107">Cela signifie que vous pouvez accéder à des tables et à des colonnes par leur nom au lieu d’utiliser les méthodes associées à des collections.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="6c6ed-108">Cela rend les requêtes plus simples et plus lisibles.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="6c6ed-109">Pour plus d’informations, consultez [typés](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="6c6ed-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="6c6ed-110"> prend en charge l’interrogation sur typé également <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-110"> also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6c6ed-111">Avec un typé <xref:System.Data.DataSet>, vous n’avez pas à utiliser le type générique <xref:System.Data.DataRowExtensions.Field%2A> méthode ou <xref:System.Data.DataRowExtensions.SetField%2A> méthode pour accéder aux données de colonne.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span>  <span data-ttu-id="6c6ed-112">Noms de propriété sont disponibles au moment de la compilation, car les informations de type sont incluses dans le <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="6c6ed-113"> fournit l’accès aux valeurs de colonne avec le type approprié, afin que les erreurs d’incompatibilité de type sont interceptées lorsque le code est compilé à la place de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="6c6ed-113"> provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>  
  
 <span data-ttu-id="6c6ed-114">Avant de procéder à l'interrogation d'un <xref:System.Data.DataSet> typé, vous devez générer la classe à l'aide du Concepteur de DataSet dans [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c6ed-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the DataSet Designer in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span></span>  <span data-ttu-id="6c6ed-115">Pour plus d’informations, consultez [Créer et configurer des datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="6c6ed-115">For more information, see [Create and configure datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c6ed-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="6c6ed-116">Example</span></span>  
 <span data-ttu-id="6c6ed-117">L'exemple suivant montre une requête sur un <xref:System.Data.DataSet> typé :</span><span class="sxs-lookup"><span data-stu-id="6c6ed-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>  
  
```csharp  
var query = from o in orders  
            where o.OnlineOrderFlag == true  
            select new { o.SalesOrderID,  
                         o.OrderDate,  
                         o.SalesOrderNumber };  
  
foreach(var order in query)   
{  
    Console.WriteLine("{0}\t{1:d}\t{2}",   
order.SalesOrderID,   
order.OrderDate,   
order.SalesOrderNumber);  
}  
```  
  
```vb  
Dim orders = ds.Tables("SalesOrderHeader")  
  
Dim query = _  
       From o In orders _  
       Where o.OnlineOrderFlag = True _  
       Select New {SalesOrderID := o.SalesOrderID, _  
                   OrderDate := o.OrderDate, _  
                   SalesOrderNumber := o.SalesOrderNumber}  
  
For Each Dim onlineOrder In query  
 Console.WriteLine("{0}\t{1:d}\t{2}", _  
 onlineOrder.SalesOrderID, _  
 onlineOrder.OrderDate, _  
 onlineOrder.SalesOrderNumber)  
Next  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c6ed-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c6ed-118">See Also</span></span>  
 [<span data-ttu-id="6c6ed-119">Interrogation de DataSets</span><span class="sxs-lookup"><span data-stu-id="6c6ed-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="6c6ed-120">Requêtes de table croisée</span><span class="sxs-lookup"><span data-stu-id="6c6ed-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [<span data-ttu-id="6c6ed-121">Requêtes de table unique</span><span class="sxs-lookup"><span data-stu-id="6c6ed-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)

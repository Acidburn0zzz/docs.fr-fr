---
title: 'Procédure : Exécuter des requêtes de Service de données (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 62997821-e0c6-4c4d-9fb7-1273fb5e5d18
ms.openlocfilehash: b68595285eb5ec06be86c771733f7bb9036c9f21
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154971"
---
# <a name="how-to-execute-data-service-queries-wcf-data-services"></a>Procédure : Exécuter des requêtes de Service de données (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] vous permet d’interroger un service de données à partir d’une application cliente .NET Framework en utilisant les classes de service de données client généré. Vous pouvez exécuter des requêtes à l'aide d'une des méthodes suivantes :  
  
-   Exécution d'une requête LINQ sur la <xref:System.Data.Services.Client.DataServiceQuery%601> nommée que vous obtenez du <xref:System.Data.Services.Client.DataServiceContext> que l'outil `Add Data Service Reference` génère.  
  
-   Implicitement, en énumérant sur la <xref:System.Data.Services.Client.DataServiceQuery%601> nommée que vous obtenez du <xref:System.Data.Services.Client.DataServiceContext> que l'outil `Add Data Service Reference` génère.  
  
-   Explicitement, en appelant la méthode <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> sur <xref:System.Data.Services.Client.DataServiceQuery%601>, ou la méthode <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> pour une exécution asynchrone.  
  
 Pour plus d’informations, consultez [interrogation du Service de données](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 L'exemple dans cette rubrique utilise l'exemple de service de données Northwind et des classes de service de données clientes générées automatiquement. Ce service et les classes de données client sont créés lorsque vous complétez le [démarrage rapide WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment définir et exécuter une requête LINQ qui retourne tous les `Customers` sur le service de données Northwind.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomerslinq)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomerslinq)]  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment utiliser le contexte que l'outil `Add Data Service Reference` génère pour exécuter implicitement une requête qui retourne tous les `Customers` sur le service de données Northwind. L'URI du jeu d'entités `Customers` demandé est déterminé automatiquement par le contexte. La requête est exécutée implicitement lorsque l'énumération se produit.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomers)]
 [!code-vb[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomers)]  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment utiliser <xref:System.Data.Services.Client.DataServiceContext> pour exécuter explicitement une requête qui retourne tous les `Customers` sur le service de données Northwind.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomersexplicit)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomersexplicit)]  
  
## <a name="see-also"></a>Voir aussi

- [Procédure : Ajouter des options de requête à une requête de service de données](../../../../docs/framework/data/wcf/how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)

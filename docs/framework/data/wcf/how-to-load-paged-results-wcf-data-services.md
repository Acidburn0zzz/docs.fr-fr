---
title: 'Procédure : Charge résultats paginés (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: bb786ea4-f3ef-4ad3-9a41-3a0b7feb6a1f
ms.openlocfilehash: 6042f4a89c390ade8b282f09808c698a107fdf24
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212009"
---
# <a name="how-to-load-paged-results-wcf-data-services"></a>Procédure : Charge résultats paginés (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] permet au service de données limiter le nombre d’entités qui sont retournées dans un flux de réponse unique. Lorsque cela arrive, la dernière entrée dans le flux contient un lien vers la page suivante de données. L'URI vers la page suivante de données s'obtient en appelant la méthode <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> sur le <xref:System.Data.Services.Client.QueryOperationResponse%601> retourné lorsque <xref:System.Data.Services.Client.DataServiceQuery%601> est exécuté. L'URI représenté par cet objet est ensuite utilisé pour charger la page suivante de résultats. Pour plus d’informations, consultez [le chargement du contenu différé](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 L'exemple dans cette rubrique utilise l'exemple de service de données Northwind et des classes de service de données clientes générées automatiquement. Ce service et les classes de données client sont créés lorsque vous complétez le [démarrage rapide WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise une boucle `do…while` pour charger des entités `Customers` à partir de résultats paginés du service de données.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspaged)]
 [!code-vb[Astoria Northwind Client#GetCustomersPaged](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspaged)]  
  
## <a name="example"></a>Exemple  
 Cet exemple retourne des entités `Orders` connexes avec chaque entité `Customers` et utilise une boucle `do…while` pour charger des pages d'entités `Customers` et une boucle `while` imbriquée pour charger des pages d'entités `Orders` connexes à partir du service de données.  
  
 [!code-csharp[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getcustomerspagednested)]
 [!code-vb[Astoria Northwind Client#GetCustomersPagedNested](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getcustomerspagednested)]  
  
## <a name="see-also"></a>Voir aussi

- [Chargement de contenu différé](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [Procédure : Charger des entités associées](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)

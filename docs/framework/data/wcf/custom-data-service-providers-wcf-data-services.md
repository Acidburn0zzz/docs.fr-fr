---
title: Fournisseurs de services de données personnalisés (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: 8a0045f0c1b2a0f405e00c6eb729c88a5e95b426
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354957"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Fournisseurs de services de données personnalisés (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] inclut un jeu de fournisseurs qui vous permet de définir un modèle de données basé sur des types de données à liaison tardive.  
  
|Fournisseur|Description|  
|--------------|-----------------|  
|Fournisseur de métadonnées|Il s'agit du fournisseur de services de données personnalisé principal qui vous permet de définir pendant l'exécution un modèle de données personnalisé en implémentant l'interface <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|Fournisseur de requête|Ce fournisseur vous permet d'exécuter des requêtes sur un modèle de données personnalisé défini à l'aide de l'interface <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>. Le fournisseur de requête est créé en implémentant l'interface <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.|  
|Fournisseur de mise à jour|Ce fournisseur vous permet d'effectuer des mises à jour sur les types exposés dans un fournisseur de services de données personnalisé et de gérer l'accès concurrentiel. Un fournisseur de mise à jour est créé en implémentant l'interface <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>|  
|Fournisseur de pagination|Ce fournisseur est utilisé avec le fournisseur de services de données personnalisé pour permettre la prise en charge de la pagination pilotée par le serveur. Un fournisseur de pagination pour un service de données personnalisé est créé en implémentant l'interface <xref:System.Data.Services.Providers.IDataServicePagingProvider>.|  
|Fournisseur de diffusion en continu|Ce fournisseur vous permet d'exposer des types de données d'objet blob (binary large object) sous forme de flux en continu. Un fournisseur de diffusion en continu est créé en implémentant l'interface <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Le fournisseur de diffusion en continu peut également être utilisé avec Entity Framework et des fournisseurs de source de données de réflexion. Pour plus d’informations, consultez [fournisseur de diffusion en continu](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
 Pour plus d’informations, consultez l’article [fournisseurs de services de données personnalisé](http://go.microsoft.com/fwlink/?LinkID=186850) et [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] boîte à outils du fournisseur dans le [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>Voir aussi  
 [Fournisseurs de services de données](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Fournisseur Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [Fournisseur de réflexion](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)

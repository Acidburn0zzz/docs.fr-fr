---
title: Gestion du cache pour les applications réseau
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1e0b3ed66977dd6587789e3d88f532b699653c6f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195574"
---
# <a name="cache-management-for-network-applications"></a>Gestion du cache pour les applications réseau
Cette rubrique et ses sous-rubriques associées décrivent la mise en cache pour les ressources obtenues à l’aide des classes <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> et <xref:System.Net.FtpWebRequest>.  
  
 Un cache procure un stockage temporaire des ressources qui ont été demandées par une application. Si une application demande la même ressource plusieurs fois, celle-ci peut être retournée à partir du cache, ce qui évite de devoir la redemander au serveur. La mise en cache peut améliorer les performances de l’application en réduisant la durée nécessaire pour obtenir une ressource demandée. Elle peut également réduire le trafic réseau en réduisant le nombre d’allers-retours au serveur. Bien que la mise en cache améliore les performances, elle augmente le risque que la ressource retournée à l’application soit périmée, c’est-à-dire qu’elle ne soit pas identique à la ressource qui aurait été envoyée par le serveur si la mise en cache n’était pas utilisée.  
  
 La mise en cache peut permettre à des utilisateurs ou des processus non autorisés de lire des données sensibles. Une réponse authentifiée mise en cache peut-être récupérée à partir du cache sans autorisation supplémentaire. Si la mise en cache est activée, définissez <xref:System.Net.WebRequest.CachePolicy%2A> sur <xref:System.Net.Cache.RequestCacheLevel.BypassCache> ou <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> pour désactiver la mise en cache pour cette demande.  
  
 Pour des raisons de sécurité, la mise en cache n’est **pas** recommandée pour les scénarios de couche intermédiaire.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Stratégie de cache](../../../docs/framework/network-programming/cache-policy.md)  
 Explique ce qu’est une stratégie de cache et comment en définir une.  
  
 [Stratégies de cache basées sur l’emplacement](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 Définit chaque type de stratégie de cache basée sur l’emplacement disponible pour les ressources Hypertext Transfer Protocol (http et https).  
  
 [Stratégies de cache basées sur la durée](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 Décrit les critères qui peuvent être utilisés pour personnaliser une stratégie de cache basée sur la durée.  
  
 [Configuration de la mise en cache dans les applications réseau](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 Décrit comment créer par programmation des stratégies de cache et des demandes qui utilisent la mise en cache.  
  
## <a name="reference"></a>Référence  
 <xref:System.Net.Cache>  
 Définit les types et les énumérations utilisés pour définir des stratégies de cache applicables aux ressources obtenues à l’aide des classes <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> et <xref:System.Net.FtpWebRequest>.

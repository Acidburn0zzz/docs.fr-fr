---
title: "IHostSemaphore::ReleaseSemaphore, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6828726fe81cc99adc719659a6eb1b15afda84c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsemaphorereleasesemaphore-method"></a>IHostSemaphore::ReleaseSemaphore, méthode
Incrémente le nombre d’actuel [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance de la valeur spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lReleaseCount`  
 [in] La quantité d’augmentation du nombre d’en cours `IHostSemaphore` instance. Ce montant doit être supérieur à zéro.  
  
 `lpPreviousCount`  
 [out] Pointeur vers le compteur antérieur ou null si l’appelant ne nécessite pas le compteur antérieur.  
  
## <a name="return-value"></a>Valeur de retour  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`ReleaseSemaphore`retourné avec succès.|  
|HOST_E_CLRNOTAVAILABLE|Le common language runtime (CLR) n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.|  
|HOST_E_TIMEOUT|L’appel a expiré.|  
|HOST_E_NOT_OWNER|L’appelant ne possède pas le verrou.|  
|HOST_E_ABANDONED|Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.|  
|E_FAIL|Une défaillance grave et inconnue s’est produite. Lorsqu’une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus. Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Notes  
 Le CLR appelle généralement `ReleaseSemaphore` pour notifier l’hôte qu’il a terminé d’utiliser une ressource, en passant une valeur de 1 pour le `lReleaseCount` paramètre.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MSCorEE.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [ICLRSyncManager, interface](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostAutoEvent, interface](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [IHostManualEvent, interface](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [IHostSemaphore, interface](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [IHostSyncManager, interface](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)

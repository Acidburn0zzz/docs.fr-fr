---
title: IActionOnCLREvent, interface
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24191e93d0d8b27d01a914cae76c9ff4e0a7182d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="iactiononclrevent-interface"></a>IActionOnCLREvent, interface
Fournit la [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) (méthode), qui exécute des rappels sur les événements qui ont été inscrits à l’aide d’un appel à la [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) (méthode).  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[OnEvent, méthode](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|Exécute un rappel pour un événement enregistré.|  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MSCorEE.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [EClrEvent, énumération](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [ICLRControl, interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLROnEventManager, interface](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [Interfaces d’hébergement](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

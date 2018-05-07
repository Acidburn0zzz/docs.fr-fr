---
title: ICorDebugRegisterSet2, interface
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f4947a9b6c0e3fd87ee474111f143d273c1d7b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugregisterset2-interface"></a>ICorDebugRegisterSet2, interface
Étend les fonctionnalités de la [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface pour les plateformes matérielles qui possèdent plus de 64 registres.  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetRegisters, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|Obtient la valeur de chaque registre (sur l’ordinateur qui exécute actuellement le code) qui est spécifié par le masque de bits.|  
|[GetRegistersAvailable, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|Obtient un tableau d’octets qui fournit une bitmap des registres disponibles.|  
|[SetRegisters, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|Non implémenté dans le .NET Framework version 2.0.|  
  
## <a name="remarks"></a>Notes  
  
> [!NOTE]
>  Cette interface ne prend pas en charge l'appel à distance, que ce soit entre ordinateurs ou entre processus.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ICorDebugRegisterSet, interface](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)

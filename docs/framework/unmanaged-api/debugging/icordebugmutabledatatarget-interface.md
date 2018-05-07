---
title: ICorDebugMutableDataTarget, interface
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 677db647320ff4014b791502b7ac1b261378c8dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmutabledatatarget-interface"></a>ICorDebugMutableDataTarget, interface
Étend la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface pour prendre en charge des cibles de données mutables.  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[ContinueStatusChanged, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|Modifie l'état de continuation de l'événement de débogage en suspens sur le thread spécifié.|  
|[SetThreadContext, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|Définit le contexte (valeurs de registre) d'un thread.|  
|[WriteVirtual, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|Écrit la mémoire dans l'espace d'adressage du processus cible.|  
  
## <a name="remarks"></a>Notes  
 Cette extension pour le [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface peut être implémentée par les outils de débogage qui souhaitent modifier le processus cible (par exemple, pour effectuer un débogage INVASIF en direct).  
  
 Toutes ces méthodes sont facultatives dans le sens où aucune fonctionnalité de débogage principale basée sur l'inspection n'est perdue en cas de non-implémentation de cette interface ou en cas d'échec des appels à ces méthodes.  Tout `HRESULT` d'échec issu de ces méthodes se propage sous la forme d'un `HRESULT` de l'appel de méthode ICorDebug.  
  
 Notez qu'un seul appel de méthode ICorDebug peut entraîner plusieurs mutations et qu'il n'existe aucun mécanisme garantissant l'application en mode transactionnel (tout ou rien) des mutations connexes.  Cela signifie que si une mutation échoue après la réussite d'autres mutations (pour le même appel ICorDebug), le processus cible peut se retrouver dans un état incohérent pouvant nuire à la fiabilité du débogage.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Débogage](../../../../docs/framework/unmanaged-api/debugging/index.md)

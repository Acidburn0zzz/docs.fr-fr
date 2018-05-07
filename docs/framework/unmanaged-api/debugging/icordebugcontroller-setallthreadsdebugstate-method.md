---
title: ICorDebugController::SetAllThreadsDebugState, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ee396c512dca2bea0a7a9737d5515defce4b2b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>ICorDebugController::SetAllThreadsDebugState, méthode
Définit l’état de débogage de tous les threads managés dans le processus.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `state`  
 [in] Valeur de l’énumération « CorDebugThreadState » qui spécifie l’état du thread pour le débogage.  
  
 `pExceptThisThread`  
 [in] Pointeur vers un objet « ICorDebugThread » qui représente un thread à exempter du paramètre d’état de débogage. Si cette valeur est null, aucun thread n’est exempté.  
  
## <a name="remarks"></a>Notes  
 Le `SetAllThreadsDebugState` threads qui ne sont pas visibles via la méthode peut affecter [EnumerateThreads, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), les threads qui ont été interrompus avec le `SetAllThreadsDebugState` méthode devra être repris avec le `SetAllThreadsDebugState` (méthode).  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 

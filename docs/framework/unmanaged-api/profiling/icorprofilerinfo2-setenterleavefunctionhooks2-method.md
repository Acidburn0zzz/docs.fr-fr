---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52988378ff4df0bb03e15c9a4b25efbcd6c318f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a>ICorProfilerInfo2::SetEnterLeaveFunctionHooks2, méthode
Spécifie les fonctions implémentées par le profileur à être appelée sur les versions mises à jour des « entrer », « quitter » et « tailcall » de fonctions managées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pFuncEnter`  
 [in] Un pointeur vers l’implémentation à utiliser comme le [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) rappel.  
  
 `pFuncLeave`  
 [in] Un pointeur vers l’implémentation à utiliser comme le [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) rappel.  
  
 `pFuncTailcall`  
 [in] Un pointeur vers l’implémentation à utiliser comme le [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) rappel.  
  
## <a name="remarks"></a>Notes  
 Le `SetEnterLeaveFunctionHooks2` méthode est similaire à la [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) (méthode). Utilisez la première pour spécifier les fonctions à utiliser comme les versions plus récentes de l’entrée/leave/tailcall et ce dernier pour spécifier les fonctions à utiliser comme les versions précédentes des rappels entrée/leave/tailcall.  
  
 Qu’un seul jeu de rappels peut être actif à la fois. Par conséquent, si un profileur appelle `ICorProfilerInfo::SetEnterLeaveFunctionHooks` et `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` est utilisé.  
  
 Le `SetEnterLeaveFunctionHooks2` méthode peut être appelée uniquement à partir du profileur [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) rappel.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl, CorProf.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [ICorProfilerInfo, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

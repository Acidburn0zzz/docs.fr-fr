---
title: FunctionLeave2 (fonction)
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d6486a90d952208af89428423867a3daa4e8618
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453357"
---
# <a name="functionleave2-function"></a>FunctionLeave2 (fonction)
Notifie le profileur qu’une fonction doit retourner à l’appelant et fournit des informations sur la valeur de retour pile fonction et de frame.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `funcId`  
 [in] Identificateur de la fonction qui retourne.  
  
 `clientData`  
 [in] Identificateur de fonction remappé, avec le profileur spécifié précédemment via le [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) (fonction).  
  
 `func`  
 [in] A `COR_PRF_FRAME_INFO` valeur qui pointe vers des informations sur le frame de pile.  
  
 Le profileur doit le traiter en tant que handle opaque qui peut être passé au moteur d’exécution dans le [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) (méthode).  
  
 `retvalRange`  
 [in] Un pointeur vers un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure qui spécifie l’emplacement de mémoire de valeur de retour de la fonction.  
  
 Pour accéder à la valeur de retour d’informations, le `COR_PRF_ENABLE_FUNCTION_RETVAL` indicateur doit être défini. Le profileur peut utiliser le [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) pour définir les indicateurs d’événement.  
  
## <a name="remarks"></a>Notes  
 Les valeurs de la `func` et `retvalRange` paramètres ne sont pas valides après le `FunctionLeave2` fonction retourne, car les valeurs peuvent changer ou être détruites.  
  
 Le `FunctionLeave2` fonction est un rappel ; vous devez l’implémenter. L’implémentation doit utiliser le `__declspec`(`naked`) attribut de classe de stockage.  
  
 Le moteur d’exécution n’enregistre pas les registres avant d’appeler cette fonction.  
  
-   À l’entrée, vous devez enregistrer tous les registres que vous utilisez, y compris ceux de l’unité à virgule flottante (FPU).  
  
-   À la sortie, vous devez restaurer la pile par extraire tous les paramètres qui ont été envoyées par son appelant.  
  
 L’implémentation de `FunctionLeave2` ne doivent pas bloquer, car il sera retarder le garbage collection. L’implémentation ne doit pas tenter une opération garbage collection, car la pile est peut-être pas dans un état de nom convivial de la collection garbage. Si un garbage collection est tenté, le runtime bloque jusqu'à ce que `FunctionLeave2` retourne.  
  
 En outre, le `FunctionLeave2` (fonction) ne doit pas appeler dans du code managé ou de quelque manière qu’une allocation de mémoire managée.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [FunctionEnter2, fonction](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [FunctionTailcall2, fonction](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [SetEnterLeaveFunctionHooks2, méthode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Fonctions statiques globales de profilage](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)

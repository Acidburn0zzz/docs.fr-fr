---
title: ICorDebugILFrame2::RemapFunction, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f03d8c993be1ac83ca84275bcb94f1bb3cdf884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction, méthode
Remappe une fonction modifiée en spécifiant l’offset du nouveau Microsoft intermediate language (MSIL)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `newILOffset`  
 [in] Nouvel offset MSIL du frame de pile à laquelle le pointeur d’instruction doit être placé. Cette valeur doit être un point de séquence.  
  
 Il est responsable de l’appelant pour garantir la validité de cette valeur. Par exemple, l’offset MSIL n’est pas valide s’il est en dehors des limites de la fonction.  
  
## <a name="remarks"></a>Notes  
 Lors de la fonction d’un frame a été modifiée, le débogueur peut appeler le `RemapFunction` méthode pour passer à la dernière version de la fonction du frame afin de pouvoir être exécuté. L’exécution du code commence à l’offset MSIL donné.  
  
> [!NOTE]
>  Appel de `RemapFunction`, comme l’appel [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), invalidera immédiatement toutes les interfaces de débogage qui sont liées à la génération d’une trace de pile du thread. Ces interfaces incluent [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame et ICorDebugNativeFrame.  
  
 Le `RemapFunction` méthode peut être appelée uniquement dans le contexte de l’image actuelle et uniquement dans un des cas suivants :  
  
-   Après réception d’un [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) rappel qui n’a pas encore repris.  
  
-   Pendant l’exécution du code est arrêtée en raison d’une [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) événement pour ce frame.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

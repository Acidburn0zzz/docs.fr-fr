---
title: ICorDebugStackWalk::GetContext, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba1e6c113fb4caa0db8963e238d3eceba0cc8ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224856"
---
# <a name="icordebugstackwalkgetcontext-method"></a>ICorDebugStackWalk::GetContext, méthode
Retourne le contexte pour le frame actuel dans le [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a>Paramètres  
 `contextFlags`  
 [in] Indicateurs qui spécifient le contenu demandé de la mémoire tampon de contexte (défini dans WinNT.h).  
  
 `contextBufSize`  
 [in] La taille allouée de la mémoire tampon de contexte.  
  
 `contextSize`  
 [out] La taille réelle du contexte. Cette valeur doit être inférieure ou égale à la taille de la mémoire tampon de contexte.  
  
 `contextBuf`  
 [out] Mémoire tampon de contexte.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne les HRESULT spécifiques suivants ainsi que les erreurs HRESULT indiquant l'échec de la méthode.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Le contexte pour le frame actuel a été retourné avec succès.|  
|E_FAIL|Le contexte n’a pas pu être retourné.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|Mémoire tampon de contexte est trop petite.|  
|CORDBG_E_PAST_END_OF_STACK|Le pointeur de frame est déjà à la fin de la pile ; Par conséquent, aucun frame supplémentaires ne sont accessibles.|  
  
## <a name="exceptions"></a>Exceptions  
  
## <a name="remarks"></a>Notes  
 Étant donné que le déroulement restaure uniquement un sous-ensemble des registres, tels que les registres non volatils, le contexte peut différer l’état du Registre au moment de l’appel.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [Interfaces de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Débogage](../../../../docs/framework/unmanaged-api/debugging/index.md)

---
title: ICorDebugStackWalk::SetContext, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7306ee61d750ae256c93c049819a23d3d61f7297
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116465"
---
# <a name="icordebugstackwalksetcontext-method"></a>ICorDebugStackWalk::SetContext, méthode
Définit le [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) contexte actuel de l’objet à un contexte valid pour le thread.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>Paramètres  
 `flag`  
 [in] Un [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) indicateur qui indique si le contexte provient du frame actif sur la pile, ou un contexte obtenu par le déroulement de la pile.  
  
 `contextSize`  
 [in] La taille allouée de la `CONTEXT` mémoire tampon.  
  
 `context`  
 [in] Le `CONTEXT` mémoire tampon.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne les HRESULT spécifiques suivants ainsi que les erreurs HRESULT indiquant l'échec de la méthode.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Le `ICorDebugStackWalk` contexte de l’objet a été défini correctement.|  
|E_FAIL|Le `ICorDebugStackWalk` contexte de l’objet n’a pas été défini.|  
|E_INVALIDARG|Le contexte est null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Mémoire tampon de contexte est trop petite.|  
  
## <a name="exceptions"></a>Exceptions  
  
## <a name="remarks"></a>Notes  
 Cette méthode ne modifie pas le contexte actuel du thread.  
  
 Définition du contexte actuel à un contexte non valide peut provoquer des résultats imprévisibles à partir de l’Explorateur de pile.  
  
 Vous pouvez récupérer une copie au niveau du bit exacte de ce contexte en appelant immédiatement la [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) (méthode).  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [Interfaces de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Débogage](../../../../docs/framework/unmanaged-api/debugging/index.md)

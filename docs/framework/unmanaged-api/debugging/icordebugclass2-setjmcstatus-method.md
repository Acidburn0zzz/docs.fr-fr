---
title: ICorDebugClass2::SetJMCStatus, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d234e01e3d47a64b9a001591ee2b61074eea8afb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403391"
---
# <a name="icordebugclass2setjmcstatus-method"></a>ICorDebugClass2::SetJMCStatus, méthode
Pour chaque méthode de la classe, définit une valeur qui indique si la méthode est un code défini par l’utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `bIsJustMyCode`  
 [in] La valeur `true` pour indiquer que la méthode est définie par l’utilisateur de code ; sinon, valeur `false`.  
  
## <a name="remarks"></a>Notes  
 Un uniquement mon code (JMC) ignorera le code non défini par l’utilisateur. Code défini par l’utilisateur doit être un sous-ensemble de code pouvant être débogué.  
  
 `SetJMCStatus` Retourne une valeur HRESULT de S_FALSE en cas d’échec définir la valeur de n’importe quelle méthode, même si la valeur pour toutes les autres méthodes.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

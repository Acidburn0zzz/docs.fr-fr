---
title: CLR_DEBUGGING_PROCESS_FLAGS, énumération
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dff6b245c80050a5e85561b8bba6aa9ba8199ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407064"
---
# <a name="clrdebuggingprocessflags-enumeration"></a>CLR_DEBUGGING_PROCESS_FLAGS, énumération
Fournit des valeurs qui sont utilisées par le [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) (méthode).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Membres  
  
|Membre|Description|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Cette exécution a un événement du débogueur managé non-catch-up à envoyer. Consultez la section Notes de la distinction entre les événements de rattrapage et non-catch-up.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|L’événement managé qui est en attente est un <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> demande.|  
  
## <a name="remarks"></a>Notes  
 Événements de rattrapage incluent des processus, domaine d’application, assembly, module et les notifications de la création du thread que le débogueur passe à l’état actuel une fois qu’il a joint à un processus. Les événements de non-catch-up, qui sont indiquées par le `CLR_DEBUGGING_MANAGED_EVENT_PENDING` indicateur, inclure tous les autres événements de débogueur, telles que les exceptions et de débogage des notifications de l’assistant (MDA).  
  
 Le `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` indicateur permet à l’exécution différencier une exception de fin et une demande d’attachement d’un débogueur managé qui peut être annulé.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Metahost.idl, Metahost.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Débogage](../../../../docs/framework/unmanaged-api/debugging/index.md)

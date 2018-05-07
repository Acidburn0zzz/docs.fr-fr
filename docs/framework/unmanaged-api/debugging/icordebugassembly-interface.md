---
title: ICorDebugAssembly Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88134fb7854091bb60e8084a6d776bdec922c7e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugassembly-interface1"></a>ICorDebugAssembly Interface1
Représente un assembly.  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[EnumerateModules, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|Obtient un énumérateur pour les modules contenus dans l’assembly.|  
|[GetAppDomain, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|Obtient un pointeur d’interface vers le domaine d’application qui contient cette `ICorDebugAssembly` instance.|  
|[GetCodeBase, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|Non implémenté dans la version actuelle du .NET Framework.|  
|[GetName, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|Obtient le nom de l'assembly.|  
|[GetProcess, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|Obtient l’instance ICorDebugProcess dans lequel l’assembly est en cours d’exécution.|  
  
## <a name="remarks"></a>Notes  
  
> [!NOTE]
>  Cette interface ne prend pas en charge l'appel à distance, que ce soit entre ordinateurs ou entre processus.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

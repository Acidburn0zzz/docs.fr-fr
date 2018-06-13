---
title: ICorProfilerCallback::Shutdown, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83e32b2b69d53772f8a4ebaabe1c025b95d1da47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453725"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown, méthode
Notifie le profileur que l’application est en cours d’arrêt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Notes  
 Le profileur de code ne peut pas appeler en toute sécurité les méthodes de la [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface après le `Shutdown` méthode est appelée. Tous les appels à `ICorProfilerInfo` méthodes entraîner un comportement indéfini après le `Shutdown` le retour de méthode. Certains événements immuables peuvent encore se produire après l’arrêt ; le profileur doit veiller à retourner immédiatement lorsque cela se produit.  
  
 Le `Shutdown` méthode sera appelée uniquement si l’application managée est en cours de profilage est démarrée en tant que le code managé (autrement dit, le frame initial sur la pile de processus est géré). Si l’application en tant que code non managé, mais plus tard est passé dans le code managé, créant ainsi une instance du common language runtime (CLR), puis `Shutdown` ne sera pas appelée. Dans ce cas, le profileur doit inclure dans sa bibliothèque un `DllMain` routine qui utilise le DLL_PROCESS_DETACH value pour libérer les ressources et d’exécuter le nettoyage de ses données, telles que la suppression des traces sur le disque et ainsi de suite.  
  
 En général, le profileur doit faire face à des arrêts inattendus. Par exemple, un processus peut être arrêté par de Win32 `TerminateProcess` (méthode) (déclaré dans Winbase.h). Dans d’autres cas, le CLR arrêtera certains threads managés (threads d’arrière-plan) sans la remise des messages de la destruction de façon ordonnée pour eux.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl, CorProf.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [ICorProfilerCallback, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Initialize, méthode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)

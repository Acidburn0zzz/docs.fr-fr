---
title: ICorProfilerCallback::COMClassicVTableDestroyed, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63dc9ee81c98a23f01948a142018369eca7210b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116753"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a>ICorProfilerCallback::COMClassicVTableDestroyed, méthode
Notifie le profileur qu’une vtable d’interopérabilité COM est en cours de destruction.  
  
> [!NOTE]
>  Ce rappel est susceptible de ne jamais se produire, car la destruction de vtable survient très près de l’arrêt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a>Paramètres  
 `wrappedClasId`  
 [in] L’ID de la classe pour laquelle cette vtable a été créée.  
  
 `implementedIID`  
 [in] ID de l’interface implémentée par la classe. Cette valeur peut être NULL si l’interface est uniquement interne.  
  
 `pVTable`  
 [in] Pointeur vers le début de la vtable.  
  
## <a name="remarks"></a>Notes  
 Le profileur ne doit pas bloquer dans son implémentation de cette méthode, car la pile ne peut pas être dans un état qui autorise le garbage collection, et par conséquent, le garbage collection préemptif ne peut pas être activé. Si le profileur bloque ici et le garbage collection est tenté, le runtime bloque jusqu'à ce que ce rappel renvoie.  
  
 L’implémentation du profileur de cette méthode ne doit pas appeler dans du code managé ou de quelque manière qu’une allocation de mémoire managée.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl, CorProf.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [ICorProfilerCallback, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [COMClassicVTableCreated, méthode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)

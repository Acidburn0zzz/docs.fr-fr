---
title: "ICorPublish::EnumProcesses, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7e0af492cbec401d7470502de807033f21e39f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses, méthode
Obtient un énumérateur pour les processus managés en cours d’exécution sur cet ordinateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Type`  
 Une valeur de la [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) énumération qui spécifie le type de processus à récupérer. Dans la version actuelle, seul COR_PUB_MANAGEDONLY est valide.  
  
 `ppIEnum`  
 Un pointeur vers l’adresse d’un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance qui est l’énumérateur des processus.  
  
## <a name="remarks"></a>Notes  
 Collection de l’énumérateur de processus est basée sur un instantané des processus qui s’exécutent lorsque le `EnumProcesses` méthode est appelée. L’énumérateur n’inclut pas tous les processus qui se terminer avant ou démarrer après `EnumProcesses` est appelée.  
  
 Le `EnumProcesses` méthode peut être appelée plusieurs fois sur ce [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance pour créer une nouvelle collection à jour de processus. Les collections existantes ne seront pas affectées par les appels suivants de la `EnumProcesses` (méthode).  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorPub.idl, CorPub.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [ICorPublish, interface](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)

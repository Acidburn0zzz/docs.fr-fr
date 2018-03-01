---
title: COR_PRF_GC_GENERATION_RANGE, structure
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
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59969f45d4cca0ff208bd9e77c93994cad61ab13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgenerationrange-structure"></a>COR_PRF_GC_GENERATION_RANGE, structure
Décrit une plage (un bloc) de mémoire qui va faire l’objet d’un garbage collection.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a>Membres  
  
|Membre|Description|  
|------------|-----------------|  
|`generation`|Une valeur de la [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) appartient d’énumération qui spécifie la génération à laquelle le bloc de mémoire.|  
|`rangeStart`|L’ID d’un objet qui spécifie l’emplacement de départ du bloc de mémoire.|  
|`rangeLength`|Pointeur vers un entier qui spécifie la taille de la partie utilisée du bloc de mémoire (autrement dit, la quantité de mémoire utilisée dans le bloc).|  
|`rangeLengthReserved`|Pointeur vers un entier qui spécifie la taille du bloc de mémoire (autrement dit, la quantité de mémoire réservée pour le bloc).|  
  
## <a name="remarks"></a>Notes  
 Le `rangeLength` valeur est garantie exacte uniquement si [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) ou [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), tous deux utilisent le `COR_PRF_GC_GENERATION_RANGE` la structure, est appelée à partir de la [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) ou [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) (méthode).  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Structures de profilage](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

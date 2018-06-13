---
title: COR_PRF_GC_GENERATION_RANGE, structure
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1f4c8e9a7ce5eddde18c1266cb724d5c3b0d5f41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450319"
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
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Structures de profilage](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

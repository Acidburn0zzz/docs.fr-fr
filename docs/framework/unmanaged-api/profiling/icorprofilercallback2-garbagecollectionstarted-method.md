---
title: "ICorProfilerCallback2::GarbageCollectionStarted, méthode"
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
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b721b990312f9acda5c9e0208f998793735d2cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="d91aa-102">ICorProfilerCallback2::GarbageCollectionStarted, méthode</span><span class="sxs-lookup"><span data-stu-id="d91aa-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="d91aa-103">Notifie le profileur de code que le garbage collection a démarré.</span><span class="sxs-lookup"><span data-stu-id="d91aa-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d91aa-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d91aa-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d91aa-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d91aa-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="d91aa-106">[in] Le nombre total d’entrées dans le `generationCollected` tableau.</span><span class="sxs-lookup"><span data-stu-id="d91aa-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="d91aa-107">[in] Un tableau de valeurs booléennes, qui sont `true` si la génération qui correspond à l’index de tableau sont collectées par ce garbage collection ; sinon, `false`.</span><span class="sxs-lookup"><span data-stu-id="d91aa-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d91aa-108">Le tableau est indexé par une valeur de la [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) énumération qui indique la génération.</span><span class="sxs-lookup"><span data-stu-id="d91aa-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="d91aa-109">[in] Une valeur de la [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) énumération qui indique la raison pour laquelle le garbage collection a été INDUITE.</span><span class="sxs-lookup"><span data-stu-id="d91aa-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d91aa-110">Notes</span><span class="sxs-lookup"><span data-stu-id="d91aa-110">Remarks</span></span>  
 <span data-ttu-id="d91aa-111">Tous les rappels relatifs à ce garbage collection seront produit entre le `GarbageCollectionStarted` rappel et correspondants [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) rappel.</span><span class="sxs-lookup"><span data-stu-id="d91aa-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="d91aa-112">Ces rappels ne doivent pas avoir lieu sur le même thread.</span><span class="sxs-lookup"><span data-stu-id="d91aa-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="d91aa-113">Il est possible pour le profileur d’inspecter des objets dans leurs emplacements d’origine pendant la `GarbageCollectionStarted` rappel.</span><span class="sxs-lookup"><span data-stu-id="d91aa-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="d91aa-114">Le garbage collector commencera à déplacer les objets après le retour de `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="d91aa-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="d91aa-115">Une fois que le profileur a retourné à partir de ce rappel, le profileur doit considérer tous les ID d’objet est non valide jusqu'à ce qu’il reçoive une `ICorProfilerCallback2::GarbageCollectionFinished` rappel.</span><span class="sxs-lookup"><span data-stu-id="d91aa-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d91aa-116">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="d91aa-116">Requirements</span></span>  
 <span data-ttu-id="d91aa-117">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d91aa-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d91aa-118">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d91aa-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d91aa-119">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d91aa-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d91aa-120">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d91aa-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91aa-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d91aa-121">See Also</span></span>  
 [<span data-ttu-id="d91aa-122">ICorProfilerCallback, interface</span><span class="sxs-lookup"><span data-stu-id="d91aa-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d91aa-123">ICorProfilerCallback2, interface</span><span class="sxs-lookup"><span data-stu-id="d91aa-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)

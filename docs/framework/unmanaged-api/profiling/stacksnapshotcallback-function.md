---
title: StackSnapshotCallback (fonction)
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78fdcb69e73bc7238972d1a6ffb37b5ba91c7953
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459083"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="cbf40-102">StackSnapshotCallback (fonction)</span><span class="sxs-lookup"><span data-stu-id="cbf40-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="cbf40-103">Fournit au profileur des informations sur chaque frame managé et chaque exécution de frames non managés sur la pile pendant un parcours de pile, qui est initié par le [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="cbf40-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbf40-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cbf40-104">Syntax</span></span>  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbf40-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="cbf40-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="cbf40-106">[in] Si cette valeur est zéro, ce rappel est pour une exécution de frames non managés ; Sinon, il s’agit de l’identificateur d’une fonction managée et ce rappel correspond à un frame managé.</span><span class="sxs-lookup"><span data-stu-id="cbf40-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="cbf40-107">[in] La valeur du pointeur d’instruction de code natif dans le frame.</span><span class="sxs-lookup"><span data-stu-id="cbf40-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="cbf40-108">[in] A `COR_PRF_FRAME_INFO` valeur qui fait référence à des informations sur le frame de pile.</span><span class="sxs-lookup"><span data-stu-id="cbf40-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="cbf40-109">Cette valeur est valide pour une utilisation uniquement pendant ce rappel.</span><span class="sxs-lookup"><span data-stu-id="cbf40-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="cbf40-110">[in] La taille de la `CONTEXT` structure, ce qui est référencé par le `context` paramètre.</span><span class="sxs-lookup"><span data-stu-id="cbf40-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="cbf40-111">[in] Un pointeur vers un Win32 `CONTEXT` structure qui représente l’état de l’UC pour ce frame.</span><span class="sxs-lookup"><span data-stu-id="cbf40-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="cbf40-112">Le `context` paramètre est valide uniquement si l’indicateur COR_PRF_SNAPSHOT_CONTEXT a été passé dans `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="cbf40-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="cbf40-113">[in] Un pointeur vers les données client, qui sont transmis directement par le biais de `ICorProfilerInfo2::DoStackSnapshot`.</span><span class="sxs-lookup"><span data-stu-id="cbf40-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbf40-114">Notes</span><span class="sxs-lookup"><span data-stu-id="cbf40-114">Remarks</span></span>  
 <span data-ttu-id="cbf40-115">Le `StackSnapshotCallback` fonction est implémentée par le writer de profileur.</span><span class="sxs-lookup"><span data-stu-id="cbf40-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="cbf40-116">Vous devez limiter la complexité du travail effectué dans `StackSnapshotCallback`.</span><span class="sxs-lookup"><span data-stu-id="cbf40-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="cbf40-117">Par exemple, lorsque vous utilisez `ICorProfilerInfo2::DoStackSnapshot` de manière asynchrone, le thread cible peut contenir des verrous.</span><span class="sxs-lookup"><span data-stu-id="cbf40-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="cbf40-118">Si le code situé dans `StackSnapshotCallback` requiert les mêmes verrous, un interblocage peut entraîner.</span><span class="sxs-lookup"><span data-stu-id="cbf40-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="cbf40-119">Le `ICorProfilerInfo2::DoStackSnapshot` les appels de méthode du `StackSnapshotCallback` fonction une fois par frame managé ou une fois par exécution de frames non managés.</span><span class="sxs-lookup"><span data-stu-id="cbf40-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="cbf40-120">Si `StackSnapshotCallback` est appelée pour une exécution de frames non managés, le profileur peut utiliser le contexte de Registre (référencé par le `context` paramètre) pour effectuer son propre parcours de pile non managé.</span><span class="sxs-lookup"><span data-stu-id="cbf40-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="cbf40-121">Dans ce cas, Win32 `CONTEXT` structure représente l’état de l’UC pour le frame plus récemment envoyée lors de l’exécution de frames non managés.</span><span class="sxs-lookup"><span data-stu-id="cbf40-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="cbf40-122">Bien que Win32 `CONTEXT` structure inclut des valeurs pour tous les registres, vous devez compter uniquement sur les valeurs de Registre de pointeur de pile, Registre de pointeur de frame, Registre de pointeur d’instruction et la non volatile (autrement dit, préservée) registres d’entiers.</span><span class="sxs-lookup"><span data-stu-id="cbf40-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbf40-123">Spécifications</span><span class="sxs-lookup"><span data-stu-id="cbf40-123">Requirements</span></span>  
 <span data-ttu-id="cbf40-124">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbf40-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbf40-125">**En-tête :** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="cbf40-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cbf40-126">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbf40-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbf40-127">**Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbf40-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf40-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbf40-128">See Also</span></span>  
 [<span data-ttu-id="cbf40-129">DoStackSnapshot, méthode</span><span class="sxs-lookup"><span data-stu-id="cbf40-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="cbf40-130">Fonctions statiques globales de profilage</span><span class="sxs-lookup"><span data-stu-id="cbf40-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)

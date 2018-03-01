---
title: "ICorDebugThread::SetDebugState, méthode"
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
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2754caf11f89358b3e81e6324835d5b2e12f17e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="edafb-102">ICorDebugThread::SetDebugState, méthode</span><span class="sxs-lookup"><span data-stu-id="edafb-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="edafb-103">Définit les indicateurs qui décrivent l’état de débogage de ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="edafb-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edafb-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="edafb-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="edafb-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="edafb-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="edafb-106">[in] Combinaison de bits des valeurs d’énumération CorDebugThreadState qui spécifient l’état de débogage de ce thread.</span><span class="sxs-lookup"><span data-stu-id="edafb-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edafb-107">Notes</span><span class="sxs-lookup"><span data-stu-id="edafb-107">Remarks</span></span>  
 <span data-ttu-id="edafb-108">`SetDebugState`définit l’état de débogage actuel du thread.</span><span class="sxs-lookup"><span data-stu-id="edafb-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="edafb-109">(Le « état de débogage actuel » représente l’état de débogage si le processus de se poursuivre, pas l’état actuel réel.) La valeur normale est THREAD_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="edafb-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="edafb-110">Seul le débogueur peut affecter l’état de débogage d’un thread.</span><span class="sxs-lookup"><span data-stu-id="edafb-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="edafb-111">États de débogage dernière à travers continue, donc si vous souhaitez conserver un thread THREAD_SUSPENDed sur plusieurs continue, vous pouvez définir une seule fois et au préoccupez pas.</span><span class="sxs-lookup"><span data-stu-id="edafb-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="edafb-112">Suspendre les threads et la reprise du processus peuvent entraîner des blocages, bien qu’il soit généralement peu probable.</span><span class="sxs-lookup"><span data-stu-id="edafb-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="edafb-113">Ceci est une qualité intrinsèque des threads et processus et de par sa conception.</span><span class="sxs-lookup"><span data-stu-id="edafb-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="edafb-114">Un débogueur peut arrêter de façon asynchrone et reprendre les threads pour arrêter l’interblocage.</span><span class="sxs-lookup"><span data-stu-id="edafb-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="edafb-115">Si l’état utilisateur du thread inclut USER_UNSAFE_POINT, le thread peut bloquer un garbage collection (GC).</span><span class="sxs-lookup"><span data-stu-id="edafb-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="edafb-116">Cela signifie que le thread suspendu risque davantage de provoquer un interblocage.</span><span class="sxs-lookup"><span data-stu-id="edafb-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="edafb-117">Cela peut affecter pas les événements sont déjà en file d’attente de débogage.</span><span class="sxs-lookup"><span data-stu-id="edafb-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="edafb-118">Par conséquent, un débogueur doit vider la file d’attente de la totalité de l’événement (en appelant [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) avant de suspendre ou reprendre des threads.</span><span class="sxs-lookup"><span data-stu-id="edafb-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="edafb-119">Sinon, il peut obtenir des événements sur un thread qu’elle estime qu’il a déjà suspendu.</span><span class="sxs-lookup"><span data-stu-id="edafb-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edafb-120">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="edafb-120">Requirements</span></span>  
 <span data-ttu-id="edafb-121">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edafb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edafb-122">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edafb-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edafb-123">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edafb-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edafb-124">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edafb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

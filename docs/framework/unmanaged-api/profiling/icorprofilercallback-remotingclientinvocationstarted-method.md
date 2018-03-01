---
title: "ICorProfilerCallback::RemotingClientInvocationStarted, méthode"
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
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 071e2892202271cac5e0acb226e9bef0e626b134
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="aac66-102">ICorProfilerCallback::RemotingClientInvocationStarted, méthode</span><span class="sxs-lookup"><span data-stu-id="aac66-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="aac66-103">Notifie le profileur qu’un appel de la communication à distance a démarré.</span><span class="sxs-lookup"><span data-stu-id="aac66-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac66-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="aac66-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="aac66-105">Notes</span><span class="sxs-lookup"><span data-stu-id="aac66-105">Remarks</span></span>  
 <span data-ttu-id="aac66-106">Cet événement est le même pour les appels synchrones et asynchrones.</span><span class="sxs-lookup"><span data-stu-id="aac66-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="aac66-107">Chacune des paires de rappels suivantes se produit sur le même thread :</span><span class="sxs-lookup"><span data-stu-id="aac66-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="aac66-108">`RemotingClientInvocationStarted`et [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="aac66-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="aac66-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) et [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="aac66-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="aac66-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) et [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="aac66-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="aac66-111">Vous devez être conscient des problèmes suivants avec les rappels de la communication à distance :</span><span class="sxs-lookup"><span data-stu-id="aac66-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="aac66-112">Exécution d’une fonction de la communication à distance n’est pas reflétée par l’API de profileur, afin de notifications pour les fonctions qui sont appelées à partir du client et exécutées sur le serveur ne sont pas reçues correctement.</span><span class="sxs-lookup"><span data-stu-id="aac66-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="aac66-113">L’appel réel se produit via un objet proxy ; pour le profileur, il apparaît que certaines fonctions sont compilées juste- mais jamais utilisé.</span><span class="sxs-lookup"><span data-stu-id="aac66-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="aac66-114">Le profileur ne reçoit pas de notifications exactes pour les événements de la communication à distance asynchrone.</span><span class="sxs-lookup"><span data-stu-id="aac66-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aac66-115">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="aac66-115">Requirements</span></span>  
 <span data-ttu-id="aac66-116">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aac66-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aac66-117">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aac66-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aac66-118">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aac66-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aac66-119">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac66-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac66-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aac66-120">See Also</span></span>  
 [<span data-ttu-id="aac66-121">ICorProfilerCallback, interface</span><span class="sxs-lookup"><span data-stu-id="aac66-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

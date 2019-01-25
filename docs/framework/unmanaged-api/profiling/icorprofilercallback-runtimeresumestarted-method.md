---
title: ICorProfilerCallback::RuntimeResumeStarted, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc0d0e6094d5c4668126714b36915cfa4512c1b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517628"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="3a10c-102">ICorProfilerCallback::RuntimeResumeStarted, méthode</span><span class="sxs-lookup"><span data-stu-id="3a10c-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="3a10c-103">Notifie le profileur que le runtime reprend tous les threads d’exécution.</span><span class="sxs-lookup"><span data-stu-id="3a10c-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a10c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3a10c-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="3a10c-105">Spécifications</span><span class="sxs-lookup"><span data-stu-id="3a10c-105">Requirements</span></span>  
 <span data-ttu-id="3a10c-106">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a10c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a10c-107">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a10c-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a10c-108">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a10c-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a10c-109">**Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a10c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a10c-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a10c-110">See also</span></span>
- [<span data-ttu-id="3a10c-111">ICorProfilerCallback, interface</span><span class="sxs-lookup"><span data-stu-id="3a10c-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3a10c-112">RuntimeResumeFinished, méthode</span><span class="sxs-lookup"><span data-stu-id="3a10c-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)

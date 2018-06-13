---
title: ICorProfilerInfo::GetThreadInfo, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f68565977551a54244f3caf6a0250f67005a6ecf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452879"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="46c1e-102">ICorProfilerInfo::GetThreadInfo, méthode</span><span class="sxs-lookup"><span data-stu-id="46c1e-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="46c1e-103">Obtient l’identité de thread Win32 actuelle pour le thread spécifié.</span><span class="sxs-lookup"><span data-stu-id="46c1e-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46c1e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="46c1e-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46c1e-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="46c1e-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="46c1e-106">[in] L’ID du thread pour lequel obtenir l’ID Win32 actuel.</span><span class="sxs-lookup"><span data-stu-id="46c1e-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="46c1e-107">[out] ID un pointeur vers le thread de Win32 actuel du thread spécifié d'.</span><span class="sxs-lookup"><span data-stu-id="46c1e-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46c1e-108">Spécifications</span><span class="sxs-lookup"><span data-stu-id="46c1e-108">Requirements</span></span>  
 <span data-ttu-id="46c1e-109">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46c1e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c1e-110">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46c1e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46c1e-111">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46c1e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46c1e-112">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46c1e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c1e-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46c1e-113">See Also</span></span>  
 [<span data-ttu-id="46c1e-114">ICorProfilerInfo, interface</span><span class="sxs-lookup"><span data-stu-id="46c1e-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

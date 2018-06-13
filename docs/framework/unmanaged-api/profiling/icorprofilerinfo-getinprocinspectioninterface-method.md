---
title: ICorProfilerInfo::GetInprocInspectionInterface, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 761dd55d2ae48739f24a03b8ce81c571fb211a5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453155"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="c2375-102">ICorProfilerInfo::GetInprocInspectionInterface, méthode</span><span class="sxs-lookup"><span data-stu-id="c2375-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="c2375-103">Obtient un objet qui peut être interrogé pour une interface « ICorDebugProcess ».</span><span class="sxs-lookup"><span data-stu-id="c2375-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="c2375-104">Cette méthode est obsolète dans le .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="c2375-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2375-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c2375-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2375-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c2375-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="c2375-107">[out](/cpp/atl/iunknown) objet qui peut être interrogé pour une `ICorDebugProcess` interface.</span><span class="sxs-lookup"><span data-stu-id="c2375-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2375-108">Notes</span><span class="sxs-lookup"><span data-stu-id="c2375-108">Remarks</span></span>  
 <span data-ttu-id="c2375-109">L’API de débogage du common language runtime (CLR) prise en charge limitée dans le processus de débogage dans le .NET Framework version 1.0.</span><span class="sxs-lookup"><span data-stu-id="c2375-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="c2375-110">Dans le processus de débogage activé un profileur d’utiliser les parties de l’inspection de l’API de débogage.</span><span class="sxs-lookup"><span data-stu-id="c2375-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="c2375-111">Suite à des commentaires client, dans le processus de débogage ont été supprimé du .NET Framework version 2.0 et remplacé par un ensemble de fonctionnalités qui sont plus adaptées à l’API de profilage.</span><span class="sxs-lookup"><span data-stu-id="c2375-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2375-112">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c2375-112">Requirements</span></span>  
 <span data-ttu-id="c2375-113">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2375-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2375-114">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2375-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2375-115">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2375-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2375-116">**Version du .NET framework :** 1.0</span><span class="sxs-lookup"><span data-stu-id="c2375-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2375-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c2375-117">See Also</span></span>  
 [<span data-ttu-id="c2375-118">ICorProfilerInfo, interface</span><span class="sxs-lookup"><span data-stu-id="c2375-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

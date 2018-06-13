---
title: ICorProfilerInfo::BeginInprocDebugging, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82e798e1a31f771c63e71f2a85f8cbb684b237bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462388"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="1c9a8-102">ICorProfilerInfo::BeginInprocDebugging, méthode</span><span class="sxs-lookup"><span data-stu-id="1c9a8-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="1c9a8-103">Initialise intra-processus prise en charge de débogage.</span><span class="sxs-lookup"><span data-stu-id="1c9a8-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="1c9a8-104">Cette méthode est obsolète dans le .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="1c9a8-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c9a8-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1c9a8-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c9a8-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1c9a8-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="1c9a8-107">[in] Définissez cette valeur sur `true` pour initialiser la prise en charge du débogage pour le thread actuel uniquement ; lui affectez la valeur `false` pour initialiser la prise en charge du débogage pour tous les threads.</span><span class="sxs-lookup"><span data-stu-id="1c9a8-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="1c9a8-108">[out] Pointeur vers une valeur retournée qui identifie la session de débogage.</span><span class="sxs-lookup"><span data-stu-id="1c9a8-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c9a8-109">Notes</span><span class="sxs-lookup"><span data-stu-id="1c9a8-109">Remarks</span></span>  
 <span data-ttu-id="1c9a8-110">Les services de débogage CLR pris en charge limitée dans le processus de débogage dans les versions du .NET Framework 1.0 et 1.1.</span><span class="sxs-lookup"><span data-stu-id="1c9a8-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="1c9a8-111">Dans le processus de débogage activé un profileur d’utiliser les parties de l’inspection de l’API de débogage.</span><span class="sxs-lookup"><span data-stu-id="1c9a8-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="1c9a8-112">Toutefois, en raison des commentaires des clients, dans le processus de débogage ont été supprimé du .NET Framework version 2.0 et remplacé par un ensemble de fonctionnalités qui sont plus adaptées à l’API de profilage.</span><span class="sxs-lookup"><span data-stu-id="1c9a8-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c9a8-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="1c9a8-113">Requirements</span></span>  
 <span data-ttu-id="1c9a8-114">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c9a8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c9a8-115">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c9a8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c9a8-116">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c9a8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c9a8-117">**Version du .NET framework :** 1.0</span><span class="sxs-lookup"><span data-stu-id="1c9a8-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9a8-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c9a8-118">See Also</span></span>  
 [<span data-ttu-id="1c9a8-119">ICorProfilerInfo, interface</span><span class="sxs-lookup"><span data-stu-id="1c9a8-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

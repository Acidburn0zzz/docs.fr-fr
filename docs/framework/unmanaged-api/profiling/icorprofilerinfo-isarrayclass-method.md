---
title: ICorProfilerInfo::IsArrayClass, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f34fee19c796f65d315fcbd26d55e1d5322303a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453026"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="6fdef-102">ICorProfilerInfo::IsArrayClass, méthode</span><span class="sxs-lookup"><span data-stu-id="6fdef-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="6fdef-103">Détermine si la classe spécifiée est une classe de tableau.</span><span class="sxs-lookup"><span data-stu-id="6fdef-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fdef-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6fdef-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6fdef-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="6fdef-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="6fdef-106">[in] L’ID de la classe doit être examinée.</span><span class="sxs-lookup"><span data-stu-id="6fdef-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="6fdef-107">[out] Pointeur vers une valeur de l’énumération CorElementType qui indique le type des éléments du tableau.</span><span class="sxs-lookup"><span data-stu-id="6fdef-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="6fdef-108">[out] Pointeur vers l’ID de classe des éléments du tableau, lorsqu’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="6fdef-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="6fdef-109">[out] Pointeur vers un entier qui indique le rang (autrement dit, le nombre de dimensions) du tableau.</span><span class="sxs-lookup"><span data-stu-id="6fdef-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fdef-110">Notes</span><span class="sxs-lookup"><span data-stu-id="6fdef-110">Remarks</span></span>  
 <span data-ttu-id="6fdef-111">Si la classe spécifiée est une classe de tableau, le `IsArrayClass` méthode retourne un HRESULT S_OK et les valeurs des paramètres de sortie non null.</span><span class="sxs-lookup"><span data-stu-id="6fdef-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="6fdef-112">Sinon, elle retourne S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="6fdef-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fdef-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="6fdef-113">Requirements</span></span>  
 <span data-ttu-id="6fdef-114">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fdef-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fdef-115">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6fdef-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6fdef-116">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fdef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fdef-117">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fdef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fdef-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6fdef-118">See Also</span></span>  
 [<span data-ttu-id="6fdef-119">ICorProfilerInfo, interface</span><span class="sxs-lookup"><span data-stu-id="6fdef-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

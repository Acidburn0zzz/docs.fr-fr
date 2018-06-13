---
title: ICorProfilerInfo::SetILInstrumentedCodeMap, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ecb80de1ae46b072df4bab8357e78e7a22ae298
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458060"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a><span data-ttu-id="c987c-102">ICorProfilerInfo::SetILInstrumentedCodeMap, méthode</span><span class="sxs-lookup"><span data-stu-id="c987c-102">ICorProfilerInfo::SetILInstrumentedCodeMap Method</span></span>
<span data-ttu-id="c987c-103">Définit une carte de code pour la fonction spécifiée à l’aide des entrées de mappage Microsoft intermediate language (MSIL) spécifiées.</span><span class="sxs-lookup"><span data-stu-id="c987c-103">Sets a code map for the specified function using the specified Microsoft intermediate language (MSIL) map entries.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c987c-104">Dans le .NET Framework version 2.0, l’appel `SetILInstrumentedCodeMap` sur un `FunctionID` que représente une fonction générique dans un domaine d’application particulier affecte toutes les instances de cette fonction dans le domaine d’application.</span><span class="sxs-lookup"><span data-stu-id="c987c-104">In the .NET Framework version 2.0, calling `SetILInstrumentedCodeMap` on a `FunctionID` that represents a generic function in a particular application domain will affect all instances of that function in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c987c-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c987c-105">Syntax</span></span>  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c987c-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c987c-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c987c-107">[in] L’ID de la fonction pour laquelle définir la carte de code.</span><span class="sxs-lookup"><span data-stu-id="c987c-107">[in] The ID of the function for which to set the code map.</span></span>  
  
 `fStartJit`  
 <span data-ttu-id="c987c-108">[in] Valeur booléenne qui indique si l’appel à la `SetILInstrumentedCodeMap` (méthode) est le premier pour un particulier `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="c987c-108">[in] A Boolean value that indicates whether the call to the `SetILInstrumentedCodeMap` method is the first for a particular `FunctionID`.</span></span> <span data-ttu-id="c987c-109">Définissez `fStartJit` à `true` dans le premier appel à `SetILInstrumentedCodeMap` pour une donnée `FunctionID`et `false` par la suite.</span><span class="sxs-lookup"><span data-stu-id="c987c-109">Set `fStartJit` to `true` in the first call to `SetILInstrumentedCodeMap` for a given `FunctionID`, and to `false` thereafter.</span></span>  
  
 `cILMapEntries`  
 <span data-ttu-id="c987c-110">[in] Le nombre d’éléments dans le `cILMapEntries` tableau.</span><span class="sxs-lookup"><span data-stu-id="c987c-110">[in] The number of elements in the `cILMapEntries` array.</span></span>  
  
 `rgILMapEntries`  
 <span data-ttu-id="c987c-111">[in] Tableau de structures COR_IL_MAP, dont chacun spécifie un offset MSIL.</span><span class="sxs-lookup"><span data-stu-id="c987c-111">[in] An array of COR_IL_MAP structures, each of which specifies an MSIL offset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c987c-112">Notes</span><span class="sxs-lookup"><span data-stu-id="c987c-112">Remarks</span></span>  
 <span data-ttu-id="c987c-113">Un profileur insère souvent des instructions dans le code source d’une méthode pour instrumenter cette méthode (par exemple, pour avertir lorsqu’une ligne source donnée est atteinte).</span><span class="sxs-lookup"><span data-stu-id="c987c-113">A profiler often inserts statements within the source code of a method in order to instrument that method (for example, to notify when a given source line is reached).</span></span> <span data-ttu-id="c987c-114">`SetILInstrumentedCodeMap` permet à un profileur de mapper les instructions MSIL d’origine vers leurs nouveaux emplacements.</span><span class="sxs-lookup"><span data-stu-id="c987c-114">`SetILInstrumentedCodeMap` enables a profiler to map the original MSIL instructions to their new locations.</span></span> <span data-ttu-id="c987c-115">Un profileur peut utiliser le [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) méthode pour obtenir l’offset MSIL d’origine pour un offset natif donné.</span><span class="sxs-lookup"><span data-stu-id="c987c-115">A profiler can use the [ICorProfilerInfo::GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) method to get the original MSIL offset for a given native offset.</span></span>  
  
 <span data-ttu-id="c987c-116">Le débogueur suppose que chaque ancien offset fait référence à un offset MSIL dans le code MSIL non modifié d’origine, et que chaque nouvel offset fait référence à l’offset MSIL dans le nouveau code instrumenté.</span><span class="sxs-lookup"><span data-stu-id="c987c-116">The debugger will assume that each old offset refers to an MSIL offset within the original, unmodified MSIL code, and that each new offset refers to the MSIL offset within the new, instrumented code.</span></span> <span data-ttu-id="c987c-117">Le mappage doit être trié par ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="c987c-117">The map should be sorted in increasing order.</span></span> <span data-ttu-id="c987c-118">Pour exécuter pas à pas pour fonctionner correctement, suivez ces instructions :</span><span class="sxs-lookup"><span data-stu-id="c987c-118">For stepping to work properly, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="c987c-119">Ne réorganisez pas le code MSIL instrumenté.</span><span class="sxs-lookup"><span data-stu-id="c987c-119">Do not reorder instrumented MSIL code.</span></span>  
  
-   <span data-ttu-id="c987c-120">Ne supprimez pas le code MSIL d’origine.</span><span class="sxs-lookup"><span data-stu-id="c987c-120">Do not remove the original MSIL code.</span></span>  
  
-   <span data-ttu-id="c987c-121">Inclure les entrées pour tous les points de séquence dans le fichier du programme (PDB) de la base de données dans le mappage.</span><span class="sxs-lookup"><span data-stu-id="c987c-121">Include entries for all the sequence points from the program database (PDB) file in the map.</span></span> <span data-ttu-id="c987c-122">Le mappage n’interpole pas les entrées manquantes.</span><span class="sxs-lookup"><span data-stu-id="c987c-122">The map does not interpolate missing entries.</span></span> <span data-ttu-id="c987c-123">Par conséquent, étant donné la carte suivante :</span><span class="sxs-lookup"><span data-stu-id="c987c-123">So, given the following map:</span></span>  
  
     <span data-ttu-id="c987c-124">(0 ancien, 0 nouveau)</span><span class="sxs-lookup"><span data-stu-id="c987c-124">(0 old, 0 new)</span></span>  
  
     <span data-ttu-id="c987c-125">(5 anciens, 10 nouveaux)</span><span class="sxs-lookup"><span data-stu-id="c987c-125">(5 old, 10 new)</span></span>  
  
     <span data-ttu-id="c987c-126">(9 ancien, 20 nouveaux)</span><span class="sxs-lookup"><span data-stu-id="c987c-126">(9 old, 20 new)</span></span>  
  
    -   <span data-ttu-id="c987c-127">Un ancien offset de 0, 1, 2, 3 ou 4 sera mappé au nouvel offset 0.</span><span class="sxs-lookup"><span data-stu-id="c987c-127">An old offset of 0, 1, 2, 3, or 4 will be mapped to new offset 0.</span></span>  
  
    -   <span data-ttu-id="c987c-128">Un ancien offset de 5, 6, 7 ou 8 sera mappé au nouvel offset 10.</span><span class="sxs-lookup"><span data-stu-id="c987c-128">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
    -   <span data-ttu-id="c987c-129">Un ancien offset de 9 ou version ultérieure sera mappé au nouvel offset 20.</span><span class="sxs-lookup"><span data-stu-id="c987c-129">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
    -   <span data-ttu-id="c987c-130">Un nouvel offset de 0, 1, 2, 3, 4, 5, 6, 7, 8 ou 9 sera mappé à l’ancien offset 0.</span><span class="sxs-lookup"><span data-stu-id="c987c-130">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
    -   <span data-ttu-id="c987c-131">Un nouvel offset de 10, 11, 12, 13, 14, 15, 16, 17, 18 ou 19 sera mappé à l’ancien offset 5.</span><span class="sxs-lookup"><span data-stu-id="c987c-131">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
    -   <span data-ttu-id="c987c-132">Un nouvel offset de 20 ou supérieur sera mappé à l’ancien offset 9.</span><span class="sxs-lookup"><span data-stu-id="c987c-132">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c987c-133">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c987c-133">Requirements</span></span>  
 <span data-ttu-id="c987c-134">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c987c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c987c-135">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c987c-135">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c987c-136">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c987c-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c987c-137">**Versions du .NET framework :** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c987c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c987c-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c987c-138">See Also</span></span>  
 [<span data-ttu-id="c987c-139">ICorProfilerInfo, interface</span><span class="sxs-lookup"><span data-stu-id="c987c-139">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

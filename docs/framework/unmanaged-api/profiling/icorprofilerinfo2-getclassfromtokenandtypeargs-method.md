---
title: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04be252092732296354cfec102cf8fe648ed2dd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456636"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="d972e-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs, méthode</span><span class="sxs-lookup"><span data-stu-id="d972e-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="d972e-103">Obtient le `ClassID` d’un type à l’aide du jeton de métadonnées spécifié et le `ClassID` valeurs des arguments de type.</span><span class="sxs-lookup"><span data-stu-id="d972e-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d972e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d972e-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d972e-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d972e-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="d972e-106">[in] L’ID du module dans lequel réside le type.</span><span class="sxs-lookup"><span data-stu-id="d972e-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="d972e-107">[in] Un `mdTypeDef` jeton de métadonnées qui fait référence au type.</span><span class="sxs-lookup"><span data-stu-id="d972e-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="d972e-108">[in] Le nombre de paramètres de type pour le type donné.</span><span class="sxs-lookup"><span data-stu-id="d972e-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="d972e-109">Cette valeur doit être zéro pour les types non génériques.</span><span class="sxs-lookup"><span data-stu-id="d972e-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="d972e-110">[in] Un tableau de `ClassID` valeurs, chacune d’elles est un argument de type.</span><span class="sxs-lookup"><span data-stu-id="d972e-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="d972e-111">La valeur de `typeArgs` peut être NULL si `cTypeArgs` est défini à zéro.</span><span class="sxs-lookup"><span data-stu-id="d972e-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="d972e-112">[out] Un pointeur vers le `ClassID` du type spécifié.</span><span class="sxs-lookup"><span data-stu-id="d972e-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d972e-113">Notes</span><span class="sxs-lookup"><span data-stu-id="d972e-113">Remarks</span></span>  
 <span data-ttu-id="d972e-114">Appel de la `GetClassFromTokenAndTypeArgs` méthode avec une `mdTypeRef` au lieu d’un `mdTypeDef` jeton de métadonnées peut avoir des résultats imprévisibles ; les appelants doivent résoudre le `mdTypeRef` à un `mdTypeDef` lors de son passage.</span><span class="sxs-lookup"><span data-stu-id="d972e-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="d972e-115">Si le type n’est pas déjà chargé, l’appel `GetClassFromTokenAndTypeArgs` déclenchera le chargement, qui est une opération dangereuse dans de nombreux contextes.</span><span class="sxs-lookup"><span data-stu-id="d972e-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="d972e-116">Par exemple, l’appel de cette méthode pendant le chargement de modules ou d’autres types peut entraîner une boucle infinie, que le runtime tente de charger des éléments.</span><span class="sxs-lookup"><span data-stu-id="d972e-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="d972e-117">En règle générale, utilisez des `GetClassFromTokenAndTypeArgs` est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="d972e-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="d972e-118">Si les profileurs sont intéressés par les événements pour un type particulier, ils doivent stocker le `ModuleID` et `mdTypeDef` de ce type et utilisez [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) pour vérifier si une donnée `ClassID` est celle de la type souhaité.</span><span class="sxs-lookup"><span data-stu-id="d972e-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d972e-119">Spécifications</span><span class="sxs-lookup"><span data-stu-id="d972e-119">Requirements</span></span>  
 <span data-ttu-id="d972e-120">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d972e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d972e-121">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d972e-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d972e-122">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d972e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d972e-123">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d972e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d972e-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d972e-124">See Also</span></span>  
 [<span data-ttu-id="d972e-125">ICorProfilerInfo, interface</span><span class="sxs-lookup"><span data-stu-id="d972e-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="d972e-126">ICorProfilerInfo2, interface</span><span class="sxs-lookup"><span data-stu-id="d972e-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)

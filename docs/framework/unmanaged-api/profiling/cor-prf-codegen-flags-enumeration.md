---
title: COR_PRF_CODEGEN_FLAGS, énumération
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 321318b63368ed6e57d235cf97d94485352f8686
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211359"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="9c037-102">COR_PRF_CODEGEN_FLAGS, énumération</span><span class="sxs-lookup"><span data-stu-id="9c037-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="9c037-103">Définit les indicateurs de génération de code qui peuvent être définies avec la [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="9c037-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c037-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9c037-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9c037-105">Membres</span><span class="sxs-lookup"><span data-stu-id="9c037-105">Members</span></span>  
  
|<span data-ttu-id="9c037-106">Membre</span><span class="sxs-lookup"><span data-stu-id="9c037-106">Member</span></span>|<span data-ttu-id="9c037-107">Description</span><span class="sxs-lookup"><span data-stu-id="9c037-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="9c037-108">Aucune fonctions ne seront incorporées dans les corps de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="9c037-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="9c037-109">Toutefois, la fonction elle-même peut être inline dans ses appelants.</span><span class="sxs-lookup"><span data-stu-id="9c037-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="9c037-110">Toutes les optimisations seront désactivées pour les corps de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="9c037-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="9c037-111">Toutefois, la fonction elle-même peut toujours être inline dans ses appelants.</span><span class="sxs-lookup"><span data-stu-id="9c037-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c037-112">Notes</span><span class="sxs-lookup"><span data-stu-id="9c037-112">Remarks</span></span>  
 <span data-ttu-id="9c037-113">Le `COR_PRF_CODEGEN_FLAGS` énumération est utilisée par le [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) méthode pour activer le profileur contrôler la génération de code pour la fonction recompilée de JIT.</span><span class="sxs-lookup"><span data-stu-id="9c037-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c037-114">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9c037-114">Requirements</span></span>  
 <span data-ttu-id="9c037-115">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c037-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c037-116">**En-tête :** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c037-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c037-117">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c037-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9c037-118">Versions de .NET Framework :</span><span class="sxs-lookup"><span data-stu-id="9c037-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9c037-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c037-119">See also</span></span>

- [<span data-ttu-id="9c037-120">Énumérations de profilage</span><span class="sxs-lookup"><span data-stu-id="9c037-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)

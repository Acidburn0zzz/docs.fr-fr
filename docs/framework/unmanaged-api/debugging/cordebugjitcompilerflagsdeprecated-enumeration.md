---
title: CorDebugJITCompilerFlagsDeprecated, énumération
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlagsDeprecated
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlagsDeprecated
helpviewer_keywords:
- CorDebugJITCompilerFlagsDeprecated enumeration [.NET Framework debugging]
ms.assetid: af15e2ca-6be1-472b-bd36-03644a1e3ddd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca206f0da69eddd3e98b599f2813fa7985daf057
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404125"
---
# <a name="cordebugjitcompilerflagsdeprecated-enumeration"></a><span data-ttu-id="db87b-102">CorDebugJITCompilerFlagsDeprecated, énumération</span><span class="sxs-lookup"><span data-stu-id="db87b-102">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>
<span data-ttu-id="db87b-103">Cette énumération est obsolète.</span><span class="sxs-lookup"><span data-stu-id="db87b-103">This enumeration is obsolete.</span></span> <span data-ttu-id="db87b-104">Utilisez le `CORDEBUG_JIT_DEFAULT` membre de la [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) énumération à la place.</span><span class="sxs-lookup"><span data-stu-id="db87b-104">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db87b-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="db87b-105">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlagsDeprecated {  
    CORDEBUG_JIT_TRACK_DEBUG_INFO  = 0x1  
} CorDebugJITCompilerFlagsDeprecated;  
```  
  
## <a name="members"></a><span data-ttu-id="db87b-106">Membres</span><span class="sxs-lookup"><span data-stu-id="db87b-106">Members</span></span>  
  
|<span data-ttu-id="db87b-107">Membre</span><span class="sxs-lookup"><span data-stu-id="db87b-107">Member</span></span>|<span data-ttu-id="db87b-108">Description</span><span class="sxs-lookup"><span data-stu-id="db87b-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_TRACK_DEBUG_INFO`|<span data-ttu-id="db87b-109">Utilisez plutôt `CORDEBUG_JIT_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="db87b-109">Use `CORDEBUG_JIT_DEFAULT` instead.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db87b-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="db87b-110">Requirements</span></span>  
 <span data-ttu-id="db87b-111">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db87b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db87b-112">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db87b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db87b-113">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db87b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db87b-114">**Versions du .NET framework :** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="db87b-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db87b-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db87b-115">See Also</span></span>  
 [<span data-ttu-id="db87b-116">Énumérations de débogage</span><span class="sxs-lookup"><span data-stu-id="db87b-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

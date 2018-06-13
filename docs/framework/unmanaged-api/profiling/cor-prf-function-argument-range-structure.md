---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE, structure
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92e3a0a930a4e4b91cac27cbed1b745dea4207a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450022"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="57feb-102">COR_PRF_FUNCTION_ARGUMENT_RANGE, structure</span><span class="sxs-lookup"><span data-stu-id="57feb-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="57feb-103">Représente un bloc d’arguments de fonction stockés de façon contiguë en mémoire selon un ordre de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="57feb-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57feb-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="57feb-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="57feb-105">Membres</span><span class="sxs-lookup"><span data-stu-id="57feb-105">Members</span></span>  
  
|<span data-ttu-id="57feb-106">Membres</span><span class="sxs-lookup"><span data-stu-id="57feb-106">Members</span></span>|<span data-ttu-id="57feb-107">Description</span><span class="sxs-lookup"><span data-stu-id="57feb-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="57feb-108">Adresse de départ du bloc.</span><span class="sxs-lookup"><span data-stu-id="57feb-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="57feb-109">La longueur du bloc contigu.</span><span class="sxs-lookup"><span data-stu-id="57feb-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57feb-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="57feb-110">Requirements</span></span>  
 <span data-ttu-id="57feb-111">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57feb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57feb-112">**En-tête :** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="57feb-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="57feb-113">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57feb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57feb-114">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57feb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57feb-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57feb-115">See Also</span></span>  
 [<span data-ttu-id="57feb-116">Structures de profilage</span><span class="sxs-lookup"><span data-stu-id="57feb-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)

---
title: CorDebugGenerationTypes, énumération
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 563c1fccd0b1fd254d721f631b0c8312b3b09bbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402429"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="38260-102">CorDebugGenerationTypes, énumération</span><span class="sxs-lookup"><span data-stu-id="38260-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="38260-103">Spécifie la génération d’une région de la mémoire sur le tas managé.</span><span class="sxs-lookup"><span data-stu-id="38260-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38260-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="38260-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="38260-105">Membres</span><span class="sxs-lookup"><span data-stu-id="38260-105">Members</span></span>  
  
|<span data-ttu-id="38260-106">Nom de membre</span><span class="sxs-lookup"><span data-stu-id="38260-106">Member name</span></span>|<span data-ttu-id="38260-107">Description</span><span class="sxs-lookup"><span data-stu-id="38260-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="38260-108">Génération 0.</span><span class="sxs-lookup"><span data-stu-id="38260-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="38260-109">Génération 1.</span><span class="sxs-lookup"><span data-stu-id="38260-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="38260-110">Génération 2.</span><span class="sxs-lookup"><span data-stu-id="38260-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="38260-111">Le tas d’objets volumineux.</span><span class="sxs-lookup"><span data-stu-id="38260-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38260-112">Notes</span><span class="sxs-lookup"><span data-stu-id="38260-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38260-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="38260-113">Requirements</span></span>  
 <span data-ttu-id="38260-114">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38260-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38260-115">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38260-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38260-116">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38260-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38260-117">**Versions du .NET framework :** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38260-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38260-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="38260-118">See Also</span></span>  
 [<span data-ttu-id="38260-119">Énumérations de débogage</span><span class="sxs-lookup"><span data-stu-id="38260-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

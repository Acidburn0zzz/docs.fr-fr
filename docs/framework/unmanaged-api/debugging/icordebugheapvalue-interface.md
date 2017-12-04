---
title: ICorDebugHeapValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue
helpviewer_keywords: ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868fc84ba3003909992334d1a66e1ed243eca18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="f5339-102">ICorDebugHeapValue Interface1</span><span class="sxs-lookup"><span data-stu-id="f5339-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="f5339-103">Une sous-classe de « ICorDebugValue » qui représente un objet qui a été collecté par le garbage collector du common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f5339-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5339-104">Méthodes</span><span class="sxs-lookup"><span data-stu-id="f5339-104">Methods</span></span>  
  
|<span data-ttu-id="f5339-105">Méthode</span><span class="sxs-lookup"><span data-stu-id="f5339-105">Method</span></span>|<span data-ttu-id="f5339-106">Description</span><span class="sxs-lookup"><span data-stu-id="f5339-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5339-107">CreateRelocBreakpoint (méthode)</span><span class="sxs-lookup"><span data-stu-id="f5339-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="f5339-108">Non implémenté.</span><span class="sxs-lookup"><span data-stu-id="f5339-108">Not implemented.</span></span>|  
|[<span data-ttu-id="f5339-109">IsValid (méthode)</span><span class="sxs-lookup"><span data-stu-id="f5339-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="f5339-110">Obtient une valeur qui indique si l’objet représenté par ce `ICorDebugHeapValue` est valide ou a été récupéré par le garbage collector.</span><span class="sxs-lookup"><span data-stu-id="f5339-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="f5339-111">Cette méthode a été déconseillée dans le .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="f5339-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5339-112">Remarques</span><span class="sxs-lookup"><span data-stu-id="f5339-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5339-113">Cette interface ne prend pas en charge l'appel à distance, que ce soit entre ordinateurs ou entre processus.</span><span class="sxs-lookup"><span data-stu-id="f5339-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5339-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="f5339-114">Requirements</span></span>  
 <span data-ttu-id="f5339-115">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5339-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5339-116">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5339-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5339-117">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5339-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5339-118">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5339-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5339-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5339-119">See Also</span></span>  
    
    
    
 [<span data-ttu-id="f5339-120">Interfaces de débogage</span><span class="sxs-lookup"><span data-stu-id="f5339-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
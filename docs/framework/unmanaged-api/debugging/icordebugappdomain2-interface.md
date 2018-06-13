---
title: ICorDebugAppDomain2 Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff6ffdd733cf6e7b923d88d057d7cd230c8d8541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407113"
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="3db51-102">ICorDebugAppDomain2 Interface1</span><span class="sxs-lookup"><span data-stu-id="3db51-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="3db51-103">Fournit des méthodes pour travailler avec les tableaux, les pointeurs, les pointeurs de fonction et les types référence.</span><span class="sxs-lookup"><span data-stu-id="3db51-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="3db51-104">Cette interface est une extension de l’interface ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="3db51-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3db51-105">Méthodes</span><span class="sxs-lookup"><span data-stu-id="3db51-105">Methods</span></span>  
  
|<span data-ttu-id="3db51-106">Méthode</span><span class="sxs-lookup"><span data-stu-id="3db51-106">Method</span></span>|<span data-ttu-id="3db51-107">Description</span><span class="sxs-lookup"><span data-stu-id="3db51-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3db51-108">GetArrayOrPointerType, méthode</span><span class="sxs-lookup"><span data-stu-id="3db51-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="3db51-109">Obtient un tableau du type spécifié, ou un pointeur ou une référence au type spécifié.</span><span class="sxs-lookup"><span data-stu-id="3db51-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="3db51-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="3db51-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="3db51-111">Obtient un pointeur vers une fonction qui a une signature donnée.</span><span class="sxs-lookup"><span data-stu-id="3db51-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3db51-112">Notes</span><span class="sxs-lookup"><span data-stu-id="3db51-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3db51-113">Cette interface ne prend pas en charge l'appel à distance, que ce soit entre ordinateurs ou entre processus.</span><span class="sxs-lookup"><span data-stu-id="3db51-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3db51-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="3db51-114">Requirements</span></span>  
 <span data-ttu-id="3db51-115">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3db51-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3db51-116">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3db51-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3db51-117">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3db51-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3db51-118">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3db51-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db51-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3db51-119">See Also</span></span>  
 [<span data-ttu-id="3db51-120">Interfaces de débogage</span><span class="sxs-lookup"><span data-stu-id="3db51-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

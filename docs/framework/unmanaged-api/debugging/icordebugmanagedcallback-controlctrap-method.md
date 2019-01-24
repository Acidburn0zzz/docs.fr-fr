---
title: ICorDebugManagedCallback::ControlCTrap, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f13800bcecbf6e7bdc5fede4e11c2ea15ecdec93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603896"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="11081-102">ICorDebugManagedCallback::ControlCTrap, méthode</span><span class="sxs-lookup"><span data-stu-id="11081-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="11081-103">Notifie le débogueur que CTRL + C est intercepté dans le processus en cours de débogage.</span><span class="sxs-lookup"><span data-stu-id="11081-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11081-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="11081-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11081-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="11081-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="11081-106">[in] Pointeur vers un objet ICorDebugProcess qui représente le processus dans lequel CTRL + C est intercepté.</span><span class="sxs-lookup"><span data-stu-id="11081-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11081-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="11081-107">Return Value</span></span>  
  
|<span data-ttu-id="11081-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11081-108">HRESULT</span></span>|<span data-ttu-id="11081-109">Description</span><span class="sxs-lookup"><span data-stu-id="11081-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11081-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="11081-110">S_OK</span></span>|<span data-ttu-id="11081-111">Le débogueur gère l’interruption CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="11081-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="11081-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="11081-112">S_FALSE</span></span>|<span data-ttu-id="11081-113">Le débogueur ne gère pas l’interruption CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="11081-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11081-114">Notes</span><span class="sxs-lookup"><span data-stu-id="11081-114">Remarks</span></span>  
 <span data-ttu-id="11081-115">Tous les domaines d’application au sein du processus sont arrêtés pour ce rappel.</span><span class="sxs-lookup"><span data-stu-id="11081-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11081-116">Spécifications</span><span class="sxs-lookup"><span data-stu-id="11081-116">Requirements</span></span>  
 <span data-ttu-id="11081-117">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11081-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11081-118">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11081-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11081-119">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11081-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11081-120">**Versions du .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11081-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11081-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11081-121">See also</span></span>
- [<span data-ttu-id="11081-122">ICorDebugManagedCallback, interface</span><span class="sxs-lookup"><span data-stu-id="11081-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

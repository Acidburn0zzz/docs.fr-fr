---
title: "ICLRDebugManager::EndConnection, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 210226b697eb3dffe574bd842ca31e83948891a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="64cbd-102">ICLRDebugManager::EndConnection, méthode</span><span class="sxs-lookup"><span data-stu-id="64cbd-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="64cbd-103">Supprime l’association entre une liste de tâches et un identificateur et un nom convivial.</span><span class="sxs-lookup"><span data-stu-id="64cbd-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64cbd-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="64cbd-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64cbd-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="64cbd-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="64cbd-106">[in] Identificateur spécifique à l’hôte pour la connexion et la liste associée des tâches de courantes language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="64cbd-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64cbd-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="64cbd-107">Return Value</span></span>  
  
|<span data-ttu-id="64cbd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64cbd-108">HRESULT</span></span>|<span data-ttu-id="64cbd-109">Description</span><span class="sxs-lookup"><span data-stu-id="64cbd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64cbd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="64cbd-110">S_OK</span></span>|<span data-ttu-id="64cbd-111">`EndConnection`retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="64cbd-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="64cbd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64cbd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64cbd-113">Le CLR n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="64cbd-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64cbd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64cbd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64cbd-115">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="64cbd-115">The call timed out.</span></span>|  
|<span data-ttu-id="64cbd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64cbd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64cbd-117">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="64cbd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64cbd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64cbd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64cbd-119">Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="64cbd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64cbd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64cbd-120">E_FAIL</span></span>|<span data-ttu-id="64cbd-121">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="64cbd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64cbd-122">Une fois une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="64cbd-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64cbd-123">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="64cbd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="64cbd-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="64cbd-124">E_INVALIDARG</span></span>|<span data-ttu-id="64cbd-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) n’a jamais été appelé à l’aide de `dwConnectionId`, ou `dwConnectionId` était zéro.</span><span class="sxs-lookup"><span data-stu-id="64cbd-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64cbd-126">Notes</span><span class="sxs-lookup"><span data-stu-id="64cbd-126">Remarks</span></span>  
 <span data-ttu-id="64cbd-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) fournit trois méthodes, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), et `EndConnection`, permettant d’associer des listes de tâches à des identificateurs et noms conviviaux.</span><span class="sxs-lookup"><span data-stu-id="64cbd-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64cbd-128">Ces trois méthodes doivent être appelées dans un ordre spécifique pour chaque ensemble de tâches.</span><span class="sxs-lookup"><span data-stu-id="64cbd-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="64cbd-129">`BeginConnection`est appelée en premier pour établir une nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="64cbd-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="64cbd-130">`SetConnectionTasks`est ensuite appelée pour fournir l’ensemble des tâches à associer à cette connexion.</span><span class="sxs-lookup"><span data-stu-id="64cbd-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="64cbd-131">`EndConnection`est appelée en dernier pour supprimer l’association entre la liste des tâches et l’identificateur et le nom convivial. Toutefois, les appels pour des connexions différentes peuvent être imbriqués.</span><span class="sxs-lookup"><span data-stu-id="64cbd-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64cbd-132">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="64cbd-132">Requirements</span></span>  
 <span data-ttu-id="64cbd-133">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64cbd-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64cbd-134">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64cbd-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64cbd-135">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64cbd-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64cbd-136">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64cbd-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64cbd-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64cbd-137">See Also</span></span>  
 [<span data-ttu-id="64cbd-138">ICLRControl, interface</span><span class="sxs-lookup"><span data-stu-id="64cbd-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="64cbd-139">ICLRDebugManager, interface</span><span class="sxs-lookup"><span data-stu-id="64cbd-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="64cbd-140">BeginConnection, méthode</span><span class="sxs-lookup"><span data-stu-id="64cbd-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="64cbd-141">SetConnectionTasks, méthode</span><span class="sxs-lookup"><span data-stu-id="64cbd-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="64cbd-142">IHostControl, interface</span><span class="sxs-lookup"><span data-stu-id="64cbd-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)

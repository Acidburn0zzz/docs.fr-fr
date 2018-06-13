---
title: IHostTaskManager::ReverseEnterRuntime, méthode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0945a4b32a155e99e0402dfcdcc826d1eff3eb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442018"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="027d2-102">IHostTaskManager::ReverseEnterRuntime, méthode</span><span class="sxs-lookup"><span data-stu-id="027d2-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="027d2-103">Avertit l’hôte qu’un appel est effectué dans le common language runtime (CLR) à partir de code non managé.</span><span class="sxs-lookup"><span data-stu-id="027d2-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="027d2-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="027d2-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="027d2-105">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="027d2-105">Return Value</span></span>  
  
|<span data-ttu-id="027d2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="027d2-106">HRESULT</span></span>|<span data-ttu-id="027d2-107">Description</span><span class="sxs-lookup"><span data-stu-id="027d2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="027d2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="027d2-108">S_OK</span></span>|<span data-ttu-id="027d2-109">`ReverseEnterRuntime` retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="027d2-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="027d2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="027d2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="027d2-111">Le CLR n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="027d2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="027d2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="027d2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="027d2-113">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="027d2-113">The call timed out.</span></span>|  
|<span data-ttu-id="027d2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="027d2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="027d2-115">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="027d2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="027d2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="027d2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="027d2-117">Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="027d2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="027d2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="027d2-118">E_FAIL</span></span>|<span data-ttu-id="027d2-119">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="027d2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="027d2-120">Lorsqu’une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="027d2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="027d2-121">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="027d2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="027d2-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="027d2-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="027d2-123">Pas assez de mémoire est disponible pour terminer l’allocation de la ressource demandée.</span><span class="sxs-lookup"><span data-stu-id="027d2-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="027d2-124">Notes</span><span class="sxs-lookup"><span data-stu-id="027d2-124">Remarks</span></span>  
 <span data-ttu-id="027d2-125">Si l’appel dans le CLR est effectué à partir d’une séquence provenant de code managé, chaque appel à `ReverseEnterRuntime` correspond à un appel à [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="027d2-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="027d2-126">Les appels peuvent provenir de code non managé sans être imbriqués.</span><span class="sxs-lookup"><span data-stu-id="027d2-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="027d2-127">Dans ce cas, il n’existe aucun appel à [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), ou `ReverseLeaveRuntime`et le nombre d’appels à `ReverseEnterRuntime` ne ne pas égal au nombre d’appels à `ReverseLeaveRuntime`.</span><span class="sxs-lookup"><span data-stu-id="027d2-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="027d2-128">Spécifications</span><span class="sxs-lookup"><span data-stu-id="027d2-128">Requirements</span></span>  
 <span data-ttu-id="027d2-129">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="027d2-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="027d2-130">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="027d2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="027d2-131">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="027d2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="027d2-132">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="027d2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027d2-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="027d2-133">See Also</span></span>  
 [<span data-ttu-id="027d2-134">ICLRTask, interface</span><span class="sxs-lookup"><span data-stu-id="027d2-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="027d2-135">ICLRTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="027d2-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="027d2-136">IHostTask, interface</span><span class="sxs-lookup"><span data-stu-id="027d2-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="027d2-137">IHostTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="027d2-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

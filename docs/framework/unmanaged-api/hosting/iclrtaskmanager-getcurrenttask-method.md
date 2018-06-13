---
title: ICLRTaskManager::GetCurrentTask, méthode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d447bd9712fc925cd738bd0c530d8329f510a5f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437376"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="62c83-102">ICLRTaskManager::GetCurrentTask, méthode</span><span class="sxs-lookup"><span data-stu-id="62c83-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="62c83-103">Obtient le [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance en cours d’exécution sur le thread de système d’exploitation d'où provenance l’appel de méthode.</span><span class="sxs-lookup"><span data-stu-id="62c83-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c83-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="62c83-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62c83-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="62c83-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="62c83-106">[out] Un pointeur vers l’adresse d’un `ICLRTask` instance en cours d’exécution sur le thread de système d’exploitation d'où provenance l’appel ou null si aucune tâche n’est en cours d’exécution sur ce thread.</span><span class="sxs-lookup"><span data-stu-id="62c83-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62c83-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="62c83-107">Return Value</span></span>  
  
|<span data-ttu-id="62c83-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62c83-108">HRESULT</span></span>|<span data-ttu-id="62c83-109">Description</span><span class="sxs-lookup"><span data-stu-id="62c83-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62c83-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="62c83-110">S_OK</span></span>|<span data-ttu-id="62c83-111">La méthode a été retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="62c83-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="62c83-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62c83-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62c83-113">Le common language runtime (CLR) n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="62c83-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62c83-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62c83-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62c83-115">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="62c83-115">The call timed out.</span></span>|  
|<span data-ttu-id="62c83-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62c83-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62c83-117">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="62c83-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62c83-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62c83-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62c83-119">Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="62c83-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62c83-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62c83-120">E_FAIL</span></span>|<span data-ttu-id="62c83-121">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="62c83-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62c83-122">Lorsqu’une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="62c83-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62c83-123">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="62c83-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62c83-124">Notes</span><span class="sxs-lookup"><span data-stu-id="62c83-124">Remarks</span></span>  
 <span data-ttu-id="62c83-125">Le `ICLRTask` de l’instance qui le `ppTask` paramètre pointe représente la tâche en cours d’exécution pour le CLR.</span><span class="sxs-lookup"><span data-stu-id="62c83-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="62c83-126">Le `ICLRTask` instance est associée à un correspondant [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance qui représente la tâche pour l’hôte.</span><span class="sxs-lookup"><span data-stu-id="62c83-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c83-127">Spécifications</span><span class="sxs-lookup"><span data-stu-id="62c83-127">Requirements</span></span>  
 <span data-ttu-id="62c83-128">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62c83-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62c83-129">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62c83-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62c83-130">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62c83-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62c83-131">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62c83-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c83-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62c83-132">See Also</span></span>  
 [<span data-ttu-id="62c83-133">ICLRTask, interface</span><span class="sxs-lookup"><span data-stu-id="62c83-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="62c83-134">ICLRTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="62c83-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="62c83-135">IHostTask, interface</span><span class="sxs-lookup"><span data-stu-id="62c83-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="62c83-136">IHostTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="62c83-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

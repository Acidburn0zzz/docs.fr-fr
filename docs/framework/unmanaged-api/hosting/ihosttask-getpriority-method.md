---
title: "IHostTask::GetPriority, méthode"
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
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 468a2e29ed3c031889fdc5df3d4defa6506d8fcf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="82793-102">IHostTask::GetPriority, méthode</span><span class="sxs-lookup"><span data-stu-id="82793-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="82793-103">Obtient le niveau de priorité de thread de la tâche représentée par le [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span><span class="sxs-lookup"><span data-stu-id="82793-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82793-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="82793-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82793-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="82793-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="82793-106">[out] Un pointeur vers un entier qui indique le niveau de priorité de thread de la tâche représentée par le `IHostTask` instance.</span><span class="sxs-lookup"><span data-stu-id="82793-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82793-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="82793-107">Return Value</span></span>  
  
|<span data-ttu-id="82793-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82793-108">HRESULT</span></span>|<span data-ttu-id="82793-109">Description</span><span class="sxs-lookup"><span data-stu-id="82793-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82793-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="82793-110">S_OK</span></span>|<span data-ttu-id="82793-111">`GetPriority`retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="82793-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="82793-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82793-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82793-113">Le common language runtime (CLR) n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="82793-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82793-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82793-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82793-115">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="82793-115">The call timed out.</span></span>|  
|<span data-ttu-id="82793-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82793-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82793-117">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="82793-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82793-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82793-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82793-119">Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="82793-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82793-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82793-120">E_FAIL</span></span>|<span data-ttu-id="82793-121">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="82793-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82793-122">Lorsqu’une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="82793-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82793-123">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="82793-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82793-124">Notes</span><span class="sxs-lookup"><span data-stu-id="82793-124">Remarks</span></span>  
 <span data-ttu-id="82793-125">Les valeurs de niveau de priorité de thread sont définies par Win32 `SetThreadPriority` (fonction).</span><span class="sxs-lookup"><span data-stu-id="82793-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82793-126">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="82793-126">Requirements</span></span>  
 <span data-ttu-id="82793-127">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82793-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82793-128">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82793-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82793-129">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82793-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82793-130">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82793-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82793-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82793-131">See Also</span></span>  
 [<span data-ttu-id="82793-132">ICLRTask, interface</span><span class="sxs-lookup"><span data-stu-id="82793-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="82793-133">ICLRTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="82793-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="82793-134">IHostTask, interface</span><span class="sxs-lookup"><span data-stu-id="82793-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="82793-135">IHostTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="82793-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)

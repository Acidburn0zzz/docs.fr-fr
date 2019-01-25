---
title: ICLRMemoryNotificationCallback::OnMemoryNotification, méthode
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c318b6f395e8bd7ccddf5fcbfc4acfcb11087fdf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722554"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="fd6da-102">ICLRMemoryNotificationCallback::OnMemoryNotification, méthode</span><span class="sxs-lookup"><span data-stu-id="fd6da-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="fd6da-103">Notifie le common language runtime (CLR) de la charge de mémoire sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fd6da-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd6da-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fd6da-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd6da-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="fd6da-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="fd6da-106">[in] Parmi les [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) valeurs, indiquant la sollicitation de la mémoire, l’ordinateur connaît actuellement.</span><span class="sxs-lookup"><span data-stu-id="fd6da-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd6da-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="fd6da-107">Return Value</span></span>  
  
|<span data-ttu-id="fd6da-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd6da-108">HRESULT</span></span>|<span data-ttu-id="fd6da-109">Description</span><span class="sxs-lookup"><span data-stu-id="fd6da-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd6da-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd6da-110">S_OK</span></span>|<span data-ttu-id="fd6da-111">`OnMemoryNotification` retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="fd6da-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="fd6da-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd6da-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd6da-113">Le CLR n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter le code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="fd6da-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd6da-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd6da-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd6da-115">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="fd6da-115">The call timed out.</span></span>|  
|<span data-ttu-id="fd6da-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd6da-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd6da-117">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="fd6da-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd6da-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd6da-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd6da-119">Un événement a été annulé alors qu’un thread bloqué ou Fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="fd6da-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd6da-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd6da-120">E_FAIL</span></span>|<span data-ttu-id="fd6da-121">Une défaillance catastrophique inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="fd6da-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd6da-122">Une fois une méthode retourne E_FAIL, le CLR n’est plus utilisable au sein du processus.</span><span class="sxs-lookup"><span data-stu-id="fd6da-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd6da-123">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd6da-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd6da-124">Notes</span><span class="sxs-lookup"><span data-stu-id="fd6da-124">Remarks</span></span>  
 <span data-ttu-id="fd6da-125">Le CLR enregistre un rappel à `OnMemoryNotification` à l’aide d’un appel à la [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="fd6da-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="fd6da-126">Le runtime utilise les informations retournées dans le rappel pour libérer de la mémoire supplémentaire lorsque l’hôte signale que la mémoire ressources sont faibles.</span><span class="sxs-lookup"><span data-stu-id="fd6da-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd6da-127">Les appels à `OnMemoryNotification` ne jamais se bloquer.</span><span class="sxs-lookup"><span data-stu-id="fd6da-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="fd6da-128">Elles retournent toujours immédiatement.</span><span class="sxs-lookup"><span data-stu-id="fd6da-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd6da-129">Spécifications</span><span class="sxs-lookup"><span data-stu-id="fd6da-129">Requirements</span></span>  
 <span data-ttu-id="fd6da-130">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd6da-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd6da-131">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd6da-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd6da-132">**Bibliothèque :** Inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd6da-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd6da-133">**Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd6da-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd6da-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fd6da-134">See also</span></span>
- [<span data-ttu-id="fd6da-135">IHostMemoryManager, interface</span><span class="sxs-lookup"><span data-stu-id="fd6da-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="fd6da-136">RegisterMemoryNotificationCallback, méthode</span><span class="sxs-lookup"><span data-stu-id="fd6da-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="fd6da-137">ICLRMemoryNotificationCallback, interface</span><span class="sxs-lookup"><span data-stu-id="fd6da-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)

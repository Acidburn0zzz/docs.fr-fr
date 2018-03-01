---
title: "ICLRPolicyManager::SetTimeout, méthode"
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
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5042d2f06d25b2cccc81239367362313210d3c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="f730e-102">ICLRPolicyManager::SetTimeout, méthode</span><span class="sxs-lookup"><span data-stu-id="f730e-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="f730e-103">Définit une valeur de délai d’attente pour l’opération spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f730e-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f730e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f730e-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f730e-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f730e-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="f730e-106">[in] Parmi les [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valeurs indiquant l’opération du common language runtime (CLR) pour laquelle définir un délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="f730e-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="f730e-107">Les valeurs suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="f730e-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="f730e-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="f730e-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="f730e-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="f730e-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="f730e-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f730e-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="f730e-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f730e-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="f730e-112">[in] La nouvelle valeur de délai d’attente en millisecondes.</span><span class="sxs-lookup"><span data-stu-id="f730e-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="f730e-113">Une valeur d’infini, l’opération jamais au délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="f730e-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f730e-114">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="f730e-114">Return Value</span></span>  
  
|<span data-ttu-id="f730e-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f730e-115">HRESULT</span></span>|<span data-ttu-id="f730e-116">Description</span><span class="sxs-lookup"><span data-stu-id="f730e-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f730e-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f730e-117">S_OK</span></span>|<span data-ttu-id="f730e-118">`SetTimeout`retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="f730e-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="f730e-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f730e-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f730e-120">Le CLR n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="f730e-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f730e-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f730e-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f730e-122">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="f730e-122">The call timed out.</span></span>|  
|<span data-ttu-id="f730e-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f730e-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f730e-124">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="f730e-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f730e-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f730e-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f730e-126">Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="f730e-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f730e-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f730e-127">E_FAIL</span></span>|<span data-ttu-id="f730e-128">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="f730e-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f730e-129">Une fois une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="f730e-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f730e-130">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f730e-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f730e-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f730e-131">E_INVALIDARG</span></span>|<span data-ttu-id="f730e-132">Impossible de définir un délai d’attente spécifié `operation`, ou une valeur non valide a été fournie pour `operation`.</span><span class="sxs-lookup"><span data-stu-id="f730e-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f730e-133">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="f730e-133">Requirements</span></span>  
 <span data-ttu-id="f730e-134">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f730e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f730e-135">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f730e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f730e-136">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f730e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f730e-137">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f730e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f730e-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f730e-138">See Also</span></span>  
 [<span data-ttu-id="f730e-139">EClrOperation, énumération</span><span class="sxs-lookup"><span data-stu-id="f730e-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="f730e-140">ICLRControl, interface</span><span class="sxs-lookup"><span data-stu-id="f730e-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f730e-141">ICLRPolicyManager, interface</span><span class="sxs-lookup"><span data-stu-id="f730e-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)

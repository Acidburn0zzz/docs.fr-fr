---
title: ICLRGCManager::Collect, méthode
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b9c3899c4319c623bc991d0775945f0a4dc09e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434753"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="2ce49-102">ICLRGCManager::Collect, méthode</span><span class="sxs-lookup"><span data-stu-id="2ce49-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="2ce49-103">Force une garbage collection pour la génération spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2ce49-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce49-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2ce49-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ce49-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2ce49-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="2ce49-106">[in] Génération à collecter.</span><span class="sxs-lookup"><span data-stu-id="2ce49-106">[in] The generation to collect.</span></span> <span data-ttu-id="2ce49-107">La valeur -1 force une collection de toutes les générations.</span><span class="sxs-lookup"><span data-stu-id="2ce49-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ce49-108">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="2ce49-108">Return Value</span></span>  
  
|<span data-ttu-id="2ce49-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ce49-109">HRESULT</span></span>|<span data-ttu-id="2ce49-110">Description</span><span class="sxs-lookup"><span data-stu-id="2ce49-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ce49-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ce49-111">S_OK</span></span>|<span data-ttu-id="2ce49-112">`Collect` retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="2ce49-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="2ce49-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ce49-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ce49-114">Le common language runtime (CLR) n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="2ce49-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ce49-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ce49-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ce49-116">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="2ce49-116">The call timed out.</span></span>|  
|<span data-ttu-id="2ce49-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ce49-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ce49-118">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="2ce49-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ce49-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ce49-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ce49-120">Un événement a été annulé alors qu’un thread bloqué ou une fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="2ce49-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ce49-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ce49-121">E_FAIL</span></span>|<span data-ttu-id="2ce49-122">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="2ce49-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ce49-123">Une fois une méthode retourne E_FAIL, le CLR n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="2ce49-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ce49-124">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2ce49-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ce49-125">Notes</span><span class="sxs-lookup"><span data-stu-id="2ce49-125">Remarks</span></span>  
 <span data-ttu-id="2ce49-126">Le `Collect` méthode force du garbage collector CLR à exécuter une collection indépendamment de son état actuel.</span><span class="sxs-lookup"><span data-stu-id="2ce49-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ce49-127">Spécifications</span><span class="sxs-lookup"><span data-stu-id="2ce49-127">Requirements</span></span>  
 <span data-ttu-id="2ce49-128">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ce49-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ce49-129">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ce49-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ce49-130">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ce49-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ce49-131">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ce49-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce49-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ce49-132">See Also</span></span>  
 [<span data-ttu-id="2ce49-133">Gestion automatique de la mémoire</span><span class="sxs-lookup"><span data-stu-id="2ce49-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="2ce49-134">Nettoyage de la mémoire</span><span class="sxs-lookup"><span data-stu-id="2ce49-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="2ce49-135">ICLRControl, interface</span><span class="sxs-lookup"><span data-stu-id="2ce49-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="2ce49-136">ICLRGCManager, interface</span><span class="sxs-lookup"><span data-stu-id="2ce49-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="2ce49-137">Interfaces d’hébergement CLR</span><span class="sxs-lookup"><span data-stu-id="2ce49-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="2ce49-138">Interfaces d’hébergement</span><span class="sxs-lookup"><span data-stu-id="2ce49-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="2ce49-139">Hébergement</span><span class="sxs-lookup"><span data-stu-id="2ce49-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

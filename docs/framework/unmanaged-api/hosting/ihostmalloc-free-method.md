---
title: IHostMAlloc::Free, méthode
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cf60d4e711d0c88b5fb8b4c213b19bdea564324
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477827"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="17c9f-102">IHostMAlloc::Free, méthode</span><span class="sxs-lookup"><span data-stu-id="17c9f-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="17c9f-103">Libère la mémoire qui a été alloué à l’aide de la [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) (fonction).</span><span class="sxs-lookup"><span data-stu-id="17c9f-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c9f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="17c9f-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17c9f-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="17c9f-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="17c9f-106">[in] Pointeur vers la mémoire à libérer.</span><span class="sxs-lookup"><span data-stu-id="17c9f-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17c9f-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="17c9f-107">Return Value</span></span>  
  
|<span data-ttu-id="17c9f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17c9f-108">HRESULT</span></span>|<span data-ttu-id="17c9f-109">Description</span><span class="sxs-lookup"><span data-stu-id="17c9f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17c9f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="17c9f-110">S_OK</span></span>|<span data-ttu-id="17c9f-111">`Free` retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="17c9f-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="17c9f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17c9f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17c9f-113">Le common language runtime (CLR) n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter le code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="17c9f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="17c9f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="17c9f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="17c9f-115">L’appel a expiré.</span><span class="sxs-lookup"><span data-stu-id="17c9f-115">The call timed out.</span></span>|  
|<span data-ttu-id="17c9f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="17c9f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="17c9f-117">L’appelant ne possède pas le verrou.</span><span class="sxs-lookup"><span data-stu-id="17c9f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="17c9f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="17c9f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="17c9f-119">Un événement a été annulé alors qu’un thread bloqué ou Fibre l’attendait.</span><span class="sxs-lookup"><span data-stu-id="17c9f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="17c9f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17c9f-120">E_FAIL</span></span>|<span data-ttu-id="17c9f-121">Une défaillance catastrophique inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="17c9f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="17c9f-122">Lorsqu’une méthode retourne E_FAIL, le CLR n’est plus utilisable au sein du processus.</span><span class="sxs-lookup"><span data-stu-id="17c9f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="17c9f-123">Les appels suivants aux méthodes d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="17c9f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="17c9f-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="17c9f-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="17c9f-125">Une tentative a été effectuée pour libérer la mémoire qui n’était pas alloué via l’hôte.</span><span class="sxs-lookup"><span data-stu-id="17c9f-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17c9f-126">Notes</span><span class="sxs-lookup"><span data-stu-id="17c9f-126">Remarks</span></span>  
 <span data-ttu-id="17c9f-127">Si le `pMem` paramètre fait référence à une région de mémoire qui n’était pas alloué à l’aide d’un appel à `Alloc`, l’hôte doit alors retourner HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="17c9f-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17c9f-128">Spécifications</span><span class="sxs-lookup"><span data-stu-id="17c9f-128">Requirements</span></span>  
 <span data-ttu-id="17c9f-129">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17c9f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17c9f-130">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="17c9f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17c9f-131">**Bibliothèque :** Inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17c9f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17c9f-132">**Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17c9f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c9f-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17c9f-133">See also</span></span>
- [<span data-ttu-id="17c9f-134">IHostMemoryManager, interface</span><span class="sxs-lookup"><span data-stu-id="17c9f-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="17c9f-135">IHostMalloc, interface</span><span class="sxs-lookup"><span data-stu-id="17c9f-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)

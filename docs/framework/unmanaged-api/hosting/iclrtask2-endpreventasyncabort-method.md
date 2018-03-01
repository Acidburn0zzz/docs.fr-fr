---
title: "ICLRTask2::EndPreventAsyncAbort, méthode"
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
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b18f6b8f6768c0a2980489cf8b84e16a9dd31350
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="bd4d8-102">ICLRTask2::EndPreventAsyncAbort, méthode</span><span class="sxs-lookup"><span data-stu-id="bd4d8-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="bd4d8-103">Permet de nouveau ou en attente de demandes d’abandon de thread de thread abandonne sur le thread actuel.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd4d8-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bd4d8-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bd4d8-105">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="bd4d8-105">Return Value</span></span>  
 <span data-ttu-id="bd4d8-106">Cette méthode retourne les HRESULT spécifiques suivants ainsi que les erreurs HRESULT indiquant l'échec de la méthode.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bd4d8-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd4d8-107">HRESULT</span></span>|<span data-ttu-id="bd4d8-108">Description</span><span class="sxs-lookup"><span data-stu-id="bd4d8-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd4d8-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd4d8-109">S_OK</span></span>|<span data-ttu-id="bd4d8-110">La commande s'est correctement terminée.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="bd4d8-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="bd4d8-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="bd4d8-112">La méthode a été appelée sur un thread qui n’est pas le thread actuel.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd4d8-113">Notes</span><span class="sxs-lookup"><span data-stu-id="bd4d8-113">Remarks</span></span>  
 <span data-ttu-id="bd4d8-114">Appel de ce compteur décrémente l’abandon de thread de délai de méthode pour le thread actuel d’une unité.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="bd4d8-115">Les appels à [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) et `EndPreventAsyncAbort` peuvent être imbriquées.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="bd4d8-116">Tant que le compteur est supérieur à zéro, pour le thread actuel abandons de thread.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="bd4d8-117">La fonctionnalité exposée par cette fonctionnalité est utilisée en interne par la machine virtuelle (VM).</span><span class="sxs-lookup"><span data-stu-id="bd4d8-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="bd4d8-118">Utilisation incorrecte de ces méthodes peut entraîner un comportement non spécifié dans la machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="bd4d8-119">Par exemple, l’appel `EndPreventAsyncAbort` sans appeler d’abord `BeginPreventAsyncAbort` Impossible de définir le compteur à zéro lorsque la machine virtuelle a précédemment incrémenté.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="bd4d8-120">De même, le compteur interne n’est pas vérifié pour le dépassement de capacité.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="bd4d8-121">Si elle dépasse sa limite intégrale, car il est incrémenté par l’hôte et la machine virtuelle, le comportement résultant n’est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="bd4d8-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd4d8-122">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="bd4d8-122">Requirements</span></span>  
 <span data-ttu-id="bd4d8-123">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd4d8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd4d8-124">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd4d8-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd4d8-125">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd4d8-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd4d8-126">**Versions du .NET framework :**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd4d8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd4d8-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd4d8-127">See Also</span></span>  
 [<span data-ttu-id="bd4d8-128">BeginPreventAsyncAbort, méthode</span><span class="sxs-lookup"><span data-stu-id="bd4d8-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [<span data-ttu-id="bd4d8-129">ICLRTask2, interface</span><span class="sxs-lookup"><span data-stu-id="bd4d8-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="bd4d8-130">ICLRTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="bd4d8-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="bd4d8-131">IHostTask, interface</span><span class="sxs-lookup"><span data-stu-id="bd4d8-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="bd4d8-132">IHostTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="bd4d8-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="bd4d8-133">Interfaces d’hébergement</span><span class="sxs-lookup"><span data-stu-id="bd4d8-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

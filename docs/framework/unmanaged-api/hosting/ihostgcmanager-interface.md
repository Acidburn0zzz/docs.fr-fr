---
title: IHostGCManager, interface
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4eac8abede82915386abc19c4c8389932451df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440374"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="1e2cf-102">IHostGCManager, interface</span><span class="sxs-lookup"><span data-stu-id="1e2cf-102">IHostGCManager Interface</span></span>
<span data-ttu-id="1e2cf-103">Fournit des méthodes qui notifier l’hôte d’événements dans le mécanisme de garbage collection implémentés par le common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1e2cf-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="1e2cf-104">Membres</span><span class="sxs-lookup"><span data-stu-id="1e2cf-104">Members</span></span>  
  
|<span data-ttu-id="1e2cf-105">Membre</span><span class="sxs-lookup"><span data-stu-id="1e2cf-105">Member</span></span>|<span data-ttu-id="1e2cf-106">Description</span><span class="sxs-lookup"><span data-stu-id="1e2cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e2cf-107">SuspensionEnding, méthode</span><span class="sxs-lookup"><span data-stu-id="1e2cf-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="1e2cf-108">Avertit l’hôte que le CLR reprend l’exécution de tâches sur les threads qui avaient été interrompus pour un garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="1e2cf-109">SuspensionStarting, méthode</span><span class="sxs-lookup"><span data-stu-id="1e2cf-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="1e2cf-110">Avertit l’hôte que le CLR interrompt l’exécution de tâches pour effectuer un garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="1e2cf-111">ThreadIsBlockingForSuspension, méthode</span><span class="sxs-lookup"><span data-stu-id="1e2cf-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="1e2cf-112">Avertit l’hôte que le thread à partir de laquelle l’appel de méthode a été effectué sur le point de bloquer pour un garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1e2cf-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e2cf-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="1e2cf-113">Requirements</span></span>  
 <span data-ttu-id="1e2cf-114">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e2cf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e2cf-115">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e2cf-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e2cf-116">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e2cf-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e2cf-117">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e2cf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e2cf-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e2cf-118">See Also</span></span>  
 [<span data-ttu-id="1e2cf-119">ICLRTask, interface</span><span class="sxs-lookup"><span data-stu-id="1e2cf-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1e2cf-120">ICLRTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="1e2cf-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1e2cf-121">IHostTask, interface</span><span class="sxs-lookup"><span data-stu-id="1e2cf-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1e2cf-122">IHostTaskManager, interface</span><span class="sxs-lookup"><span data-stu-id="1e2cf-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="1e2cf-123">Interfaces d’hébergement</span><span class="sxs-lookup"><span data-stu-id="1e2cf-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

---
title: ICLRGCManager, interface
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 045b924033630ea98d5a532a62f1037a5972df90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433922"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="0a6fa-102">ICLRGCManager, interface</span><span class="sxs-lookup"><span data-stu-id="0a6fa-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="0a6fa-103">Fournit des méthodes qui permettent à un hôte d’interagir avec le système de garbage collection du common language runtime.</span><span class="sxs-lookup"><span data-stu-id="0a6fa-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a6fa-104">En commençant par le [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], vous pouvez utiliser la [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) pour définir la taille d’un segment de garbage collection et la taille maximale de la génération du système de garbage collection 0 pour les valeurs supérieure (méthode) à la `DWORD` limite imposée par le [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="0a6fa-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a6fa-105">Méthodes</span><span class="sxs-lookup"><span data-stu-id="0a6fa-105">Methods</span></span>  
  
|<span data-ttu-id="0a6fa-106">Méthode</span><span class="sxs-lookup"><span data-stu-id="0a6fa-106">Method</span></span>|<span data-ttu-id="0a6fa-107">Description</span><span class="sxs-lookup"><span data-stu-id="0a6fa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a6fa-108">Collect, méthode</span><span class="sxs-lookup"><span data-stu-id="0a6fa-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="0a6fa-109">Force une garbage collection pour la génération spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0a6fa-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="0a6fa-110">GetStats, méthode</span><span class="sxs-lookup"><span data-stu-id="0a6fa-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="0a6fa-111">Obtient un jeu de statistiques actuelles concernant le système de garbage collection.</span><span class="sxs-lookup"><span data-stu-id="0a6fa-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="0a6fa-112">SetGCStartupLimits, méthode</span><span class="sxs-lookup"><span data-stu-id="0a6fa-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="0a6fa-113">Définit la taille d’un segment de garbage collection et la taille maximale de la génération du système de garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="0a6fa-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a6fa-114">Notes</span><span class="sxs-lookup"><span data-stu-id="0a6fa-114">Remarks</span></span>  
 <span data-ttu-id="0a6fa-115">Le common language runtime (CLR) implémente son mécanisme de garbage collection avec managé <xref:System.GC> type.</span><span class="sxs-lookup"><span data-stu-id="0a6fa-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="0a6fa-116">Pour plus d’informations sur le système de garbage collection, consultez [le Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="0a6fa-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a6fa-117">Spécifications</span><span class="sxs-lookup"><span data-stu-id="0a6fa-117">Requirements</span></span>  
 <span data-ttu-id="0a6fa-118">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a6fa-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a6fa-119">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0a6fa-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a6fa-120">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a6fa-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a6fa-121">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a6fa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a6fa-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a6fa-122">See Also</span></span>  
 [<span data-ttu-id="0a6fa-123">Gestion automatique de la mémoire</span><span class="sxs-lookup"><span data-stu-id="0a6fa-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="0a6fa-124">COR_GC_STATS, structure</span><span class="sxs-lookup"><span data-stu-id="0a6fa-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="0a6fa-125">ICLRControl, interface</span><span class="sxs-lookup"><span data-stu-id="0a6fa-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="0a6fa-126">Interfaces d’hébergement CLR</span><span class="sxs-lookup"><span data-stu-id="0a6fa-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="0a6fa-127">Interfaces d’hébergement</span><span class="sxs-lookup"><span data-stu-id="0a6fa-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="0a6fa-128">Hébergement</span><span class="sxs-lookup"><span data-stu-id="0a6fa-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)

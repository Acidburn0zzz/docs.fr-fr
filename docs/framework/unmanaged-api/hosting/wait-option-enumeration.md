---
title: "WAIT_OPTION, énumération"
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
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 143c191592efe8cfea8049f0dd5dc05a5bd4192f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="5f5b9-102">WAIT_OPTION, énumération</span><span class="sxs-lookup"><span data-stu-id="5f5b9-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="5f5b9-103">Contient des valeurs qui indiquent que l’action qu’un hôte doit effectuer si l’opération demandée par le common language runtime (CLR) se bloque.</span><span class="sxs-lookup"><span data-stu-id="5f5b9-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f5b9-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5f5b9-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="5f5b9-105">Membres</span><span class="sxs-lookup"><span data-stu-id="5f5b9-105">Members</span></span>  
  
|<span data-ttu-id="5f5b9-106">Membre</span><span class="sxs-lookup"><span data-stu-id="5f5b9-106">Member</span></span>|<span data-ttu-id="5f5b9-107">Description</span><span class="sxs-lookup"><span data-stu-id="5f5b9-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="5f5b9-108">Avertit l’hôte que la tâche doit être réactivée si le CLR appelle la [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="5f5b9-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="5f5b9-109">Avertit l’hôte qu’il doit pomper des messages sur le thread du système d’exploitation actuel si le thread est bloqué.</span><span class="sxs-lookup"><span data-stu-id="5f5b9-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="5f5b9-110">Le runtime spécifie cette valeur uniquement sur un <xref:System.Threading.ApartmentState.STA> thread.</span><span class="sxs-lookup"><span data-stu-id="5f5b9-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="5f5b9-111">Avertit l’hôte que la demande de synchronisation spécifiée ne peut pas être arrêtée par un hôte.</span><span class="sxs-lookup"><span data-stu-id="5f5b9-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="5f5b9-112">Autrement dit, l’hôte ne peut pas retourner `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="5f5b9-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f5b9-113">Notes</span><span class="sxs-lookup"><span data-stu-id="5f5b9-113">Remarks</span></span>  
 <span data-ttu-id="5f5b9-114">Le [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) et [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) méthodes prennent toutes deux un paramètre de ce type.</span><span class="sxs-lookup"><span data-stu-id="5f5b9-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f5b9-115">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="5f5b9-115">Requirements</span></span>  
 <span data-ttu-id="5f5b9-116">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f5b9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f5b9-117">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f5b9-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f5b9-118">**Bibliothèque :** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f5b9-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f5b9-119">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f5b9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f5b9-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f5b9-120">See Also</span></span>  
 [<span data-ttu-id="5f5b9-121">Énumérations d’hébergement</span><span class="sxs-lookup"><span data-stu-id="5f5b9-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

---
title: EInitializeNewDomainFlags, énumération
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0175ab1d06a8166a5bbfd0c42018085a801740f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431447"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="0c856-102">EInitializeNewDomainFlags, énumération</span><span class="sxs-lookup"><span data-stu-id="0c856-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="0c856-103">Permet à l’hôte de fournir le runtime avec des informations sur l’initialisation d’un domaine d’application.</span><span class="sxs-lookup"><span data-stu-id="0c856-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c856-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0c856-104">Syntax</span></span>  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0c856-105">Membres</span><span class="sxs-lookup"><span data-stu-id="0c856-105">Members</span></span>  
  
|<span data-ttu-id="0c856-106">Membre</span><span class="sxs-lookup"><span data-stu-id="0c856-106">Member</span></span>|<span data-ttu-id="0c856-107">Description</span><span class="sxs-lookup"><span data-stu-id="0c856-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="0c856-108">Aucun indicateur.</span><span class="sxs-lookup"><span data-stu-id="0c856-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="0c856-109">Informe le common language runtime (CLR) que l’ordinateur hôte ne sera pas apporter des modifications à l’état de sécurité du domaine d’application dans le <xref:System.AppDomainManager.InitializeNewDomain%2A> (méthode).</span><span class="sxs-lookup"><span data-stu-id="0c856-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c856-110">Notes</span><span class="sxs-lookup"><span data-stu-id="0c856-110">Remarks</span></span>  
 <span data-ttu-id="0c856-111">Le [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) méthode prend un paramètre de type `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="0c856-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c856-112">Spécifications</span><span class="sxs-lookup"><span data-stu-id="0c856-112">Requirements</span></span>  
 <span data-ttu-id="0c856-113">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c856-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c856-114">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c856-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c856-115">**Bibliothèque :** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c856-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c856-116">**Versions du .NET framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c856-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c856-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c856-117">See Also</span></span>  
 [<span data-ttu-id="0c856-118">Énumérations d’hébergement</span><span class="sxs-lookup"><span data-stu-id="0c856-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="0c856-119">SetAppDomainManagerType, méthode</span><span class="sxs-lookup"><span data-stu-id="0c856-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)

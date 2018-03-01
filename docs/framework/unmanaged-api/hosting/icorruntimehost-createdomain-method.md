---
title: "ICorRuntimeHost::CreateDomain, méthode"
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
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe0adad8397f42716368691abbb1d1c303fced97
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="90466-102">ICorRuntimeHost::CreateDomain, méthode</span><span class="sxs-lookup"><span data-stu-id="90466-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="90466-103">Crée un domaine d’application.</span><span class="sxs-lookup"><span data-stu-id="90466-103">Creates an application domain.</span></span> <span data-ttu-id="90466-104">L’appelant reçoit un pointeur d’interface de type <xref:System._AppDomain> à une instance de type <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90466-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90466-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="90466-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90466-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="90466-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="90466-107">[in] Un paramètre optionnel utilisé pour donner un nom convivial pour le domaine.</span><span class="sxs-lookup"><span data-stu-id="90466-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="90466-108">Ce nom convivial peut être affiché dans les interfaces utilisateur telles que les débogueurs pour identifier le domaine.</span><span class="sxs-lookup"><span data-stu-id="90466-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="90466-109">[in] Tableau facultatif de pointeurs vers les `IIdentity` instances qui représentent la preuve mappée via une stratégie de sécurité pour établir un jeu d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="90466-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="90466-110">Un `IIdentity` objet peut être obtenu en appelant le [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="90466-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="90466-111">[out] Un pointeur d’interface de type <xref:System._AppDomain> à une instance de <xref:System.AppDomain?displayProperty=nameWithType> qui peut être utilisé pour contrôler davantage le domaine.</span><span class="sxs-lookup"><span data-stu-id="90466-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90466-112">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="90466-112">Return Value</span></span>  
  
|<span data-ttu-id="90466-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90466-113">HRESULT</span></span>|<span data-ttu-id="90466-114">Description</span><span class="sxs-lookup"><span data-stu-id="90466-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90466-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="90466-115">S_OK</span></span>|<span data-ttu-id="90466-116">L’opération a réussi.</span><span class="sxs-lookup"><span data-stu-id="90466-116">The operation was successful.</span></span>|  
|<span data-ttu-id="90466-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="90466-117">S_FALSE</span></span>|<span data-ttu-id="90466-118">L’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="90466-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="90466-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="90466-119">E_FAIL</span></span>|<span data-ttu-id="90466-120">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="90466-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="90466-121">Si une méthode retourne E_FAIL, le common language runtime (CLR) n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="90466-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="90466-122">Les appels suivants à toute API d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="90466-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="90466-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="90466-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="90466-124">Le CLR n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="90466-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90466-125">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="90466-125">Requirements</span></span>  
 <span data-ttu-id="90466-126">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90466-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90466-127">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="90466-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90466-128">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90466-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90466-129">**Versions du .NET framework :** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="90466-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90466-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90466-130">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="90466-131">ICorRuntimeHost, interface</span><span class="sxs-lookup"><span data-stu-id="90466-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)

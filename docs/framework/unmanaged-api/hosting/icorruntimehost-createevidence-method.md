---
title: ICorRuntimeHost::CreateEvidence, méthode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c54c21008e5922a5357f503821d87e297f0d00e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499249"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="71c03-102">ICorRuntimeHost::CreateEvidence, méthode</span><span class="sxs-lookup"><span data-stu-id="71c03-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="71c03-103">Obtient un pointeur d’interface de type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, ce qui permet à l’hôte de créer la preuve de sécurité à passer à la [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) ou [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="71c03-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71c03-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="71c03-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71c03-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="71c03-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="71c03-106">[out] Un pointeur d’interface vers un <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance utilisée pour créer la preuve de sécurité.</span><span class="sxs-lookup"><span data-stu-id="71c03-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="71c03-107">Ce pointeur est tapé `IUnknown`, de sorte que les appelants doivent généralement appeler `QueryInterface` sur cette interface pour obtenir un pointeur vers un <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="71c03-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71c03-108">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="71c03-108">Return Value</span></span>  
  
|<span data-ttu-id="71c03-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71c03-109">HRESULT</span></span>|<span data-ttu-id="71c03-110">Description</span><span class="sxs-lookup"><span data-stu-id="71c03-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71c03-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="71c03-111">S_OK</span></span>|<span data-ttu-id="71c03-112">L’opération a réussi.</span><span class="sxs-lookup"><span data-stu-id="71c03-112">The operation was successful.</span></span>|  
|<span data-ttu-id="71c03-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="71c03-113">S_FALSE</span></span>|<span data-ttu-id="71c03-114">L’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="71c03-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="71c03-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71c03-115">E_FAIL</span></span>|<span data-ttu-id="71c03-116">Une défaillance grave et inconnue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="71c03-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="71c03-117">Si une méthode retourne E_FAIL, le common language runtime (CLR) n’est plus utilisable dans le processus.</span><span class="sxs-lookup"><span data-stu-id="71c03-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="71c03-118">Les appels suivants à toute API d’hébergement retournent HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71c03-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71c03-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71c03-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71c03-120">Le CLR n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter le code managé ou traiter l’appel avec succès.</span><span class="sxs-lookup"><span data-stu-id="71c03-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71c03-121">Notes</span><span class="sxs-lookup"><span data-stu-id="71c03-121">Remarks</span></span>  
 <span data-ttu-id="71c03-122">Cette méthode retourne une collection vide qui ne peuvent pas être remplie à partir du code natif.</span><span class="sxs-lookup"><span data-stu-id="71c03-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="71c03-123">Vous devez utiliser le <xref:System.Security.Policy.Evidence> méthode à la place.</span><span class="sxs-lookup"><span data-stu-id="71c03-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71c03-124">Spécifications</span><span class="sxs-lookup"><span data-stu-id="71c03-124">Requirements</span></span>  
 <span data-ttu-id="71c03-125">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71c03-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71c03-126">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71c03-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71c03-127">**Bibliothèque :** Inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71c03-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71c03-128">**Version du .NET framework :** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="71c03-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c03-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71c03-129">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="71c03-130">ICorRuntimeHost, interface</span><span class="sxs-lookup"><span data-stu-id="71c03-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)

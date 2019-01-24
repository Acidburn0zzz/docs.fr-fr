---
title: _CorDllMain, fonction
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f62ad2c9ec6e1c9672ac5c78e838e926b02359f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512370"
---
# <a name="cordllmain-function"></a><span data-ttu-id="6bdd8-102">_CorDllMain, fonction</span><span class="sxs-lookup"><span data-stu-id="6bdd8-102">_CorDllMain Function</span></span>
<span data-ttu-id="6bdd8-103">Initialise le common language runtime (CLR), recherche le point d’entrée managé dans l’en-tête CLR de l’assembly DLL et commence l’exécution.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bdd8-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6bdd8-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bdd8-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="6bdd8-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="6bdd8-106">[in] Le handle d’instance du module chargé.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="6bdd8-107">[in] Indique la raison pour laquelle la fonction de point d’entrée DLL est appelée.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="6bdd8-108">Ce paramètre peut être une des valeurs suivantes : DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH ou DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="6bdd8-109">Pour obtenir une description de ces valeurs, consultez le `DllMain` documentation dans le kit Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="6bdd8-110">[in] Inutilisé.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bdd8-111">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="6bdd8-111">Return Value</span></span>  
 <span data-ttu-id="6bdd8-112">Cette méthode retourne `true` de réussite et `false` si une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bdd8-113">Notes</span><span class="sxs-lookup"><span data-stu-id="6bdd8-113">Remarks</span></span>  
 <span data-ttu-id="6bdd8-114">Cette fonction est appelée par le chargeur du système d’exploitation pour les assemblys DLL.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="6bdd8-115">Pour les assemblys exécutables, le chargeur appelle le [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) fonctionner à la place.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="6bdd8-116">Le chargeur du système d’exploitation appelle cette méthode, quel que soit le point d’entrée spécifié dans le fichier DLL.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
 <span data-ttu-id="6bdd8-117">Dans Windows 98, Windows ME, Windows NT et Windows 2000, le `_CorDllMain` fonction est appelée indirectement via un fixupin le chargeur du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-117">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorDllMain` function is called indirectly through a fixupin the operating system loader.</span></span> <span data-ttu-id="6bdd8-118">Dans tous les autres versions de Windows, elle est appelée directement par le chargeur du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-118">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="6bdd8-119">Pour plus d’informations, consultez la section Remarques dans le [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) rubrique.</span><span class="sxs-lookup"><span data-stu-id="6bdd8-119">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bdd8-120">Spécifications</span><span class="sxs-lookup"><span data-stu-id="6bdd8-120">Requirements</span></span>  
 <span data-ttu-id="6bdd8-121">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bdd8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bdd8-122">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6bdd8-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bdd8-123">**Bibliothèque :** Inclus en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6bdd8-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bdd8-124">**Versions du .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bdd8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bdd8-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6bdd8-125">See also</span></span>
- [<span data-ttu-id="6bdd8-126">Fonctions statiques globales des métadonnées</span><span class="sxs-lookup"><span data-stu-id="6bdd8-126">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

---
title: IMetaDataEmit::SetMethodProps, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ef6771ec3f458c20701cc330a5730367b3c5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445924"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="3efda-102">IMetaDataEmit::SetMethodProps, méthode</span><span class="sxs-lookup"><span data-stu-id="3efda-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="3efda-103">Définit ou met à jour de la fonctionnalité, stockée à l’adresse virtuelle relative spécifiée, d’une méthode définie par un appel antérieur à [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="3efda-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3efda-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3efda-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3efda-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="3efda-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="3efda-106">[in] Le jeton pour la méthode doit être modifié.</span><span class="sxs-lookup"><span data-stu-id="3efda-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="3efda-107">[in] Les attributs de membre.</span><span class="sxs-lookup"><span data-stu-id="3efda-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="3efda-108">[in] L’adresse du code.</span><span class="sxs-lookup"><span data-stu-id="3efda-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="3efda-109">[in] Les indicateurs d’implémentation pour la méthode.</span><span class="sxs-lookup"><span data-stu-id="3efda-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3efda-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="3efda-110">Requirements</span></span>  
 <span data-ttu-id="3efda-111">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3efda-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3efda-112">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3efda-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3efda-113">**Bibliothèque :** utilisé en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3efda-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3efda-114">**Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3efda-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3efda-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3efda-115">See Also</span></span>  
 [<span data-ttu-id="3efda-116">IMetaDataEmit, interface</span><span class="sxs-lookup"><span data-stu-id="3efda-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="3efda-117">IMetaDataEmit2, interface</span><span class="sxs-lookup"><span data-stu-id="3efda-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

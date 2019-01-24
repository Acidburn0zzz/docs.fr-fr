---
title: IInstallReferenceEnum::GetNextInstallReferenceItem, méthode
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba2abaccfc4a9ae2d1f07677a49a72c980acda24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607499"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="ba2fb-102">IInstallReferenceEnum::GetNextInstallReferenceItem, méthode</span><span class="sxs-lookup"><span data-stu-id="ba2fb-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="ba2fb-103">Obtient un pointeur vers la prochaine [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) objet contenu dans ce [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) objet.</span><span class="sxs-lookup"><span data-stu-id="ba2fb-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba2fb-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ba2fb-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba2fb-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ba2fb-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="ba2fb-106">[out] Retourné `IInstallReferenceItem` pointeur.</span><span class="sxs-lookup"><span data-stu-id="ba2fb-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ba2fb-107">[in] Réservé pour une extensibilité future.</span><span class="sxs-lookup"><span data-stu-id="ba2fb-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ba2fb-108">`dwFlags` doit être 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="ba2fb-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ba2fb-109">[in] Réservé pour une extensibilité future.</span><span class="sxs-lookup"><span data-stu-id="ba2fb-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ba2fb-110">`pvReserved` doit être une référence null.</span><span class="sxs-lookup"><span data-stu-id="ba2fb-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba2fb-111">Spécifications</span><span class="sxs-lookup"><span data-stu-id="ba2fb-111">Requirements</span></span>  
 <span data-ttu-id="ba2fb-112">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba2fb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba2fb-113">**En-tête :** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ba2fb-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ba2fb-114">**Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba2fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba2fb-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba2fb-115">See also</span></span>
- [<span data-ttu-id="ba2fb-116">IInstallReferenceItem, interface</span><span class="sxs-lookup"><span data-stu-id="ba2fb-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="ba2fb-117">IInstallReferenceEnum, interface</span><span class="sxs-lookup"><span data-stu-id="ba2fb-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)

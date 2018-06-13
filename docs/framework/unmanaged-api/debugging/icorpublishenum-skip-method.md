---
title: ICorPublishEnum::Skip, méthode
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a691f61fcd25b7aaaae90e6adcc3c2ee0c421cf0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424256"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="1d645-102">ICorPublishEnum::Skip, méthode</span><span class="sxs-lookup"><span data-stu-id="1d645-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="1d645-103">Déplace le curseur vers l’avant dans l’énumération par le nombre spécifié d’éléments.</span><span class="sxs-lookup"><span data-stu-id="1d645-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d645-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1d645-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d645-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1d645-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1d645-106">[in] Le nombre d’éléments permettant de déplacer le curseur vers le bas.</span><span class="sxs-lookup"><span data-stu-id="1d645-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d645-107">Spécifications</span><span class="sxs-lookup"><span data-stu-id="1d645-107">Requirements</span></span>  
 <span data-ttu-id="1d645-108">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d645-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d645-109">**En-tête :** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1d645-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1d645-110">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d645-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d645-111">**Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d645-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d645-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d645-112">See Also</span></span>  
 [<span data-ttu-id="1d645-113">ICorPublishEnum, interface</span><span class="sxs-lookup"><span data-stu-id="1d645-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)

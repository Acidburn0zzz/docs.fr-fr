---
title: ICorPublishAppDomainEnum, interface
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
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f84a93053744f059eb3fdd06e2fb69e098e24ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="70358-102">ICorPublishAppDomainEnum, interface</span><span class="sxs-lookup"><span data-stu-id="70358-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="70358-103">Une sous-classe de la [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface qui fournit des méthodes pour parcourir une collection de [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) les objets qui existent actuellement dans un processus.</span><span class="sxs-lookup"><span data-stu-id="70358-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70358-104">Méthodes</span><span class="sxs-lookup"><span data-stu-id="70358-104">Methods</span></span>  
  
|<span data-ttu-id="70358-105">Méthode</span><span class="sxs-lookup"><span data-stu-id="70358-105">Method</span></span>|<span data-ttu-id="70358-106">Description</span><span class="sxs-lookup"><span data-stu-id="70358-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70358-107">Next, méthode</span><span class="sxs-lookup"><span data-stu-id="70358-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="70358-108">Obtient le nombre spécifié de `ICorPublishAppDomain` les instances de la collection, en commençant à la position actuelle.</span><span class="sxs-lookup"><span data-stu-id="70358-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70358-109">Notes</span><span class="sxs-lookup"><span data-stu-id="70358-109">Remarks</span></span>  
 <span data-ttu-id="70358-110">Le `ICorPublishAppDomainEnum` interface implémente les méthodes de l’interface abstraite [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="70358-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70358-111">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="70358-111">Requirements</span></span>  
 <span data-ttu-id="70358-112">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70358-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70358-113">**En-tête :** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="70358-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="70358-114">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70358-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70358-115">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70358-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70358-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70358-116">See Also</span></span>  
 [<span data-ttu-id="70358-117">Interfaces de débogage</span><span class="sxs-lookup"><span data-stu-id="70358-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="70358-118">CorpubPublish, coclasse</span><span class="sxs-lookup"><span data-stu-id="70358-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)

---
title: "IBindingDisplay::InitializeForProcess, méthode"
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
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 56f55788fcaf08507f413a03c5364ce3bcdbbf3c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="d11ac-102">IBindingDisplay::InitializeForProcess, méthode</span><span class="sxs-lookup"><span data-stu-id="d11ac-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="d11ac-103">Initialise le [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) objet.</span><span class="sxs-lookup"><span data-stu-id="d11ac-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11ac-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d11ac-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d11ac-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d11ac-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="d11ac-106">[in] L’identificateur de processus.</span><span class="sxs-lookup"><span data-stu-id="d11ac-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d11ac-107">Notes</span><span class="sxs-lookup"><span data-stu-id="d11ac-107">Remarks</span></span>  
 <span data-ttu-id="d11ac-108">Le débogueur appelle la `InitializeForProcess` méthode au moment de la création pour initialiser l’affichage de la liaison.</span><span class="sxs-lookup"><span data-stu-id="d11ac-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="d11ac-109">`InitializeForProcess`doit être appelée au moment de la création avant toute autre méthode pour `IBindingDisplay` est appelée.</span><span class="sxs-lookup"><span data-stu-id="d11ac-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d11ac-110">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="d11ac-110">Requirements</span></span>  
 <span data-ttu-id="d11ac-111">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d11ac-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d11ac-112">**En-tête :** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="d11ac-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="d11ac-113">**Bibliothèque :** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="d11ac-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="d11ac-114">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d11ac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11ac-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d11ac-115">See Also</span></span>  
 [<span data-ttu-id="d11ac-116">IBindingDisplay, interface</span><span class="sxs-lookup"><span data-stu-id="d11ac-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)

---
title: "ITypeName::GetNames, méthode"
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
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62635531149f90a499b4809869ed2a2efded58a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="25e09-102">ITypeName::GetNames, méthode</span><span class="sxs-lookup"><span data-stu-id="25e09-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="25e09-103">Cette m&#233;thode prend en charge l'infrastructure .NET Framework et n'est pas destin&#233;e &#224; &#234;tre utilis&#233;e directement &#224; partir de votre code.</span><span class="sxs-lookup"><span data-stu-id="25e09-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25e09-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="25e09-104">Syntax</span></span>  
  
```  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="25e09-105">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="25e09-105">Requirements</span></span>  
 <span data-ttu-id="25e09-106">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25e09-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25e09-107">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25e09-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25e09-108">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="25e09-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25e09-109">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25e09-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e09-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25e09-110">See Also</span></span>  
 [<span data-ttu-id="25e09-111">Interfaces d’hébergement</span><span class="sxs-lookup"><span data-stu-id="25e09-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

---
title: Méthode ICLRStrongName::StrongNameHashSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ebf2e0225cf497a0b89a46ecdb3e203d5b9a4cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432012"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="859aa-102">Méthode ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="859aa-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="859aa-103">Obtient la taille de mémoire tampon requise pour un hachage à l’aide de l’algorithme de hachage spécifié.</span><span class="sxs-lookup"><span data-stu-id="859aa-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="859aa-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="859aa-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="859aa-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="859aa-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="859aa-106">[in] L’algorithme de hachage utilisé pour calculer la taille du tampon.</span><span class="sxs-lookup"><span data-stu-id="859aa-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="859aa-107">[out] La taille de la mémoire tampon retournée, en octets.</span><span class="sxs-lookup"><span data-stu-id="859aa-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="859aa-108">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="859aa-108">Return Value</span></span>  
 <span data-ttu-id="859aa-109">`S_OK` Si la méthode a réussi ; Sinon, une valeur HRESULT qui indique un échec (voir [valeurs HRESULT courantes](http://go.microsoft.com/fwlink/?LinkId=213878) pour obtenir la liste).</span><span class="sxs-lookup"><span data-stu-id="859aa-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="859aa-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="859aa-110">Requirements</span></span>  
 <span data-ttu-id="859aa-111">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="859aa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="859aa-112">**En-tête :** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="859aa-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="859aa-113">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="859aa-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="859aa-114">**Versions du .NET framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="859aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859aa-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="859aa-115">See Also</span></span>  
 [<span data-ttu-id="859aa-116">ICLRStrongName, interface</span><span class="sxs-lookup"><span data-stu-id="859aa-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

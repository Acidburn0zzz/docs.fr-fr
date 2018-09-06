---
title: Méthode ICLRStrongName::StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc5a40a0e26f116ce1700973a5000e8d6bbbd890
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43799799"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="f93e2-102">Méthode ICLRStrongName::StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="f93e2-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="f93e2-103">Retourne la taille de la signature de nom fort.</span><span class="sxs-lookup"><span data-stu-id="f93e2-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="f93e2-104">Cette méthode est généralement utilisée par les compilateurs pour déterminer la quantité d’espace à réserver dans le fichier lors de la création d’un assembly à signature différée.</span><span class="sxs-lookup"><span data-stu-id="f93e2-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f93e2-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f93e2-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="f93e2-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f93e2-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="f93e2-107">[in] Une structure de type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) qui contient la partie publique de la paire de clés utilisée pour générer la signature de nom fort.</span><span class="sxs-lookup"><span data-stu-id="f93e2-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="f93e2-108">[in] La taille, en octets, de `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f93e2-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="f93e2-109">[in] Le nombre d’octets requis pour stocker la signature de nom fort.</span><span class="sxs-lookup"><span data-stu-id="f93e2-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f93e2-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="f93e2-110">Return Value</span></span>  
 <span data-ttu-id="f93e2-111">`S_OK` Si la méthode a réussi ; Sinon, une valeur HRESULT qui indique un échec (consultez [valeurs HRESULT courantes](https://go.microsoft.com/fwlink/?LinkId=213878) pour obtenir la liste).</span><span class="sxs-lookup"><span data-stu-id="f93e2-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f93e2-112">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="f93e2-112">Requirements</span></span>  
 <span data-ttu-id="f93e2-113">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f93e2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f93e2-114">**En-tête :** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f93e2-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f93e2-115">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f93e2-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f93e2-116">**Versions du .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f93e2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f93e2-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f93e2-117">See Also</span></span>  
 [<span data-ttu-id="f93e2-118">ICLRStrongName, interface</span><span class="sxs-lookup"><span data-stu-id="f93e2-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

---
title: Méthode ICLRStrongName::StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00e425b56ae555b153685b5af0ac58b6ab4c335b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391644"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="c8f33-102">Méthode ICLRStrongName::StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="c8f33-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="c8f33-103">Crée un jeton de nom fort à partir du fichier d’assembly spécifié et retourne la clé publique qui représente le jeton.</span><span class="sxs-lookup"><span data-stu-id="c8f33-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f33-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c8f33-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8f33-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c8f33-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c8f33-106">[in] Le chemin d’accès au fichier exécutable portable (PE) pour l’assembly.</span><span class="sxs-lookup"><span data-stu-id="c8f33-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c8f33-107">[out] Le jeton de nom fort retourné.</span><span class="sxs-lookup"><span data-stu-id="c8f33-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c8f33-108">[out] La taille, en octets, du jeton de nom fort.</span><span class="sxs-lookup"><span data-stu-id="c8f33-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="c8f33-109">[out] La clé publique retournée.</span><span class="sxs-lookup"><span data-stu-id="c8f33-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="c8f33-110">[out] La taille, en octets, de la clé publique.</span><span class="sxs-lookup"><span data-stu-id="c8f33-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8f33-111">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c8f33-111">Return Value</span></span>  
 <span data-ttu-id="c8f33-112">`S_OK` Si la méthode a réussi ; Sinon, une valeur HRESULT qui indique un échec (consultez [valeurs HRESULT courantes](https://go.microsoft.com/fwlink/?LinkId=213878) pour obtenir la liste).</span><span class="sxs-lookup"><span data-stu-id="c8f33-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8f33-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c8f33-113">Remarks</span></span>  
 <span data-ttu-id="c8f33-114">Un jeton de nom fort est la forme abrégée d’une clé publique.</span><span class="sxs-lookup"><span data-stu-id="c8f33-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="c8f33-115">Le jeton est un hachage 64 bits qui est créé à partir de la clé publique utilisée pour signer l’assembly.</span><span class="sxs-lookup"><span data-stu-id="c8f33-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="c8f33-116">Le jeton est une partie du nom fort pour l’assembly et peut être lues à partir des métadonnées d’assembly.</span><span class="sxs-lookup"><span data-stu-id="c8f33-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="c8f33-117">Une fois que la clé est récupérée et le jeton est créé, vous devez appeler la [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) méthode pour libérer la mémoire allouée.</span><span class="sxs-lookup"><span data-stu-id="c8f33-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8f33-118">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="c8f33-118">Requirements</span></span>  
 <span data-ttu-id="c8f33-119">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8f33-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8f33-120">**En-tête :** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c8f33-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c8f33-121">**Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8f33-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8f33-122">**Versions du .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8f33-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f33-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8f33-123">See Also</span></span>  
 [<span data-ttu-id="c8f33-124">StrongNameTokenFromAssembly, méthode</span><span class="sxs-lookup"><span data-stu-id="c8f33-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="c8f33-125">ICLRStrongName, interface</span><span class="sxs-lookup"><span data-stu-id="c8f33-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

---
title: PublicKeyBlob, structure
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7577a24a023c38370f5ac1f8c471ce31409e75d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459337"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="46831-102">PublicKeyBlob, structure</span><span class="sxs-lookup"><span data-stu-id="46831-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="46831-103">Représente, en format binaire, la clé publique d’une paire de clés publique/privée.</span><span class="sxs-lookup"><span data-stu-id="46831-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46831-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="46831-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="46831-105">Membres</span><span class="sxs-lookup"><span data-stu-id="46831-105">Members</span></span>  
  
|<span data-ttu-id="46831-106">Membre</span><span class="sxs-lookup"><span data-stu-id="46831-106">Member</span></span>|<span data-ttu-id="46831-107">Description</span><span class="sxs-lookup"><span data-stu-id="46831-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="46831-108">L’identificateur de l’algorithme de signature (de type `ALG_ID`, comme défini dans WinCrypt.h) de la clé publique.</span><span class="sxs-lookup"><span data-stu-id="46831-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="46831-109">L’identificateur de l’algorithme de hachage (de type `ALG_ID`, comme défini dans WinCrypt.h) de la clé publique.</span><span class="sxs-lookup"><span data-stu-id="46831-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="46831-110">La longueur de la clé en octets.</span><span class="sxs-lookup"><span data-stu-id="46831-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="46831-111">Tableau d’octets de longueur variable qui contient la valeur de clé dans le format retourné par CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="46831-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46831-112">Notes</span><span class="sxs-lookup"><span data-stu-id="46831-112">Remarks</span></span>  
 <span data-ttu-id="46831-113">Le `PublicKeyBlob` structure est utilisée par [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)et d’autres fonctions de nom fort pour représenter la clé publique d’une paire de clés publique/privée.</span><span class="sxs-lookup"><span data-stu-id="46831-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46831-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="46831-114">Requirements</span></span>  
 <span data-ttu-id="46831-115">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46831-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46831-116">**En-tête :** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="46831-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="46831-117">**Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46831-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46831-118">**Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46831-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46831-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46831-119">See Also</span></span>  
 [<span data-ttu-id="46831-120">StrongNameGetPublicKey, fonction</span><span class="sxs-lookup"><span data-stu-id="46831-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="46831-121">StrongNameSignatureGeneration, fonction</span><span class="sxs-lookup"><span data-stu-id="46831-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="46831-122">Structures de noms forts</span><span class="sxs-lookup"><span data-stu-id="46831-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)

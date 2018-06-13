---
title: ICLRDataTarget::ReadVirtual, méthode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c9080a588b96c5b89c280a0fb407952bd580f26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404221"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="d736e-102">ICLRDataTarget::ReadVirtual, méthode</span><span class="sxs-lookup"><span data-stu-id="d736e-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="d736e-103">Lit les données à partir de l’adresse de mémoire virtuelle spécifiée dans la mémoire tampon spécifiée.</span><span class="sxs-lookup"><span data-stu-id="d736e-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d736e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d736e-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d736e-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d736e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d736e-106">[in] CLRDATA_ADDRESS qui stocke l’adresse de la mémoire virtuelle.</span><span class="sxs-lookup"><span data-stu-id="d736e-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="d736e-107">[out] Pointeur vers une mémoire tampon qui reçoit les données.</span><span class="sxs-lookup"><span data-stu-id="d736e-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="d736e-108">[in] La longueur de la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="d736e-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="d736e-109">[out] Pointeur vers le nombre d’octets retourné.</span><span class="sxs-lookup"><span data-stu-id="d736e-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d736e-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="d736e-110">Requirements</span></span>  
 <span data-ttu-id="d736e-111">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d736e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d736e-112">**En-tête :** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d736e-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d736e-113">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d736e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d736e-114">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d736e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d736e-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d736e-115">See Also</span></span>  
 [<span data-ttu-id="d736e-116">ICLRDataTarget, interface</span><span class="sxs-lookup"><span data-stu-id="d736e-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)

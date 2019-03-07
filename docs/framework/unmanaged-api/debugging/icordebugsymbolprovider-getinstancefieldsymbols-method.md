---
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols, méthode
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d149eeec545909d9d6b7413c7ad6d537c1493bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501316"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="0fdb9-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols, méthode</span><span class="sxs-lookup"><span data-stu-id="0fdb9-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="0fdb9-103">Obtient les symboles de champ d'instance qui correspondent à une signature typespec.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fdb9-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0fdb9-104">Syntax</span></span>  
  
```  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fdb9-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="0fdb9-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="0fdb9-106">[in] Nombre d'octets dans le tableau `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="0fdb9-107">[in] Tableau d'octets contenant la signature `typespec`.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="0fdb9-108">[in] Nombre de symboles demandés.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="0fdb9-109">[out] Pointeur vers le nombre de symboles récupérés par la méthode.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="0fdb9-110">[out] Un pointeur vers un [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) tableau qui contient les symboles de champ d’instance demandée.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fdb9-111">Notes</span><span class="sxs-lookup"><span data-stu-id="0fdb9-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fdb9-112">Cette méthode est uniquement disponible avec .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0fdb9-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fdb9-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="0fdb9-113">Requirements</span></span>  
 <span data-ttu-id="0fdb9-114">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fdb9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fdb9-115">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fdb9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fdb9-116">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fdb9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fdb9-117">**Versions du .NET Framework :** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fdb9-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fdb9-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0fdb9-118">See also</span></span>
- [<span data-ttu-id="0fdb9-119">GetStaticFieldSymbols, méthode</span><span class="sxs-lookup"><span data-stu-id="0fdb9-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="0fdb9-120">ICorDebugSymbolProvider, interface</span><span class="sxs-lookup"><span data-stu-id="0fdb9-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="0fdb9-121">Interfaces de débogage</span><span class="sxs-lookup"><span data-stu-id="0fdb9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

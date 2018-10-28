---
title: ISymUnmanagedENCUpdate::GetLocalVariables, méthode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a53493d666cb16fcc9b407ca3a46072afa306b97
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182474"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="2acdb-102">ISymUnmanagedENCUpdate::GetLocalVariables, méthode</span><span class="sxs-lookup"><span data-stu-id="2acdb-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="2acdb-103">Obtient les variables locales.</span><span class="sxs-lookup"><span data-stu-id="2acdb-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2acdb-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2acdb-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2acdb-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2acdb-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="2acdb-106">[in] Le jeton de métadonnées de la méthode.</span><span class="sxs-lookup"><span data-stu-id="2acdb-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="2acdb-107">[in] Un `ULONG` qui indique la taille de la `rgLocals` paramètre.</span><span class="sxs-lookup"><span data-stu-id="2acdb-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="2acdb-108">[out] Le tableau retourné [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span><span class="sxs-lookup"><span data-stu-id="2acdb-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2acdb-109">[out] Un pointeur vers un `ULONG` qui reçoit la taille de la `rgLocals` tampon nécessaire pour contenir les variables locales.</span><span class="sxs-lookup"><span data-stu-id="2acdb-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2acdb-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="2acdb-110">Return Value</span></span>  
 <span data-ttu-id="2acdb-111">S_OK si la méthode réussit ; Sinon, E_FAIL ou un autre code d’erreur.</span><span class="sxs-lookup"><span data-stu-id="2acdb-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2acdb-112">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="2acdb-112">Requirements</span></span>  
 <span data-ttu-id="2acdb-113">**En-tête :** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2acdb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2acdb-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2acdb-114">See Also</span></span>  
 [<span data-ttu-id="2acdb-115">ISymUnmanagedENCUpdate, interface</span><span class="sxs-lookup"><span data-stu-id="2acdb-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)

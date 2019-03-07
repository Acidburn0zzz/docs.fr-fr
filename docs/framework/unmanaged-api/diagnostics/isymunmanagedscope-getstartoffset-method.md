---
title: ISymUnmanagedScope::GetStartOffset, méthode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 189e72e513a06bfa545007fc9a8612a61314a520
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492660"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="5db22-102">ISymUnmanagedScope::GetStartOffset, méthode</span><span class="sxs-lookup"><span data-stu-id="5db22-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="5db22-103">Obtient l’offset de début pour cette étendue.</span><span class="sxs-lookup"><span data-stu-id="5db22-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db22-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5db22-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5db22-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5db22-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5db22-106">[out] Un pointeur vers un `ULONG32` qui contient l’offset de démarrage.</span><span class="sxs-lookup"><span data-stu-id="5db22-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5db22-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="5db22-107">Return Value</span></span>  
 <span data-ttu-id="5db22-108">S_OK si la méthode réussit ; Sinon, E_FAIL ou un autre code d’erreur.</span><span class="sxs-lookup"><span data-stu-id="5db22-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5db22-109">Spécifications</span><span class="sxs-lookup"><span data-stu-id="5db22-109">Requirements</span></span>  
 <span data-ttu-id="5db22-110">**En-tête :** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5db22-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db22-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5db22-111">See also</span></span>
- [<span data-ttu-id="5db22-112">ISymUnmanagedScope, interface</span><span class="sxs-lookup"><span data-stu-id="5db22-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="5db22-113">GetEndOffset, méthode</span><span class="sxs-lookup"><span data-stu-id="5db22-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)

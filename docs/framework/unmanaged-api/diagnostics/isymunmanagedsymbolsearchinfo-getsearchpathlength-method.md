---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength, méthode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0672ee0e47e28afb42a533d44e83e3807b08d659
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744530"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="cd5c1-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength, méthode</span><span class="sxs-lookup"><span data-stu-id="cd5c1-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="cd5c1-103">Obtient la longueur de chemin d’accès de recherche.</span><span class="sxs-lookup"><span data-stu-id="cd5c1-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd5c1-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cd5c1-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd5c1-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="cd5c1-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="cd5c1-106">[out] Un pointeur vers un `ULONG32` qui reçoit la taille, en caractères, de la mémoire tampon requise pour contenir la longueur de chemin d’accès de recherche.</span><span class="sxs-lookup"><span data-stu-id="cd5c1-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd5c1-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="cd5c1-107">Return Value</span></span>  
 <span data-ttu-id="cd5c1-108">S_OK si la méthode réussit ; Sinon, E_FAIL ou un autre code d’erreur.</span><span class="sxs-lookup"><span data-stu-id="cd5c1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd5c1-109">Spécifications</span><span class="sxs-lookup"><span data-stu-id="cd5c1-109">Requirements</span></span>  
 <span data-ttu-id="cd5c1-110">**En-tête :** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cd5c1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd5c1-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cd5c1-111">See also</span></span>
- [<span data-ttu-id="cd5c1-112">ISymUnmanagedSymbolSearchInfo, interface</span><span class="sxs-lookup"><span data-stu-id="cd5c1-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

---
title: "ISymUnmanagedMethod::GetScopeFromOffset, méthode"
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
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 890fd702bc2edb5714dc9c91a618c6420a11a27a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="329d3-102">ISymUnmanagedMethod::GetScopeFromOffset, méthode</span><span class="sxs-lookup"><span data-stu-id="329d3-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="329d3-103">Obtient la portée lexicale la plus englobante dans cette méthode qui englobe l’offset donné.</span><span class="sxs-lookup"><span data-stu-id="329d3-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="329d3-104">Cela permet de démarrer la recherche de variables locales.</span><span class="sxs-lookup"><span data-stu-id="329d3-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329d3-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="329d3-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="329d3-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="329d3-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="329d3-107">[in] Un `ULONG` qui contient le décalage.</span><span class="sxs-lookup"><span data-stu-id="329d3-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="329d3-108">[out] Un pointeur qui est défini à le [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="329d3-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="329d3-109">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="329d3-109">Return Value</span></span>  
 <span data-ttu-id="329d3-110">S_OK si la méthode réussit ; Sinon, E_FAIL ou un autre code d’erreur.</span><span class="sxs-lookup"><span data-stu-id="329d3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="329d3-111">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="329d3-111">Requirements</span></span>  
 <span data-ttu-id="329d3-112">**En-tête :** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="329d3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329d3-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="329d3-113">See Also</span></span>  
 [<span data-ttu-id="329d3-114">ISymUnmanagedMethod, interface</span><span class="sxs-lookup"><span data-stu-id="329d3-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

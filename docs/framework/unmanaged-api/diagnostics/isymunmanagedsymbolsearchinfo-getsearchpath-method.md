---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath, méthode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c490ee97a1a74cc6fe29a5b0bbece366db6025a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428344"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="53307-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath, méthode</span><span class="sxs-lookup"><span data-stu-id="53307-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="53307-103">Obtient le chemin de recherche.</span><span class="sxs-lookup"><span data-stu-id="53307-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53307-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="53307-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53307-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="53307-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="53307-106">[out] Un pointeur vers un `ULONG32` qui reçoit la taille, en caractères, de la mémoire tampon requise pour contenir le chemin de recherche.</span><span class="sxs-lookup"><span data-stu-id="53307-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53307-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="53307-107">Return Value</span></span>  
 <span data-ttu-id="53307-108">S_OK si la méthode réussit ; Sinon, E_FAIL ou un autre code d’erreur.</span><span class="sxs-lookup"><span data-stu-id="53307-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53307-109">Spécifications</span><span class="sxs-lookup"><span data-stu-id="53307-109">Requirements</span></span>  
 <span data-ttu-id="53307-110">**En-tête :** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="53307-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53307-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53307-111">See Also</span></span>  
 [<span data-ttu-id="53307-112">ISymUnmanagedSymbolSearchInfo, interface</span><span class="sxs-lookup"><span data-stu-id="53307-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

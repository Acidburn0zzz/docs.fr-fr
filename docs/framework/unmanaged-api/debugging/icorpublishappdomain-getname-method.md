---
title: ICorPublishAppDomain::GetName, méthode
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 796f8ea42cc5cbe13729f7b92e15bc214d62734d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423856"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="b8480-102">ICorPublishAppDomain::GetName, méthode</span><span class="sxs-lookup"><span data-stu-id="b8480-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="b8480-103">Obtient le nom du domaine d’application qui est représenté par ce [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b8480-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8480-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b8480-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8480-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b8480-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b8480-106">[in] Taille du tableau `szName`.</span><span class="sxs-lookup"><span data-stu-id="b8480-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b8480-107">[out] Un pointeur vers le nombre de caractères larges, y compris le caractère null, retourné dans le `szName` tableau.</span><span class="sxs-lookup"><span data-stu-id="b8480-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="b8480-108">[out] Tableau dans lequel stocker le nom.</span><span class="sxs-lookup"><span data-stu-id="b8480-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8480-109">Notes</span><span class="sxs-lookup"><span data-stu-id="b8480-109">Remarks</span></span>  
 <span data-ttu-id="b8480-110">Si `szName` n’est pas null, le `GetName` méthode copie jusqu'à `cchName` caractères (y compris la marque de fin null) dans `szName`.</span><span class="sxs-lookup"><span data-stu-id="b8480-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="b8480-111">Si une valeur non null est retournée dans `pcchName`, le nombre réel de caractères dans le nom (y compris la marque de fin null) est stocké dans le `szName` tableau.</span><span class="sxs-lookup"><span data-stu-id="b8480-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="b8480-112">Le `GetName` méthode retourne un HRESULT S_OK, quelle que soit le nombre de caractères ont été copié.</span><span class="sxs-lookup"><span data-stu-id="b8480-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8480-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b8480-113">Requirements</span></span>  
 <span data-ttu-id="b8480-114">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8480-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8480-115">**En-tête :** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b8480-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b8480-116">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8480-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8480-117">**Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8480-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8480-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8480-118">See Also</span></span>  
 [<span data-ttu-id="b8480-119">ICorPublishAppDomain, interface</span><span class="sxs-lookup"><span data-stu-id="b8480-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)

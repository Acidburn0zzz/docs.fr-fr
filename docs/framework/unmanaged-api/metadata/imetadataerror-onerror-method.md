---
title: IMetaDataError::OnError, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ed9e097dccd0fcb81ea9023cc9b84906589ccb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446256"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="d9f1e-102">IMetaDataError::OnError, méthode</span><span class="sxs-lookup"><span data-stu-id="d9f1e-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="d9f1e-103">Fournit une notification des erreurs qui se produisent pendant la fusion des métadonnées.</span><span class="sxs-lookup"><span data-stu-id="d9f1e-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f1e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d9f1e-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9f1e-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d9f1e-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="d9f1e-106">[in] La valeur d’erreur HRESULT retourné à la méthode appelante.</span><span class="sxs-lookup"><span data-stu-id="d9f1e-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="d9f1e-107">[in] Le jeton de métadonnées de l’objet de code qui était en cours de fusion lorsque l’erreur s’est produite.</span><span class="sxs-lookup"><span data-stu-id="d9f1e-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9f1e-108">Spécifications</span><span class="sxs-lookup"><span data-stu-id="d9f1e-108">Requirements</span></span>  
 <span data-ttu-id="d9f1e-109">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9f1e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9f1e-110">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9f1e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9f1e-111">**Bibliothèque :** utilisé en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9f1e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9f1e-112">**Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9f1e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f1e-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9f1e-113">See Also</span></span>  
 [<span data-ttu-id="d9f1e-114">IMetaDataError, interface</span><span class="sxs-lookup"><span data-stu-id="d9f1e-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)

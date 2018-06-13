---
title: IMetaDataEmit::SetFieldProps, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6a2c38340614e633de4049515b38cb387031739b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446034"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="5eeb8-102">IMetaDataEmit::SetFieldProps, méthode</span><span class="sxs-lookup"><span data-stu-id="5eeb8-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="5eeb8-103">Définit ou met à jour la valeur par défaut pour le champ référencé par le jeton de champ spécifié.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eeb8-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5eeb8-104">Syntax</span></span>  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5eeb8-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5eeb8-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="5eeb8-106">[in] Le jeton pour le champ cible.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="5eeb8-107">[in] Attributs de champ.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-107">[in] Field attributes.</span></span> <span data-ttu-id="5eeb8-108">Il s’agit d’un masque de bits de `CorFieldAttr` valeurs.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="5eeb8-109">[in] Le `ELEMENT_TYPE_` *\** pour la valeur de constante.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="5eeb8-110">Il s’agit d’un `CorElementType` valeur.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="5eeb8-111">Si une constante n’est pas définie, définissez cette valeur sur `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5eeb8-112">[in] La valeur de constante pour le champ.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="5eeb8-113">[in] La taille, en caractères Unicode de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="5eeb8-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eeb8-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="5eeb8-114">Requirements</span></span>  
 <span data-ttu-id="5eeb8-115">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5eeb8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eeb8-116">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5eeb8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5eeb8-117">**Bibliothèque :** utilisé en tant que ressource dans MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5eeb8-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5eeb8-118">**Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eeb8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eeb8-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5eeb8-119">See Also</span></span>  
 [<span data-ttu-id="5eeb8-120">IMetaDataEmit, interface</span><span class="sxs-lookup"><span data-stu-id="5eeb8-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5eeb8-121">IMetaDataEmit2, interface</span><span class="sxs-lookup"><span data-stu-id="5eeb8-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

---
title: IMetaDataImport2::EnumGenericParamConstraints, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e7a51d1ddf7a5a65ce8713161c53c1c54a5d8861
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617692"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="932b7-102">IMetaDataImport2::EnumGenericParamConstraints, méthode</span><span class="sxs-lookup"><span data-stu-id="932b7-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="932b7-103">Obtient un énumérateur pour un tableau de contraintes de paramètre générique associé au paramètre générique représenté par le jeton spécifié.</span><span class="sxs-lookup"><span data-stu-id="932b7-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="932b7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="932b7-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="932b7-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="932b7-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="932b7-106">[in, out] Pointeur vers l’énumérateur.</span><span class="sxs-lookup"><span data-stu-id="932b7-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="932b7-107">[in]   Un jeton qui représente le paramètre générique dont les contraintes doivent être énumérés.</span><span class="sxs-lookup"><span data-stu-id="932b7-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="932b7-108">[out] Tableau des contraintes de paramètre générique à énumérer.</span><span class="sxs-lookup"><span data-stu-id="932b7-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="932b7-109">[in]   Le nombre maximal demandé de jetons à placer dans `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="932b7-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="932b7-110">[out] Un pointeur vers le nombre de jetons placés dans `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="932b7-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="932b7-111">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="932b7-111">Return Value</span></span>  
  
|<span data-ttu-id="932b7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="932b7-112">HRESULT</span></span>|<span data-ttu-id="932b7-113">Description</span><span class="sxs-lookup"><span data-stu-id="932b7-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="932b7-114">`EnumGenericParameterConstraints` retourné avec succès.</span><span class="sxs-lookup"><span data-stu-id="932b7-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="932b7-115">`phEnum` ne contient aucun élément de membre.</span><span class="sxs-lookup"><span data-stu-id="932b7-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="932b7-116">Dans ce cas, `pcGenericParameterConstraints` est définie sur 0 (zéro).</span><span class="sxs-lookup"><span data-stu-id="932b7-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="932b7-117">Spécifications</span><span class="sxs-lookup"><span data-stu-id="932b7-117">Requirements</span></span>  
 <span data-ttu-id="932b7-118">**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="932b7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="932b7-119">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="932b7-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="932b7-120">**Bibliothèque :** Utilisé en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="932b7-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="932b7-121">**Versions du .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="932b7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="932b7-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="932b7-122">See also</span></span>
- [<span data-ttu-id="932b7-123">IMetaDataImport2, interface</span><span class="sxs-lookup"><span data-stu-id="932b7-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="932b7-124">IMetaDataImport, interface</span><span class="sxs-lookup"><span data-stu-id="932b7-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

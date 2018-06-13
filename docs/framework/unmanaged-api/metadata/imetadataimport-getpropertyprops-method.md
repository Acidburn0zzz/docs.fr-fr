---
title: IMetaDataImport::GetPropertyProps, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7312cbd31a04365801b0380d5914966f36679560
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449453"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="9a1d6-102">IMetaDataImport::GetPropertyProps, méthode</span><span class="sxs-lookup"><span data-stu-id="9a1d6-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="9a1d6-103">Obtient les métadonnées pour la propriété représentée par le jeton spécifié.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a1d6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9a1d6-104">Syntax</span></span>  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a1d6-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="9a1d6-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="9a1d6-106">[in] Un jeton qui représente la propriété à retourner les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="9a1d6-107">[out] Pointeur vers le jeton TypeDef qui représente le type qui implémente la propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="9a1d6-108">[out] Une mémoire tampon pour contenir le nom de propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="9a1d6-109">[in] La taille en caractères larges de `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="9a1d6-110">[out] Le nombre de caractères étendus retournés dans `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="9a1d6-111">[out] Pointeur vers les indicateurs d’attribut appliquée à la propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="9a1d6-112">Cette valeur est un masque de bits de le [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) énumération.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="9a1d6-113">[out] Pointeur vers la signature de métadonnées de la propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="9a1d6-114">[out] Le nombre d’octets retournés dans `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="9a1d6-115">[out] Indicateur qui spécifie le type de la constante qui est la valeur par défaut de la propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="9a1d6-116">Cette valeur provient de l’énumération CorElementType.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="9a1d6-117">[out] Un pointeur vers les octets qui stockent la valeur par défaut de cette propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="9a1d6-118">[out] La taille en caractères larges de `ppDefaultValue`si `pdwCPlusTypeFlag` a la valeur ELEMENT_TYPE_STRING ; sinon, cette valeur n’est pas pertinente.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="9a1d6-119">Dans ce cas, la longueur de `ppDefaultValue` est déduit du type spécifié par `pdwCPlusTypeFlag`.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="9a1d6-120">[out] Pointeur vers le jeton MethodDef qui représente la méthode d’accesseur set pour la propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="9a1d6-121">[out] Pointeur vers le jeton MethodDef qui représente la méthode d’accesseur get de la propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="9a1d6-122">[out] Tableau de jetons MethodDef représentant des autres méthodes associées à la propriété.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9a1d6-123">[in] Taille maximale du tableau `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="9a1d6-124">Si vous ne fournissez pas un tableau assez grand pour contenir toutes les méthodes, elles sont ignorées sans avertissement.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="9a1d6-125">[out] Le nombre de jetons MethodDef retournés dans `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="9a1d6-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a1d6-126">Spécifications</span><span class="sxs-lookup"><span data-stu-id="9a1d6-126">Requirements</span></span>  
 <span data-ttu-id="9a1d6-127">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a1d6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a1d6-128">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9a1d6-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a1d6-129">**Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a1d6-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a1d6-130">**Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a1d6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1d6-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a1d6-131">See Also</span></span>  
 [<span data-ttu-id="9a1d6-132">IMetaDataImport, interface</span><span class="sxs-lookup"><span data-stu-id="9a1d6-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9a1d6-133">IMetaDataImport2, interface</span><span class="sxs-lookup"><span data-stu-id="9a1d6-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

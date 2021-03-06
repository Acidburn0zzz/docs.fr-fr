---
title: IMetaDataAssemblyImport::GetExportedTypeProps, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91b1e4469f07954dc433769911c78d72bb3c36cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096148"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps, méthode
Obtient le jeu de propriétés du type exporté avec la signature de métadonnées spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Paramètres  
 `mdct`  
 [in] Un `mdExportedType` jeton de métadonnées qui représente le type exporté.  
  
 `szName`  
 [out] Le nom du type exporté.  
  
 `cchName`  
 [in] La taille, en caractères larges, de `szName`.  
  
 `pchName`  
 [out] Le nombre de caractères larges réellement retournés dans `szName`  
  
 `ptkImplementation`  
 [out] Un `mdFile`, `mdAssemblyRef`, ou `mdExportedType` jeton de métadonnées qui contienne ou autorise l’accès aux propriétés du type exporté.  
  
 `ptkTypeDef`  
 [out] Un pointeur vers un `mdTypeDef` jeton qui représente un type dans le fichier.  
  
 `pdwExportedTypeFlags`  
 [out] Pointeur vers les indicateurs qui décrivent les métadonnées appliquées pour le type exporté. La valeur des indicateurs peut être une ou plusieurs [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valeurs.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Cor.h  
  
 **Bibliothèque :** Utilisé en tant que ressource dans MsCorEE.dll  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [IMetaDataAssemblyImport, interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

---
title: IMetaDataImport::GetTypeRefProps, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 808c48bb0c516c51f39a8424acf49869b1bc9208
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165228"
---
# <a name="imetadataimportgettyperefprops-method"></a>IMetaDataImport::GetTypeRefProps, méthode
Obtient les métadonnées associées à la <xref:System.Type> référencé par le jeton TypeRef spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a>Paramètres  
 `tr`  
 [in] Le jeton TypeRef qui représente le type à retourner les métadonnées.  
  
 `ptkResolutionScope`  
 [out] Pointeur vers la portée dans laquelle la référence est faite. Cette valeur est un jeton AssemblyRef ou ModuleRef.  
  
 `szName`  
 [out] Une mémoire tampon contenant le nom de type.  
  
 `cchName`  
 [in] La taille demandée en caractères larges de `szName`.  
  
 `pchName`  
 [out] La taille retournée en caractères larges de `szName`.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Cor.h  
  
 **Bibliothèque :** Inclus en tant que ressource dans MsCorEE.dll  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [IMetaDataImport, interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2, interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

---
title: IMetaDataImport::GetFieldProps, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04b6c04868efff31253b2d723c5783060382212b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448971"
---
# <a name="imetadataimportgetfieldprops-method"></a>IMetaDataImport::GetFieldProps, méthode
Obtient les métadonnées associées au champ référencé par le jeton FieldDef spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `mb`  
 [in] Jeton FieldDef qui représente le champ pour lequel obtenir les métadonnées associées.  
  
 `pClass`  
 [out] Pointeur vers un jeton TypeDef qui représente le type de la classe à laquelle appartient le champ.  
  
 `szField`  
 [out] Le nom du champ.  
  
 `cchField`  
 [in] La taille en caractères larges de la mémoire tampon pour *szField*.  
  
 `pchField`  
 [out] La taille réelle de la mémoire tampon retournée.  
  
 `pdwAttr`  
 [out] Indicateurs associés aux métadonnées du champ.  
  
 `ppvSigBlob`  
 [in] Pointeur vers la valeur de métadonnées binaires qui décrit le champ.  
  
 `pcbSigBlob`  
 [out] La taille en octets de `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Indicateur qui spécifie le type de valeur du champ.  
  
 `ppValue`  
 [out] Valeur de constante pour le champ.  
  
 `pcchValue`  
 [out] La taille en caractères de `ppValue`, ou zéro si aucune chaîne n’existe.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Cor.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [IMetaDataImport, interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2, interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

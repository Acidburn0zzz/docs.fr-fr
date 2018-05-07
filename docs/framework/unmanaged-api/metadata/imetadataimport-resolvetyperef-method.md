---
title: IMetaDataImport::ResolveTypeRef, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 106ef520f64233323cbb3f26cb3efdee152559b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef, méthode
Résout un <xref:System.Type> référence représenté par le jeton TypeRef spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `tr`  
 [in] Le jeton de métadonnées TypeRef pour retourner les informations de type référencé.  
  
 `riid`  
 [in] IID de l’interface à retourner dans `ppIScope`. En règle générale, il correspond à IID_IMetaDataImport.  
  
 `ppIScope`  
 [out] Interface avec l’étendue du module dans lequel le type référencé est défini.  
  
 `ptd`  
 [out] Pointeur vers un jeton TypeDef qui représente le type référencé.  
  
## <a name="remarks"></a>Notes  
  
> [!IMPORTANT]
>  N’utilisez pas cette méthode si plusieurs domaines d’application sont chargés. La méthode ne respecte pas les limites du domaine d’application. Si plusieurs versions d’un assembly sont chargées et qu’ils contiennent le même type avec le même espace de noms, la méthode retourne l’étendue du module du premier type qu’il trouve.  
  
 Le `ResolveTypeRef` méthode recherche la définition de type dans d’autres modules. Si la définition de type est trouvée, `ResolveTypeRef` retourne une interface pour cette portée de module ainsi que le jeton TypeDef pour le type.  
  
 Si la référence de type pour être résolu a une portée de résolution AssemblyRef, la `ResolveTypeRef` méthode recherche une correspondance uniquement dans les portées de métadonnées qui ont déjà été ouverte avec des appels à la [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)méthode ou la [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) (méthode). C’est parce que `ResolveTypeRef` ne peut pas déterminer à partir d’uniquement l’étendue AssemblyRef où sur le disque ou dans le global assembly cache est stocké l’assembly.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Cor.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [IMetaDataImport, interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2, interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)

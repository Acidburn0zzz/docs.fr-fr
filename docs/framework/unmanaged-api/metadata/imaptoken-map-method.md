---
title: IMapToken::Map, méthode
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a85dc586b0c08fabdd34c018e82314c9003eeded
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171006"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map, méthode
Mappe une relation entre les assemblys à l’aide de signatures de métadonnées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Paramètres  
 `tkImp`  
 [in] Le jeton de métadonnées qui représente l’objet de code importé.  
  
 `tkEmit`  
 [in] Le jeton de métadonnées qui représente l’objet de code émis.  
  
## <a name="remarks"></a>Notes  
 Lorsque le jeton remapper se produit pendant une fusion, le jeton d’origine est étendu dans la portée de métadonnées importées (source) et le nouveau jeton est limité dans la portée de métadonnées émise (cible).  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Cor.h  
  
 **Bibliothèque :** Utilisé en tant que ressource dans MsCorEE.dll  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [IMapToken, interface](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)

---
title: IDENTITY_ATTRIBUTE, structure
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb970d31fb5158adc7dbcbb7cc0175cc91c83c8c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107339"
---
# <a name="identityattribute-structure"></a>IDENTITY_ATTRIBUTE, structure
Contient des informations d’attribut de métadonnées sur une [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>Membres  
  
|Membre|Description|  
|------------|-----------------|  
|`pszNamespace`|Un pointeur vers une chaîne de caractères se terminant par null qui contient l’espace de noms de l’attribut est dans.|  
|`pszName`|Un pointeur vers une chaîne de caractères se terminant par null qui contient le nom de l’attribut.|  
|`pszValue`|Un pointeur vers une chaîne de caractères se terminant par null qui contient la valeur de l’attribut.|  
  
## <a name="remarks"></a>Notes  
 Le `IDENTITY_ATTRIBUTE` structure contient trois pointeurs vers des chaînes de caractères se terminant par null. Ces trois chaînes décrivent un attribut.  
  
 Une instance d’un `IDENTITY_ATTRIBUTE` structure est associée à une instance d’un [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure. Le `IDENTITY_ATTRIBUTE` structure contient les chaînes réelles et correspondants `IDENTITY_ATTRIBUTE_BLOB` structure répertorie les offsets pour les trois chaînes répertoriées dans le `IDENTITY_ATTRIBUTE` structure.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Isolation.h  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [IDefinitionIdentity, interface](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [IDENTITY_ATTRIBUTE_BLOB, structure](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [Structures de fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)

---
title: ICorDebugObjectValue::GetFieldValue, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8778edf9ac6e32d5dab3a53a6d9cc643a8df13b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107911"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue, méthode
Obtient la valeur du champ spécifié de la classe spécifiée pour la valeur de cet objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Paramètres  
 `pClass`  
 [in] Pointeur vers un objet « ICorDebugClass » qui représente la classe pour laquelle obtenir la valeur du champ.  
  
 `fieldDef`  
 [in] Un `mdFieldDef` jeton qui référence les métadonnées décrivant le champ.  
  
 `ppValue`  
 [out] Pointeur vers un objet « ICorDebugValue » qui représente la valeur du champ spécifié.  
  
## <a name="remarks"></a>Notes  
 La classe spécifiée dans le `pClass` paramètre, doit être dans la hiérarchie de classe de la valeur d’objet et le champ doit être un champ de cette classe.  
  
 Le `GetFieldValue` méthode réussira quand même pour les objets génériques et les classes génériques. Par exemple, si MonDictionnaire\<V > hérite de dictionnaire\<string, V >, et la valeur de l’objet est de type MonDictionnaire\<int32 >, en passant le `ICorDebugClass` objet de dictionnaire\<K, V > sera obtenir correctement un champ de dictionnaire\<string, int32 >.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

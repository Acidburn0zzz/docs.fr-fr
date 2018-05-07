---
title: ICorDebugModule::GetMetaDataInterface, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fef23f2b128b1e5393c5104b6e33758882b34882
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>ICorDebugModule::GetMetaDataInterface, méthode
Obtient un objet d’interface de métadonnées qui peut être utilisé pour examiner les métadonnées pour le module.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `riid`  
 [in] L’ID de référence qui spécifie l’interface de métadonnées.  
  
 `ppObj`  
 [out] Un pointeur vers l’adresse d’un `T:IUnknown` objet qui est un de le [interfaces de métadonnées](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).  
  
## <a name="remarks"></a>Notes  
 Le débogueur peut utiliser le `GetMetaDataInterface` méthode pour effectuer une copie des métadonnées d’origine pour un module, qu’il doit effectuer pour pouvoir modifier ce module. Le débogueur appelle `GetMetaDataInterface` pour obtenir un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) objet d’interface pour le module, puis appelle [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) pour enregistrer une copie de métadonnées du module dans la mémoire.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Métadonnées](../../../../docs/framework/unmanaged-api/metadata/index.md)

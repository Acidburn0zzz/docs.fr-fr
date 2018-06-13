---
title: CorDebugEHClause, structure
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40820a805310786eeb0effd7c5284c1a70a6e70b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407598"
---
# <a name="cordebugehclause-structure"></a>CorDebugEHClause, structure
[Pris en charge dans .NET Framework 4.5.2 et ultérieur]  
  
 Représente une clause de gestion des exceptions pour un bloc spécifié de code de langage intermédiaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a>Membres  
  
|Membre|Description|  
|------------|-----------------|  
|`Flags`|Un champ de bits qui décrit les informations de l'exception dans la clause de gestion des exceptions. Pour plus d'informations, consultez la section Remarques.|  
|`TryOffset`|Le décalage en octets du bloc `try` à partir du début du corps de la méthode.|  
|`TryLength`|La longueur en octets du bloc `try`.|  
|`HandlerOffset`|L'emplacement du gestionnaire pour ce bloc `try`.|  
|`HandlerLength`|La taille du code du gestionnaire en octets.|  
|`ClassToken`|Le jeton de métadonnées pour un gestionnaire d'exceptions basé sur les types.|  
|`FilterOffset`|Le décalage en octets depuis le début du corps de la méthode pour un gestionnaire d'exceptions basé sur les filtres.|  
  
## <a name="remarks"></a>Notes  
 Un tableau de `CoreDebugEHClause` valeurs est retourné par la [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) (méthode).  
  
 Les informations de la clause du gestionnaire d'exceptions sont définies par la spécification CLI. Pour plus d’informations, consultez [Standard ECMA-355 : Common Language Infrastructure (CLI), 6th Edition](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 Le champ `flags` peut contenir les indicateurs suivants. Notez qu'ils ne sont pas définis dans CorDebug.idl ou CorDebug.h.  
  
|Indicateur|Valeur|Description|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|0x00000000|Une clause d'exception typée.|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|0x00000001|Une clause de filtre et de gestionnaire d'exceptions.|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|0x00000002|Une clause `finally`.|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|0x00000004|Une clause fault (une clause `finally` qui est appelée seulement quand une exception est levée).|  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorDebug.idl, CorDebug.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [GetEHClauses, méthode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)  
 [Structures de débogage](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

---
title: EnumImportTypes, méthode
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355738"
---
# <a name="enumimporttypes-method"></a>EnumImportTypes, méthode

Énumère chaque type dans chaque étendue.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a>Paramètres

`hEnum`\
Handle pour l’énumérateur.

`dwMax`\
Nombre maximal de types à récupérer.

`aTypeDefs`\
Reçoit des jetons de type, ne pouvant excéder `dwMax`.

`pdwCount`\
Reçoit le nombre réel de type dans `aTypeDefs`.

## <a name="return-value"></a>Valeur de retour

Retourne S_OK si la méthode réussit.

## <a name="requirements"></a>Spécifications

Nécessite alink.h

## <a name="see-also"></a>Voir aussi

- [IALink, interface](ialink-interface.md)
- [IALink2, interface](ialink2-interface.md)
- [API ALink](index.md)
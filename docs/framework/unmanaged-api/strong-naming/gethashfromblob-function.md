---
title: GetHashFromBlob, fonction
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352072"
---
# <a name="gethashfromblob-function"></a>GetHashFromBlob, fonction

Obtient un hachage de l’assembly à l’adresse mémoire spécifiée, à l’aide de l’algorithme de hachage spécifié.

Cette fonction a été déconseillée. Utilisez le [ICLRStrongName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) méthode à la place.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>Paramètres

`pbBlob`\
[in] Pointeur vers l’adresse du bloc de mémoire à hacher.

`cchBlob`\
[in] La longueur, en octets, du bloc de mémoire.

`piHashAlg`\
[in, out] Constante qui spécifie l’algorithme de hachage. Utilisez zéro pour l’algorithme par défaut.

`pbHash`\
[out] La mémoire tampon de hachage retournée.

`cchHash`\
[in] La taille maximale demandée de `pbHash`.

`pchHash`\
[out] La taille, en octets, de retourné `pbHash`.

## <a name="requirements"></a>Spécifications

**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).

**En-tête :** StrongName.h

**Bibliothèque :** Inclus en tant que ressource dans MsCorEE.dll

**Versions du .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Voir aussi

- [GetHashFromBlob, méthode](../hosting/iclrstrongname-gethashfromblob-method.md)
- [ICLRStrongName, interface](../hosting/iclrstrongname-interface.md)
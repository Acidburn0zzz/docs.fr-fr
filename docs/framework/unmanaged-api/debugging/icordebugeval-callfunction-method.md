---
title: ICorDebugEval::CallFunction, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66e51dc15f7d44ede26634571fa04c58e9735694
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364149"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction, méthode

Définit un appel à la fonction spécifiée.

Cette méthode est obsolète dans le .NET Framework version 2.0. Utilisez [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) à la place.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a>Paramètres

`pFunction`\
[in] Pointeur vers un objet ICorDebugFunction qui spécifie la fonction à appeler.

`nArgs`\
[in] Le nombre d’arguments pour la fonction.

`ppArgs`\
[in] Tableau de pointeurs, chacun d’eux pointe vers un objet ICorDebugValue qui spécifie un argument à passer à la fonction.

## <a name="remarks"></a>Notes

Si la fonction est virtuelle, `CallFunction` effectuera dispatch virtuel. Si la fonction est dans un domaine d’application différent, une transition se produit tant que tous les arguments sont également dans ce domaine d’application.

## <a name="requirements"></a>Spécifications

**Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).

**En-tête :** CorDebug.idl, CorDebug.h

**Bibliothèque :** CorGuids.lib

**Versions du .NET framework :** 1.1, 1.0

## <a name="see-also"></a>Voir aussi

- [CallParameterizedFunction, méthode](icordebugeval2-callparameterizedfunction-method.md)
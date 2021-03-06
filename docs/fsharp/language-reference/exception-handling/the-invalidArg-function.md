---
title: 'Exceptions : invalidArg (fonction)'
description: Découvrez comment la F# « invalidArg » fonction génère une exception d’argument.
ms.date: 05/16/2016
ms.openlocfilehash: 7fd8d48b80970dbbafc0c23a478b4ccf3490f3ee
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613334"
---
# <a name="exceptions-the-invalidarg-function"></a>Exceptions : invalidArg (fonction)

Le `invalidArg` fonction génère une exception d’argument.

## <a name="syntax"></a>Syntaxe

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Notes

Le nom de paramètre dans la syntaxe précédente est une chaîne avec le nom du paramètre dont l’argument n’est pas valide. Le *chaîne du message d’erreur* est une chaîne littérale ou une valeur de type `string`. Il devient le `Message` propriété de l’objet exception.

L’exception générée par `invalidArg` est un `System.ArgumentException` exception. Le code suivant illustre l’utilisation de `invalidArg` pour lever une exception.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

La sortie est la suivante, suivie d’une trace de pile (non illustrée).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Voir aussi

- [Gestion des exceptions](index.md)
- [Types d'exceptions](exception-types.md)
- [Exceptions : Le `try...with` Expression](the-try-with-expression.md)
- [Exceptions : Le `try...finally` Expression](the-try-finally-expression.md)
- [Exceptions : fonction `raise`](the-raise-function.md)
- [Exceptions : Le `failwith` (fonction)](the-failwith-function.md)
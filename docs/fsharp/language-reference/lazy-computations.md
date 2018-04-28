---
title: Calculs tardifs (F#)
description: 'Découvrez comment F # tardifs peuvent améliorer les performances de vos applications et bibliothèques.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 72dc5a14a845b52ae2512314d730516ca0cf4b9d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="lazy-computations"></a>Calculs tardifs

*Calculs tardifs* sont des calculs qui ne sont pas évalués immédiatement, mais sont évaluées à la place lorsque le résultat est nécessaire. Cela peut aider à améliorer les performances de votre code.

## <a name="syntax"></a>Syntaxe

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Notes

Dans la syntaxe précédente, *expression* est un code qui est évalué uniquement lorsqu’un résultat est requis, et *identificateur* est une valeur qui stocke le résultat. La valeur est de type [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), où le type réel qui est utilisé pour `'T` est déterminé à partir du résultat de l’expression.

Calculs tardifs permettent d’améliorer les performances en limitant l’exécution d’un calcul aux seules situations dans lesquelles un résultat est nécessaire.

Pour forcer l’exécution du calcul, vous appelez la méthode `Force`. `Force` entraîne l’exécution à effectuer qu’une seule fois. Les appels suivants à `Force` le même résultat, mais n’exécutent pas le code de retour.

Le code suivant illustre l’utilisation du calcul tardif et l’utilisation de `Force`. Dans ce code, le type de `result` est `Lazy<int>`et le `Force` méthode retourne un `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

L’évaluation différée, mais pas les `Lazy` type, est également utilisé pour les séquences. Pour plus d’informations, consultez [séquences](sequences.md).

## <a name="see-also"></a>Voir aussi

[Informations de référence du langage F#](index.md)

[LazyExtensions (module)](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)

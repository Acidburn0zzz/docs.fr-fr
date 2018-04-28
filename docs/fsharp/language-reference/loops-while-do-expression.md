---
title: 'Boucles : expression while...do (F#)'
description: Voir comment l’instruction while... procédez comme expression est utilisée pour effectuer une exécution itérative (boucle) lorsqu’une condition de test spécifié a la valeur true.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 847f99faab42c8805bd788e42e3f24ad6369ba52
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="loops-whiledo-expression"></a>Boucles : expression while...do

Le `while...do` expression est utilisée pour effectuer une exécution itérative (boucle) lorsqu’une condition de test spécifié a la valeur true.


## <a name="syntax"></a>Syntaxe

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Notes
Le *test-expression* est évaluée ; si elle est `true`, le *expression de corps* est exécuté et l’expression de test est réévaluée. Le *expression de corps* doit avoir un type `unit`. Si l’expression de test est `false`, l’itération se termine.

L’exemple suivant illustre l’utilisation de la `while...do` expression.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

La sortie du code précédent est un flux de nombres aléatoires compris entre 1 et 20, le dernier est 10.

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
Vous pouvez utiliser `while...do` dans les expressions de séquence et autres expressions de calcul, auquel cas une version personnalisée de la `while...do` expression est utilisée. Pour plus d’informations, consultez [séquences](sequences.md), [Workflows asynchrones](asynchronous-workflows.md), et [Expressions de calcul](computation-expressions.md).


## <a name="see-also"></a>Voir aussi
[Informations de référence du langage F#](index.md)

[Boucles : expression `for...in`](loops-for-in-expression.md)

[Boucles : expression `for...to`](loops-for-to-expression.md)

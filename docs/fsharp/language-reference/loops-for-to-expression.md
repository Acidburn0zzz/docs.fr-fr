---
title: 'Boucles : expression for...to (F#)'
description: 'Voir comment la boucle for) (F #.. à l’expression est utilisé pour itérer au sein d’une boucle sur une plage de valeurs d’une variable de boucle.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 95a8960d71c82c01118d2e71479fc0ec5298a02b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forto-expression"></a>Boucles : expression for...to

Le `for...to` expression est utilisée pour itérer au sein d’une boucle sur une plage de valeurs d’une variable de boucle.


## <a name="syntax"></a>Syntaxe

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Notes
Le type de l’identificateur est déduit du type de la *Démarrer* et *Terminer* expressions. Types pour ces expressions doivent être des entiers 32 bits.

Bien que techniquement d’une expression, `for...to` plus à une instruction traditionnelle dans un langage de programmation impérative. Le type de retour pour la *expression de corps* doit être `unit`. Les exemples suivants illustrent différentes utilisations de la `for...to` expression.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

La sortie du code précédent est la suivante.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Voir aussi
[Informations de référence du langage F#](index.md)

[Boucles : expression `for...in`](loops-for-in-expression.md)

[Boucles : expression `while...do`](loops-while-do-expression.md)

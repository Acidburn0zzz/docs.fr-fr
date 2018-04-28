---
title: 'Fonctions récursives : mot clé rec (F#)'
description: "Découvrez comment le mot clé F # 'rec' est utilisé avec le mot clé 'let' pour définir une fonction récursive."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1f5302c125605d2186deab0bbeaf2e84cc51edc3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="recursive-functions-the-rec-keyword"></a>Fonctions récursives : mot clé rec

Le `rec` (mot clé) est utilisé conjointement avec le `let` mot clé pour définir une fonction récursive.


## <a name="syntax"></a>Syntaxe

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>Notes
Les fonctions récursives, les fonctions qui appellent elles-mêmes, sont identifiées de façon explicite dans le langage F #. Cela permet l’identificateur qui est défini dans la portée de la fonction.

Le code suivant illustre une fonction récursive qui calcule le *n*ème nombre de Fibonacci.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
Dans la pratique, code ci-dessus comme cela est gaspille de la mémoire et le temps processeur, car il implique le recalcul des valeurs précédemment calculées.


Les méthodes sont implicitement récursives dans le type ; Il n’est pas nécessaire d’ajouter le `rec` (mot clé). Liaisons let dans les classes ne sont pas implicitement récursives.


## <a name="mutually-recursive-functions"></a>Fonctions mutuellement récursives
Parfois, les fonctions sont *mutuellement récursives*, ce qui signifie que les appels forment un cercle, où une fonction appelle une autre qui à son tour appelle la première, avec n’importe quel nombre d’appels entre les deux. Vous devez définir de telles fonctions un `let` de liaison, à l’aide de la `and` (mot clé) pour lier les.

L’exemple suivant montre deux mutuellement les fonctions récursives.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Voir aussi
[Fonctions](index.md)

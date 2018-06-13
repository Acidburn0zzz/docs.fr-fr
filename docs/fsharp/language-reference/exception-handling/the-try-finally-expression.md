---
title: 'Exceptions : expression try...finally (F#)'
description: "Découvrez comment F # ' try... finally' expression vous permet d’exécuter du code de nettoyage même si un bloc de code lève une exception."
ms.date: 05/16/2016
ms.openlocfilehash: a5fdec7b3986fc9a85c34b08d20dc31947c92b2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563491"
---
# <a name="exceptions-the-tryfinally-expression"></a>Exceptions : expression try...finally

Le `try...finally` expression vous permet d’exécuter du code de nettoyage même si un bloc de code lève une exception.


## <a name="syntax"></a>Syntaxe

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>Notes
Le `try...finally` expression peut être utilisée pour exécuter le code dans *expression2* dans la syntaxe précédente, indépendamment de si une exception est générée pendant l’exécution de *expression1*.

Le type de *expression2* ne contribue pas à la valeur de l’expression entière ; le type retourné lorsqu’une exception ne se produit pas est la dernière valeur dans *expression1*. Lorsqu’une exception se produit, aucune valeur n’est retournée et le flux de contrôle est transféré vers le Gestionnaire d’exceptions correspondant suivant dans la pile des appels. Si aucun gestionnaire d’exceptions n’est trouvée, le programme se termine. Avant que le code dans un gestionnaire correspondant est exécuté ou que le programme se termine, le code dans le `finally` branche est exécutée.

Le code suivant illustre l’utilisation de la `try...finally` expression.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

La sortie dans la console est la suivante.

```
Closing stream
Exception handled.
```

Comme vous pouvez le voir à partir de la sortie, le flux a été fermé avant que l’exception externe a été gérée et le fichier `test.txt` contient le texte `test1`, ce qui signifie que les mémoires tampons ont été vidés et écrites sur le disque même si l’exception transférés contrôle au gestionnaire d’exceptions externe.

Notez que la `try...with` est une construction distincte à partir de la `try...finally` construire. Par conséquent, si votre code requiert à la fois un `with` bloc et un `finally` bloc, vous devez imbriquer les deux constructions, comme dans l’exemple de code suivant.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

Dans le contexte d’expressions de calcul, y compris les expressions de séquence et flux de travail asynchrones, **try... finally** expressions peuvent avoir une implémentation personnalisée. Pour plus d’informations, consultez [Expressions de calcul](../computation-expressions.md).


## <a name="see-also"></a>Voir aussi
[Gestion des exceptions](index.md)

[Exceptions : expression `try...with`](the-try-with-expression.md)

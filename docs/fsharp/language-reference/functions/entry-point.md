---
title: Point d'entrée (F#)
description: 'Découvrez comment définir le point d’entrée à un programme F # est compilé en tant qu’un fichier exécutable, où l’exécution démarre formellement.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 42e5fe7f85285f990ef92e9791ed5bdfacb85059
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="entry-point"></a>Point d'entrée

Cette rubrique décrit la méthode que vous utilisez pour définir le point d’entrée à un programme F #.


## <a name="syntax"></a>Syntaxe

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Notes
Dans la syntaxe précédente, *permettent de liaison de fonction* est la définition d’une fonction dans une `let` liaison.

Le point d’entrée à un programme qui est compilé, car un fichier exécutable est où l’exécution démarre formellement. Vous spécifiez le point d’entrée à une application F # en appliquant la `EntryPoint` attribut du programme `main` (fonction). Cette fonction (créée à l’aide un `let` liaison) doit être la dernière fonction dans le dernier fichier compilé. Le dernier fichier compilé est le dernier fichier dans le projet ou le dernier fichier passé à la ligne de commande.

La fonction de point d’entrée a le type `string array -> int`. Les arguments fournis sur la ligne de commande sont passés à la `main` fonction dans le tableau de chaînes. Le premier élément du tableau est le premier argument ; le nom du fichier exécutable n’est pas inclus dans le tableau, comme dans d’autres langages. La valeur de retour est utilisée en tant que le code de sortie pour le processus. Zéro indique généralement le cas de réussite ; valeurs différentes de zéro indiquent une erreur. Il n’existe aucune convention pour la signification spécifique de codes de retour différente de zéro ; les significations des codes de retour sont spécifiques à l’application.

L’exemple suivant illustre un simple `main` (fonction).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

Lorsque ce code est exécuté avec la ligne de commande `EntryPoint.exe 1 2 3`, la sortie est la suivante.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Point d’entrée implicite
Lorsqu’un programme n’a aucun **EntryPoint** attribut qui indique explicitement le point d’entrée, les liaisons de niveau supérieur dans le dernier fichier à compiler sont utilisées comme point d’entrée.


## <a name="see-also"></a>Voir aussi
[Fonctions](index.md)

[Liaisons let](let-bindings.md)

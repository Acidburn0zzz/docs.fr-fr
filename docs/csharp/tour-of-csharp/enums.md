---
title: Énumérations C# - Visite guidée du langage C#
description: Découvrir les enums, constantes nommées discrètes en C#
ms.date: 08/10/2016
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: 7fe2626381cb90e55842e3be17dd450eb73d5a5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353352"
---
# <a name="enums"></a>Enums

Un ***type enum*** est un type valeur distinct avec un ensemble de constantes nommées. Vous définissez les enums lorsque vous devez définir un type qui peut avoir un ensemble de valeurs discrètes. Ils utilisent un des types entier comme stockage sous-jacent. Ils apportent une signification sémantique aux valeurs discrètes.

L’exemple suivant déclare et utilise un type `enum` nommé `Color` avec trois valeurs de constante, `Red`, `Green` et `Blue`.

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

Chaque type `enum` a un type intégral appelé ***type sous-jacent*** de type `enum`. Un type `enum` qui ne déclare pas explicitement un type sous-jacent a un type sous-jacent de `int`. Le format de stockage d’un type `enum` et la plage de valeurs possibles du type sont déterminés par son type sous-jacent. L’ensemble de valeurs qu’un type `enum` peut prendre n’est pas limité par ses membres `enum`. En particulier, n’importe quelle valeur du type sous-jacent d’une `enum` peut être castée en type `enum`, et une valeur valide distincte de ce type `enum`.

L’exemple suivant déclare un type `enum` nommé `Alignment` avec un type sous-jacent de `sbyte`.

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

Comme le montre l’exemple précédent, une déclaration de membre `enum` peut inclure une expression constante qui spécifie la valeur du membre. La valeur de constante pour chaque membre `enum` doit être dans la plage du type sous-jacent de l’ `enum`. Lorsqu’une déclaration de membre `enum` ne spécifie pas explicitement une valeur, le membre reçoit la valeur zéro (s’il est le premier membre dans le type `enum`) ou la valeur du membre `enum` précédent dans le texte plus un.

Les valeurs `Enum` peuvent être converties en valeurs intégrales et inversement à l’aide des casts de type. Exemple :

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

La valeur par défaut de n’importe quel type `enum` est la valeur intégrale de zéro convertie en type `enum`. Dans les cas où les variables sont initialisées automatiquement à une valeur par défaut, il s’agit de la valeur donnée aux variables des types `enum`. Afin que la valeur par défaut d’un type `enum` soit disponible, le littéral `0` convertit implicitement en n’importe quel type `enum`. Ce qui suit est donc autorisé.

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
[Précédent](interfaces.md)
[Suivant](delegates.md)

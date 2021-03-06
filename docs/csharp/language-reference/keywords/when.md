---
title: when, mot clé contextuel - Référence C#
ms.custom: seodec18
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: a8f64da0ab603830972035f1c2cd3a0b1eaadaff
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221854"
---
# <a name="when-c-reference"></a>when (référence C#)

Vous pouvez utiliser le mot clé contextuel `when` pour spécifier une condition de filtre dans deux contextes :

- dans l’instruction `catch` d’un bloc [try/catch](try-catch.md) ou [try/catch/finally](try-catch-finally.md) ;
- dans l’étiquette `case` d’une instruction [switch](switch.md).

## <a name="when-in-a-catch-statement"></a>`when` dans une instruction `catch`

Depuis C# 6, `when` peut être utilisé dans une instruction `catch` pour spécifier une condition qui doit avoir la valeur True pour que le gestionnaire d’une exception spécifique soit exécuté. Sa syntaxe est la suivante :

```csharp
catch (ExceptionType [e]) when (expr)
```

où *expr* est une expression qui prend une valeur booléenne. Si la valeur retournée est `true`, le gestionnaire de l’exception est exécuté ; si la valeur retournée est `false`, il n’est pas exécuté.

L’exemple suivant utilise le mot clé `when` afin d’exécuter conditionnellement des gestionnaires pour une exception <xref:System.Net.Http.HttpRequestException> selon le texte du message d’exception.

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a>`when` dans une instruction `switch`

Depuis C# 7.0, les étiquettes `case` n’ont plus besoin de s’exclure mutuellement et l’ordre dans lequel les étiquettes `case` s’affichent dans une instruction `switch` peut déterminer le bloc switch exécuté. Le mot clé `when` peut être utilisé pour spécifier une condition de filtre qui fait que son étiquette case associée a la valeur True uniquement si la condition de filtre a également la valeur True. Sa syntaxe est la suivante :

```csharp
case (expr) when (when-condition):
```

où *expr* est un modèle de constante ou de type qui est comparé à l’expression de correspondance, et *when-condition* représente toute expression booléenne.

L’exemple suivant utilise le mot clé `when` pour tester les objets `Shape` ayant une superficie égale à zéro, ainsi que pour tester divers objets `Shape` ayant une superficie supérieure à zéro.

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a>Voir aussi

- [switch, instruction](switch.md)
- [try/catch, instruction](try-catch.md)
- [try/catch/finally, instruction](try-catch-finally.md)
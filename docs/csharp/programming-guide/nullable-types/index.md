---
title: Types Nullable (Guide de programmation C#)
ms.date: 05/15/2017
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: fcff492f420a60a41b373bf9042ed0c2d66d0446
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2018
---
# <a name="nullable-types-c-programming-guide"></a>Types Nullable (Guide de programmation C#)
Les types Nullable sont des instances du struct <xref:System.Nullable%601?displayProperty=nameWithType>. Un type Nullable peut représenter la plage correcte de valeurs de son type valeur sous-jacent, plus une valeur `null` supplémentaire. Par exemple, un `Nullable<Int32>`, prononcé « Nullable d’Int32 », peut se voir affecter n’importe quelle valeur entre -2147483648 et 2147483647, ou la valeur `null`. Un `Nullable<bool>` peut se voir affecter les valeurs [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) ou [null](../../../csharp/language-reference/keywords/null.md). La capacité à affecter `null` aux types numériques et booléens est particulièrement utile lorsque l’on travaille avec des bases de données et d’autres types de données qui contiennent des éléments potentiellement sans valeur. Par exemple, un champ booléen dans une base de données peut stocker la valeur `true` ou `false`, ou être indéfini. 
  
[!code-csharp[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]  
  
Pour plus d’exemples, consultez la page [Utiliser les types Nullable](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).  
  
## <a name="nullable-types-overview"></a>Vue d’ensemble des types Nullable  
 Les types Nullable possèdent les caractéristiques suivantes :  
  
-   Les types Nullable représentent des variables de type valeur qui peuvent avoir la valeur `null`. Il n’est pas possible de créer un type Nullable à partir d’un type référence. (Les types référence prennent déjà en charge la valeur `null`.)  
  
-   La syntaxe `T?` est la forme abrégée de <xref:System.Nullable%601>, où `T` est un type valeur. Les deux formats sont interchangeables.  
  
-   Affectez une valeur à un type Nullable, comme vous le feriez pour un type valeur ordinaire, par exemple `int? x = 10;` ou `double? d = 4.108`. Un type Nullable peut également avoir la valeur `null` : `int? x = null.`  
  
-   Utilisez la méthode <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=nameWithType> pour retourner la valeur affectée, ou la valeur par défaut du type sous-jacent si la valeur est `null`, par exemple `int j = x.GetValueOrDefault();`  
  
-   Utilisez les propriétés <xref:System.Nullable%601.HasValue%2A> et <xref:System.Nullable%601.Value%2A> en lecture seule pour rechercher les valeurs null et récupérer la valeur, comme indiqué dans l’exemple suivant : `if(x.HasValue) j = x.Value;`  
  
    -   La propriété `HasValue` retourne `true` si la variable contient une valeur, ou `false` si elle est `null`.  
  
    -   La propriété `Value` retourne une valeur s’il existe une valeur affectée. Sinon, une exception <xref:System.InvalidOperationException?displayProperty=nameWithType> est levée.  
  
    -   La valeur par défaut de `HasValue` est `false`. La propriété `Value` n’a pas de valeur par défaut.  
  
    -   Vous pouvez également utiliser les opérateurs `==` et `!=` avec un type Nullable, comme le montre l’exemple suivant : `if (x != null) y = x;`.  
  
-   Utilisez l’opérateur `??` pour affecter une valeur par défaut qui sera appliquée lorsqu’un type Nullable dont la valeur actuelle est `null` sera affecté à un type non Nullable, par exemple `int? x = null; int y = x ?? -1;`.  
  
-   Les types Nullable imbriqués ne sont pas autorisés. Il n’est pas possible de compiler la ligne suivante : `Nullable<Nullable<int>> n;`  
  
## <a name="related-sections"></a>Rubriques connexes  
 Pour plus d'informations :  
  
-   [Utilisation de types Nullable](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Boxing des types Nullable](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [?? Opérateur](../../../csharp/language-reference/operators/null-coalescing-operator.md)  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Nullable>  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [C#](../../../csharp/index.md)  
 [Référence C#](../../../csharp/language-reference/index.md)  
 [Que signifie réellement « Lifted » ?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)

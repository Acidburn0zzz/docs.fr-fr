---
title: "Interpolation de chaîne - C#"
description: "Apprenez comment l’interpolation de chaîne fonctionne dans C# 6"
keywords: ".NET, .NET Core, C#, chaîne"
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.openlocfilehash: db062ed2f832ae933941da1c49e84303090f4390
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="string-interpolation-in-c"></a>Interpolation de chaîne en C# #

L’interpolation de chaîne est la façon dont les espaces réservés dans une chaîne sont remplacés par la valeur d’une variable de chaîne. Avant C# 6, la façon de procéder était avec <xref:System.String.Format%2A?displayProperty=nameWithType>. Cela fonctionnait correctement, mais comme des espaces réservés numérotés étaient utilisés, la lecture pouvait être plus difficile et lourde.

D’autres langages de programmation ont une interpolation de chaîne intégrée depuis un certain temps. Par exemple, dans PHP :

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

Dans C# 6, nous avons enfin ce style d’interpolation de chaîne. Vous pouvez utiliser un `$` avant une chaîne pour indiquer qu’elle doit remplacer les variables/expressions par leurs valeurs.

## <a name="prerequisites"></a>Prérequis
Vous devez configurer votre ordinateur pour exécuter .NET core. Vous trouverez les instructions d’installation sur la page de [.NET Core](https://www.microsoft.com/net/core).
Vous pouvez exécuter cette application sur Windows, Ubuntu Linux, Mac OS ou dans un conteneur Docker. Vous devez installer l’éditeur de code de votre choix. Les descriptions ci-dessous utilisent [Visual Studio Code](https://code.visualstudio.com/), un éditeur open source et multiplateforme. Cependant, vous pouvez utiliser les outils avec lesquels vous êtes le plus à l’aise.

## <a name="create-the-application"></a>Création de l’application

Maintenant que vous avez installé tous les outils, créez une nouvelle application .NET Core. Pour utiliser le générateur de ligne de commande, créez un répertoire pour votre projet, comme `interpolated`, et exécutez la commande suivante dans votre interpréteur de commandes préféré :

```
dotnet new console
```

Cette commande crée un projet .NET Core de base, avec un fichier projet, *interpolated.csproj*, et un fichier de code source, *Program.cs*. Vous devez exécuter `dotnet restore` pour restaurer les dépendances nécessaires à la compilation de ce projet.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Pour exécuter le programme, utilisez `dotnet run`. Vous devriez voir le résultat dans la « Hello, World » dans la console.



## <a name="intro-to-string-interpolation"></a>Présentation de l’interpolation de chaîne

Avec <xref:System.String.Format%2A?displayProperty=nameWithType>, vous spécifiez des « espaces réservés » dans une chaîne, qui sont remplacés par les arguments qui suivent cette chaîne. Par exemple :

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

Cela générera « My name is Matt Groves ».

Dans C# 6, au lieu d’utiliser `String.Format`, vous définissez une chaîne interpolée en ajoutant le symbole `$` au début, puis en utilisant les variables directement dans la chaîne. Par exemple :

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

Vous n'êtes pas obligé d'utiliser seulement des variables. Vous pouvez utiliser n’importe quelle expression entre crochets. Par exemple :

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

Ce qui devrait produire :

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a>Fonctionnement de l’interpolation de chaîne

En arrière-plan, cette syntaxe d’interpolation de chaîne est convertie en `String.Format` par le compilateur. Par conséquent, vous pouvez faire les [mêmes choses qu’avec `String.Format`](../../standard/base-types/formatting-types.md) auparavant.

Par exemple, vous pouvez ajouter le remplissage et la mise en forme des nombres :

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

La commande ci-dessus affiche quelque chose comme ceci :

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

Si un nom de variable est introuvable, une erreur de compilation est générée.

Par exemple :

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

Si vous compilez ce code, vous obtenez des erreurs :
 
* `Cannot use local variable 'adj' before it is declared` - la variable `adj` n’a été déclarée *qu’après* la chaîne interpolée.
* `The name 'otheranimal' does not exist in the current context` - une variable appelée `otheranimal` n’a même pas été déclarée du tout

## <a name="localization-and-internationalization"></a>Localisation et internationalisation

Une chaîne interpolée prend en charge <xref:System.IFormattable?displayProperty=nameWithType> et <xref:System.FormattableString?displayProperty=nameWithType>, ce qui peut être utile pour l’internationalisation.

Par défaut, une chaîne interpolée utilise la culture actuelle. Pour utiliser une autre culture, effectuez un cast d’une chaîne interpolée en tant que `IFormattable`. Par exemple :

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a>Conclusion 

Dans ce didacticiel, vous avez appris comment utiliser les fonctionnalités d’interpolation des chaînes C# 6. Il s’agit d’un moyen plus concis d’écrire des instructions `String.Format` simples, avec certaines précautions à observer pour des utilisations plus avancées. Pour plus d’informations, consultez la rubrique [Chaînes interpolées](../../csharp//language-reference/keywords/interpolated-strings.md).

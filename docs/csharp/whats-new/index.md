---
title: Nouveautés de C# | Guide C#
description: Évolution du langage C#
ms.date: 11/13/2017
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 3fc42809943b10d09d59780576dd9768d9e16ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c"></a>Nouveautés de C# #

Cette page fournit un Guide des nouvelles fonctionnalités de chaque version majeure du langage c#. Les liens suivants fournissent des informations détaillées sur les principales fonctionnalités ajoutées dans chaque version.

> [!IMPORTANT]
> Le langage c# s’appuie sur des types et des méthodes présents dans une *bibliothèque standard* pour certaines des fonctionnalités. Par exemple, le traitement des exceptions. Chaque instruction ou expression`throw` est vérifiée pour s’assurer de l’objet levé est dérivé de <xref:System.Exception>. De même, chaque `catch` est vérifié pour assurer que le type intercepté est dérivé de <xref:System.Exception>. Chaque version peut ajouter de nouvelles spécifications. Pour utiliser les dernières fonctionnalités de langage dans les environnements plus anciens, vous devrez peut-être installer des bibliothèques spécifiques. Ces dépendances sont décrites dans la page pour chaque version spécifique. Pour en savoir plus, consultez les [relations entre le langage et la bibliothèque](relationships-between-language-and-library.md) pour l’arrière-plan sur cette dépendance. 


* [C# 7.2](csharp-7-2.md) :
    - Cette page décrit les dernières fonctionnalités du langage C#. C# 7.2 est actuellement disponible dans [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/whatsnew/) et dans le kit [SDK .NET Core 2.0](../../core/whats-new/index.md).

* [C# 7.1](csharp-7-1.md):
    - Cette page décrit les fonctionnalités dans C# 7.1. Ces fonctionnalités ont été ajoutées dans [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/) et dans le kit [SDK .NET Core 2.0](../../core/whats-new/index.md).

* [C# 7.0](csharp-7.md) :
    - Cette page décrit les fonctionnalités ajoutées dans C# 7.0. Ces fonctionnalités ont été ajoutées dans [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) et [.NET Core 1.0](../../core/whats-new/index.md) et versions ultérieures
     
* [C# 6](csharp-6.md) :
    - Cette page décrit les nouvelles fonctionnalités de C# 6. Ces fonctionnalités sont disponibles dans Visual Studio 2015 pour les développeurs Windows, et dans .NET Core 1.0 pour les développeurs s’intéressant à C# sur Mac OS et Linux.

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* [Prise en charge multiplateforme](../../core/index.md) :
    - Grâce à sa prise en charge de .NET Core, C# s’exécute sur plusieurs plateformes. Si vous voulez essayer C# sur macOS ou sur une des nombreuses distributions Linux prises en charge, découvrez plus d’informations sur .NET Core.

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a>Versions antérieures
Les fonctionnalités clés répertoriées ci-dessous ont été introduites dans des versions antérieures du langage C# et de Visual Studio .NET.  
  
 * Visual Studio .NET 2013 : 
     - Cette version de Visual Studio incluait des correctifs de bogues, des améliorations des performances ainsi que des préversions de la plateforme de compilation .NET (« Roslyn »), aujourd’hui connue sous le nom de .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.

 * C# 5, Visual Studio .NET 2012 : 
     - `Async` / `await`, et attributs des [informations sur l’appelant](../programming-guide/concepts/caller-information.md).

 * C# 4, Visual Studio .NET 2010 : 
     - `Dynamic`, [arguments nommés](../programming-guide/classes-and-structs/named-and-optional-arguments.md), paramètres facultatifs, et [covariance et contravariance](../programming-guide/concepts/covariance-contravariance/index.md) génériques.

 * C# 3, Visual Studio .NET 2008 : 
     - Initialiseurs d’objet et de collection, expressions lambda, méthodes d’extension, types anonymes, propriétés automatiques, inférence de type `var` locale, et [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).

 * C# 2, Visual Studio .NET 2005 : 
     - Méthodes anonymes, génériques, types Nullable, itérateurs/yield, classes `static`, variance et contravariance pour les délégués.

 * C# 1.1, Visual Studio .NET 2003 : 
     - Pragma `#line` et commentaires de documentation XML.

 * C# 1, Visual Studio .NET 2002 : 
     - Première version de [C#](../csharp.md).   

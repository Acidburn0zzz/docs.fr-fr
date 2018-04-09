---
title: Interpolation de chaîne - C#
description: Apprenez comment l’interpolation de chaîne fonctionne dans C# 6
keywords: .NET, .NET Core, C#, chaîne
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.openlocfilehash: a9578d006861b987871071961437345c378a5b58
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="86da5-104">Interpolation de chaîne en C#</span><span class="sxs-lookup"><span data-stu-id="86da5-104">String Interpolation in C#</span></span> #

<span data-ttu-id="86da5-105">L’interpolation de chaîne est la façon dont les espaces réservés dans une chaîne sont remplacés par la valeur d’une variable de chaîne.</span><span class="sxs-lookup"><span data-stu-id="86da5-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="86da5-106">Avant C# 6, la façon de procéder était avec <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86da5-106">Before C# 6, the way to do this is with <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="86da5-107">Cela fonctionnait correctement, mais comme des espaces réservés numérotés étaient utilisés, la lecture pouvait être plus difficile et lourde.</span><span class="sxs-lookup"><span data-stu-id="86da5-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="86da5-108">D’autres langages de programmation ont une interpolation de chaîne intégrée depuis un certain temps.</span><span class="sxs-lookup"><span data-stu-id="86da5-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="86da5-109">Par exemple, dans PHP :</span><span class="sxs-lookup"><span data-stu-id="86da5-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="86da5-110">Dans C# 6, nous avons enfin ce style d’interpolation de chaîne.</span><span class="sxs-lookup"><span data-stu-id="86da5-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="86da5-111">Vous pouvez utiliser un `$` avant une chaîne pour indiquer qu’elle doit remplacer les variables/expressions par leurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="86da5-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86da5-112">Prérequis</span><span class="sxs-lookup"><span data-stu-id="86da5-112">Prerequisites</span></span>
<span data-ttu-id="86da5-113">Vous devez configurer votre ordinateur pour exécuter .NET core.</span><span class="sxs-lookup"><span data-stu-id="86da5-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="86da5-114">Vous trouverez les instructions d’installation sur la page de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="86da5-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="86da5-115">Vous pouvez exécuter cette application sur Windows, Ubuntu Linux, Mac OS ou dans un conteneur Docker.</span><span class="sxs-lookup"><span data-stu-id="86da5-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="86da5-116">Vous devez installer l’éditeur de code de votre choix.</span><span class="sxs-lookup"><span data-stu-id="86da5-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="86da5-117">Les descriptions ci-dessous utilisent [Visual Studio Code](https://code.visualstudio.com/), un éditeur open source et multiplateforme.</span><span class="sxs-lookup"><span data-stu-id="86da5-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="86da5-118">Cependant, vous pouvez utiliser les outils avec lesquels vous êtes le plus à l’aise.</span><span class="sxs-lookup"><span data-stu-id="86da5-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="86da5-119">Création de l’application</span><span class="sxs-lookup"><span data-stu-id="86da5-119">Create the Application</span></span>

<span data-ttu-id="86da5-120">Maintenant que vous avez installé tous les outils, créez une nouvelle application .NET Core.</span><span class="sxs-lookup"><span data-stu-id="86da5-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="86da5-121">Pour utiliser le générateur de ligne de commande, créez un répertoire pour votre projet, comme `interpolated`, et exécutez la commande suivante dans votre interpréteur de commandes préféré :</span><span class="sxs-lookup"><span data-stu-id="86da5-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="86da5-122">Cette commande crée un projet .NET Core de base, avec un fichier projet, *interpolated.csproj*, et un fichier de code source, *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="86da5-122">This command creates a barebones .NET Core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="86da5-123">Vous devez exécuter `dotnet restore` pour restaurer les dépendances nécessaires à la compilation de ce projet.</span><span class="sxs-lookup"><span data-stu-id="86da5-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="86da5-124">Pour exécuter le programme, utilisez `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="86da5-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="86da5-125">Vous devriez voir le résultat dans la « Hello, World » dans la console.</span><span class="sxs-lookup"><span data-stu-id="86da5-125">You should see "Hello, World" output to the console.</span></span>



## <a name="intro-to-string-interpolation"></a><span data-ttu-id="86da5-126">Présentation de l’interpolation de chaîne</span><span class="sxs-lookup"><span data-stu-id="86da5-126">Intro to String Interpolation</span></span>

<span data-ttu-id="86da5-127">Avec <xref:System.String.Format%2A?displayProperty=nameWithType>, vous spécifiez des « espaces réservés » dans une chaîne, qui sont remplacés par les arguments qui suivent cette chaîne.</span><span class="sxs-lookup"><span data-stu-id="86da5-127">With <xref:System.String.Format%2A?displayProperty=nameWithType>, you specify "placeholders" in a string that are replaced by the arguments following the string.</span></span> <span data-ttu-id="86da5-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="86da5-128">For instance:</span></span>

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

<span data-ttu-id="86da5-129">Cela générera « My name is Matt Groves ».</span><span class="sxs-lookup"><span data-stu-id="86da5-129">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="86da5-130">Dans C# 6, au lieu d’utiliser `String.Format`, vous définissez une chaîne interpolée en ajoutant le symbole `$` au début, puis en utilisant les variables directement dans la chaîne.</span><span class="sxs-lookup"><span data-stu-id="86da5-130">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="86da5-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="86da5-131">For instance:</span></span>

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

<span data-ttu-id="86da5-132">Vous n'êtes pas obligé d'utiliser seulement des variables.</span><span class="sxs-lookup"><span data-stu-id="86da5-132">You don't have to use just variables.</span></span> <span data-ttu-id="86da5-133">Vous pouvez utiliser n’importe quelle expression entre crochets.</span><span class="sxs-lookup"><span data-stu-id="86da5-133">You can use any expression within the brackets.</span></span> <span data-ttu-id="86da5-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="86da5-134">For instance:</span></span>

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

<span data-ttu-id="86da5-135">Ce qui devrait produire :</span><span class="sxs-lookup"><span data-stu-id="86da5-135">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="86da5-136">Fonctionnement de l’interpolation de chaîne</span><span class="sxs-lookup"><span data-stu-id="86da5-136">How string interpolation works</span></span>

<span data-ttu-id="86da5-137">En arrière-plan, cette syntaxe d’interpolation de chaîne est convertie en `String.Format` par le compilateur.</span><span class="sxs-lookup"><span data-stu-id="86da5-137">Behind the scenes, this string interpolation syntax is translated into `String.Format` by the compiler.</span></span> <span data-ttu-id="86da5-138">Par conséquent, vous pouvez faire les [mêmes choses qu’avec `String.Format`](../../standard/base-types/formatting-types.md) auparavant.</span><span class="sxs-lookup"><span data-stu-id="86da5-138">So, you can do the [same type of stuff you've done before with `String.Format`](../../standard/base-types/formatting-types.md).</span></span>

<span data-ttu-id="86da5-139">Par exemple, vous pouvez ajouter le remplissage et la mise en forme des nombres :</span><span class="sxs-lookup"><span data-stu-id="86da5-139">For instance, you can add padding and numeric formatting:</span></span>

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

<span data-ttu-id="86da5-140">La commande ci-dessus affiche quelque chose comme ceci :</span><span class="sxs-lookup"><span data-stu-id="86da5-140">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="86da5-141">Si un nom de variable est introuvable, une erreur de compilation est générée.</span><span class="sxs-lookup"><span data-stu-id="86da5-141">If a variable name is not found, then a compile-time error is generated.</span></span>

<span data-ttu-id="86da5-142">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="86da5-142">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="86da5-143">Si vous compilez ce code, vous obtenez des erreurs :</span><span class="sxs-lookup"><span data-stu-id="86da5-143">If you compile this, you get errors:</span></span>
 
* <span data-ttu-id="86da5-144">`Cannot use local variable 'adj' before it is declared` - la variable `adj` n’a été déclarée *qu’après* la chaîne interpolée.</span><span class="sxs-lookup"><span data-stu-id="86da5-144">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="86da5-145">`The name 'otheranimal' does not exist in the current context` - une variable appelée `otheranimal` n’a même pas été déclarée du tout</span><span class="sxs-lookup"><span data-stu-id="86da5-145">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="86da5-146">Localisation et internationalisation</span><span class="sxs-lookup"><span data-stu-id="86da5-146">Localization and Internationalization</span></span>

<span data-ttu-id="86da5-147">Une chaîne interpolée prend en charge <xref:System.IFormattable?displayProperty=nameWithType> et <xref:System.FormattableString?displayProperty=nameWithType>, ce qui peut être utile pour l’internationalisation.</span><span class="sxs-lookup"><span data-stu-id="86da5-147">An interpolated string supports <xref:System.IFormattable?displayProperty=nameWithType> and <xref:System.FormattableString?displayProperty=nameWithType>, which can be useful for internationalization.</span></span>

<span data-ttu-id="86da5-148">Par défaut, une chaîne interpolée utilise la culture actuelle.</span><span class="sxs-lookup"><span data-stu-id="86da5-148">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="86da5-149">Pour utiliser une autre culture, effectuez un cast d’une chaîne interpolée en tant que `IFormattable`.</span><span class="sxs-lookup"><span data-stu-id="86da5-149">To use a different culture, cast an interpolated string as `IFormattable`.</span></span> <span data-ttu-id="86da5-150">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="86da5-150">For instance:</span></span>

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a><span data-ttu-id="86da5-151">Conclusion</span><span class="sxs-lookup"><span data-stu-id="86da5-151">Conclusion</span></span> 

<span data-ttu-id="86da5-152">Dans ce didacticiel, vous avez appris comment utiliser les fonctionnalités d’interpolation des chaînes C# 6.</span><span class="sxs-lookup"><span data-stu-id="86da5-152">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="86da5-153">Il s’agit d’un moyen plus concis d’écrire des instructions `String.Format` simples, avec certaines précautions à observer pour des utilisations plus avancées.</span><span class="sxs-lookup"><span data-stu-id="86da5-153">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses.</span></span> <span data-ttu-id="86da5-154">Pour plus d’informations, consultez la rubrique [Interpolation de chaîne](../../csharp//language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="86da5-154">For more information, see the [String interpolation](../../csharp//language-reference/tokens/interpolated.md) topic.</span></span>

---
title: Commande dotnet pack - Interface CLI .NET Core
description: "La commande dotnet pack crée des packages NuGet pour votre projet .NET Core."
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 401a4491c27ea10d0fdf1877417f1e2d5da6839f
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
# <a name="dotnet-pack"></a><span data-ttu-id="de119-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="de119-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="de119-104">Name</span><span class="sxs-lookup"><span data-stu-id="de119-104">Name</span></span>

<span data-ttu-id="de119-105">`dotnet pack` : Place le code dans un package NuGet.</span><span class="sxs-lookup"><span data-stu-id="de119-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="de119-106">Résumé</span><span class="sxs-lookup"><span data-stu-id="de119-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="de119-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="de119-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="de119-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="de119-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="de119-109">Description</span><span class="sxs-lookup"><span data-stu-id="de119-109">Description</span></span>

<span data-ttu-id="de119-110">La commande `dotnet pack` génère le projet et crée les packages NuGet.</span><span class="sxs-lookup"><span data-stu-id="de119-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="de119-111">Le résultat de cette commande est un package NuGet.</span><span class="sxs-lookup"><span data-stu-id="de119-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="de119-112">Si l’option `--include-symbols` est présente, un autre package contenant les symboles de débogage est créé.</span><span class="sxs-lookup"><span data-stu-id="de119-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="de119-113">Les dépendances NuGet du projet empaqueté sont ajoutées dans le fichier *.nuspec*, pour pouvoir être correctement résolues lors de l’installation du package.</span><span class="sxs-lookup"><span data-stu-id="de119-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="de119-114">Les références entre projets ne sont pas empaquetées à l’intérieur du projet.</span><span class="sxs-lookup"><span data-stu-id="de119-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="de119-115">Actuellement, vous devez disposer d’un package par projet si vous avez des dépendances entre projets.</span><span class="sxs-lookup"><span data-stu-id="de119-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="de119-116">Par défaut, `dotnet pack` génère d’abord le projet.</span><span class="sxs-lookup"><span data-stu-id="de119-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="de119-117">Pour éviter ce comportement, passez l’option `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="de119-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="de119-118">Elle est souvent utile dans les scénarios de build d’intégration continue, pour lesquels vous savez que le code a déjà été créé.</span><span class="sxs-lookup"><span data-stu-id="de119-118">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="de119-119">Vous pouvez fournir des propriétés MSBuild à la commande `dotnet pack` pour le processus de compression.</span><span class="sxs-lookup"><span data-stu-id="de119-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="de119-120">Pour plus d’informations, consultez [Propriétés des métadonnées NuGet](csproj.md#nuget-metadata-properties) et [Informations de référence sur la ligne de commande MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="de119-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="de119-121">La section [Exemples](#examples) montre comment utiliser le commutateur MSBuild /p pour deux scénarios différents.</span><span class="sxs-lookup"><span data-stu-id="de119-121">The [Examples](#examples) section shows how to use the MSBuild /p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="de119-122">Arguments</span><span class="sxs-lookup"><span data-stu-id="de119-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="de119-123">Projet à empaqueter.</span><span class="sxs-lookup"><span data-stu-id="de119-123">The project to pack.</span></span> <span data-ttu-id="de119-124">Il s’agit du chemin d’accès d’un [fichier csproj](csproj.md) ou d’un répertoire.</span><span class="sxs-lookup"><span data-stu-id="de119-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="de119-125">Si aucune valeur n’est spécifiée, le répertoire actif est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="de119-125">If omitted, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="de119-126">Options</span><span class="sxs-lookup"><span data-stu-id="de119-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="de119-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="de119-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="de119-128">Définit la configuration de build.</span><span class="sxs-lookup"><span data-stu-id="de119-128">Defines the build configuration.</span></span> <span data-ttu-id="de119-129">La valeur par défaut est `Debug`.</span><span class="sxs-lookup"><span data-stu-id="de119-129">The default value is `Debug`.</span></span>

<span data-ttu-id="de119-130">`--force` : force la résolution de toutes les dépendances même si la dernière restauration a réussi.</span><span class="sxs-lookup"><span data-stu-id="de119-130">`--force` Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="de119-131">Cette opération équivaut à supprimer le fichier *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="de119-131">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="de119-132">Affiche une aide brève pour la commande.</span><span class="sxs-lookup"><span data-stu-id="de119-132">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="de119-133">Inclut les fichiers sources dans le package NuGet.</span><span class="sxs-lookup"><span data-stu-id="de119-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="de119-134">Les fichiers sources sont inclus dans le dossier `src` de `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="de119-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="de119-135">Génère les symboles `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="de119-135">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="de119-136">Ne génère pas le projet avant de créer le package.</span><span class="sxs-lookup"><span data-stu-id="de119-136">Doesn't build the project before packing.</span></span>

`--no-dependencies`

<span data-ttu-id="de119-137">Ignore les références entre projets et restaure uniquement le projet racine.</span><span class="sxs-lookup"><span data-stu-id="de119-137">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="de119-138">N’effectue pas de restauration implicite à l’exécution de la commande.</span><span class="sxs-lookup"><span data-stu-id="de119-138">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="de119-139">Place les packages générés dans le répertoire spécifié.</span><span class="sxs-lookup"><span data-stu-id="de119-139">Places the built packages in the directory specified.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="de119-140">Spécifie le runtime cible pour lequel restaurer les packages.</span><span class="sxs-lookup"><span data-stu-id="de119-140">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="de119-141">Pour connaître les identificateurs de runtime, consultez le [catalogue des identificateurs de runtime](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="de119-141">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="de119-142">Définit l’indicateur d’un état pouvant faire l’objet d’une maintenance dans le package.</span><span class="sxs-lookup"><span data-stu-id="de119-142">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="de119-143">Pour plus d’informations, consultez [Blog .NET : .NET 4.5.1 prend en charge les mises à jour de sécurité de Microsoft pour les bibliothèques NuGet .NET](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="de119-143">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="de119-144">Définit la valeur de la propriété MSBuild `$(VersionSuffix)` dans le projet.</span><span class="sxs-lookup"><span data-stu-id="de119-144">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="de119-145">Définit le niveau de détail de la commande.</span><span class="sxs-lookup"><span data-stu-id="de119-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="de119-146">Les valeurs autorisées sont `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` et `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="de119-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="de119-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="de119-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="de119-148">Définit la configuration de build.</span><span class="sxs-lookup"><span data-stu-id="de119-148">Defines the build configuration.</span></span> <span data-ttu-id="de119-149">La valeur par défaut est `Debug`.</span><span class="sxs-lookup"><span data-stu-id="de119-149">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="de119-150">Affiche une aide brève pour la commande.</span><span class="sxs-lookup"><span data-stu-id="de119-150">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="de119-151">Inclut les fichiers sources dans le package NuGet.</span><span class="sxs-lookup"><span data-stu-id="de119-151">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="de119-152">Les fichiers sources sont inclus dans le dossier `src` de `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="de119-152">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="de119-153">Génère les symboles `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="de119-153">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="de119-154">Ne génère pas le projet avant de créer le package.</span><span class="sxs-lookup"><span data-stu-id="de119-154">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="de119-155">Place les packages générés dans le répertoire spécifié.</span><span class="sxs-lookup"><span data-stu-id="de119-155">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="de119-156">Définit l’indicateur d’un état pouvant faire l’objet d’une maintenance dans le package.</span><span class="sxs-lookup"><span data-stu-id="de119-156">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="de119-157">Pour plus d’informations, consultez [Blog .NET : .NET 4.5.1 prend en charge les mises à jour de sécurité de Microsoft pour les bibliothèques NuGet .NET](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="de119-157">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="de119-158">Définit la valeur de la propriété MSBuild `$(VersionSuffix)` dans le projet.</span><span class="sxs-lookup"><span data-stu-id="de119-158">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="de119-159">Définit le niveau de détail de la commande.</span><span class="sxs-lookup"><span data-stu-id="de119-159">Sets the verbosity level of the command.</span></span> <span data-ttu-id="de119-160">Les valeurs autorisées sont `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` et `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="de119-160">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="de119-161">Exemples</span><span class="sxs-lookup"><span data-stu-id="de119-161">Examples</span></span>

<span data-ttu-id="de119-162">Empaquetez le projet dans le répertoire actif :</span><span class="sxs-lookup"><span data-stu-id="de119-162">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="de119-163">Empaqueter le projet `app1` :</span><span class="sxs-lookup"><span data-stu-id="de119-163">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`

<span data-ttu-id="de119-164">Empaqueter le projet dans le répertoire actif et placer les packages résultants dans le dossier `nupkgs` :</span><span class="sxs-lookup"><span data-stu-id="de119-164">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="de119-165">Empaqueter le projet dans le répertoire actif du dossier `nupkgs` et ignorer l’étape de génération :</span><span class="sxs-lookup"><span data-stu-id="de119-165">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="de119-166">Avec le suffixe de version du projet configuré comme `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` dans le fichier *.csproj*, empaqueter le projet actif et mettre à jour la version du package obtenue avec le suffixe donné :</span><span class="sxs-lookup"><span data-stu-id="de119-166">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="de119-167">Affectez `2.1.0` à la version du package à l’aide de la propriété MSBuild `PackageVersion` :</span><span class="sxs-lookup"><span data-stu-id="de119-167">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

<span data-ttu-id="de119-168">Empaquetez le projet pour un [framework cible](../../standard/frameworks.md) spécifique :</span><span class="sxs-lookup"><span data-stu-id="de119-168">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

`dotnet pack /p:TargetFrameworks=net45`

<span data-ttu-id="de119-169">Empaqueter le projet et utiliser un runtime spécifique (Windows 10) pour l’opération de restauration (SDK .NET Core 2.0 et versions ultérieures) :</span><span class="sxs-lookup"><span data-stu-id="de119-169">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet pack --runtime win10-x64`
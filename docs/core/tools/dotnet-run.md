---
title: Commande dotnet run - Interface CLI .NET Core
description: La commande dotnet run fournit une option pratique pour exécuter votre application à partir du code source.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 18ceb395ed025fa562f295fc2facd00c67a75536
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-run"></a><span data-ttu-id="75f12-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="75f12-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="75f12-104">Name</span><span class="sxs-lookup"><span data-stu-id="75f12-104">Name</span></span>

<span data-ttu-id="75f12-105">`dotnet run` - Exécute le code source sans commandes explicites de compilation ou de démarrage.</span><span class="sxs-lookup"><span data-stu-id="75f12-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="75f12-106">Résumé</span><span class="sxs-lookup"><span data-stu-id="75f12-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="75f12-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="75f12-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="75f12-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="75f12-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="75f12-109">Description</span><span class="sxs-lookup"><span data-stu-id="75f12-109">Description</span></span>

<span data-ttu-id="75f12-110">La commande `dotnet run` fournit une option pratique pour exécuter votre application à partir du code source à l’aide d’une seule commande.</span><span class="sxs-lookup"><span data-stu-id="75f12-110">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="75f12-111">Elle est utile pour le développement itératif rapide en ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="75f12-111">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="75f12-112">Elle dépend de la commande [`dotnet build`](dotnet-build.md) pour générer le code.</span><span class="sxs-lookup"><span data-stu-id="75f12-112">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="75f12-113">Les conditions requises pour la génération, par exemple le fait que le projet doit être restauré en premier, s’appliquent également à `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="75f12-113">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="75f12-114">Les fichiers de sortie sont écrits dans l’emplacement par défaut, à savoir `bin/<configuration>/<target>`.</span><span class="sxs-lookup"><span data-stu-id="75f12-114">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="75f12-115">Par exemple, si vous avez une application `netcoreapp1.0` et que vous exécutez `dotnet run`, la sortie est placée dans `bin/Debug/netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="75f12-115">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="75f12-116">Les fichiers sont remplacés, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="75f12-116">Files are overwritten as needed.</span></span> <span data-ttu-id="75f12-117">Les fichiers temporaires sont placés dans le répertoire `obj`.</span><span class="sxs-lookup"><span data-stu-id="75f12-117">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="75f12-118">Si le projet spécifie plusieurs frameworks, l’exécution de `dotnet run` entraîne une erreur, sauf si l’option `-f|--framework <FRAMEWORK>` est utilisée pour spécifier le framework.</span><span class="sxs-lookup"><span data-stu-id="75f12-118">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="75f12-119">La commande `dotnet run` est utilisée pour des projets, et pas pour des assemblys générés.</span><span class="sxs-lookup"><span data-stu-id="75f12-119">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="75f12-120">Si vous tentez d’exécuter plutôt une DLL d’applications dépendantes du framework, vous devez utiliser [dotnet](dotnet.md) sans commande.</span><span class="sxs-lookup"><span data-stu-id="75f12-120">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="75f12-121">Par exemple, pour exécuter `myapp.dll`, utilisez :</span><span class="sxs-lookup"><span data-stu-id="75f12-121">For example, to run `myapp.dll`, use:</span></span>

```
dotnet myapp.dll
```

<span data-ttu-id="75f12-122">Pour plus d’informations sur le pilote `dotnet`, consultez la rubrique [Outils en ligne de commande (CLI) .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="75f12-122">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="75f12-123">Pour exécuter l’application, la commande `dotnet run` résout les dépendances de l’application externes au runtime partagé à partir du cache NuGet.</span><span class="sxs-lookup"><span data-stu-id="75f12-123">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="75f12-124">Dans la mesure où elle utilise la mise en cache des dépendances, il n’est pas recommandé d’utiliser `dotnet run` pour exécuter des applications en production.</span><span class="sxs-lookup"><span data-stu-id="75f12-124">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="75f12-125">[Créez plutôt un déploiement](../deploying/index.md) à l’aide de la commande [`dotnet publish`](dotnet-publish.md) et déployez le résultat publié.</span><span class="sxs-lookup"><span data-stu-id="75f12-125">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="75f12-126">Options</span><span class="sxs-lookup"><span data-stu-id="75f12-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="75f12-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="75f12-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`--`

<span data-ttu-id="75f12-128">Délimite les arguments à `dotnet run` parmi les arguments de l’application en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="75f12-128">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="75f12-129">Tous les arguments après celui-ci sont passés à l’application exécutée.</span><span class="sxs-lookup"><span data-stu-id="75f12-129">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="75f12-130">Définit la configuration de build.</span><span class="sxs-lookup"><span data-stu-id="75f12-130">Defines the build configuration.</span></span> <span data-ttu-id="75f12-131">La valeur par défaut est `Debug`.</span><span class="sxs-lookup"><span data-stu-id="75f12-131">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="75f12-132">Crée et exécute l’application à l’aide du [framework](../../standard/frameworks.md) spécifié.</span><span class="sxs-lookup"><span data-stu-id="75f12-132">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="75f12-133">Le framework doit être spécifié dans le fichier projet.</span><span class="sxs-lookup"><span data-stu-id="75f12-133">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="75f12-134">Force la résolution de toutes les dépendances même si la dernière restauration a réussi.</span><span class="sxs-lookup"><span data-stu-id="75f12-134">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="75f12-135">Cette opération équivaut à supprimer *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="75f12-135">This is equivalent to deleting *project.assets.json*.</span></span>

`-h|--help`

<span data-ttu-id="75f12-136">Affiche une aide brève pour la commande.</span><span class="sxs-lookup"><span data-stu-id="75f12-136">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="75f12-137">Nom du profil de lancement éventuel à utiliser au lancement de l’application.</span><span class="sxs-lookup"><span data-stu-id="75f12-137">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="75f12-138">Les profils de lancement sont définis dans le fichier *launchSettings.json* et sont généralement appelés `Development`, `Staging` et `Production`.</span><span class="sxs-lookup"><span data-stu-id="75f12-138">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging` and `Production`.</span></span> <span data-ttu-id="75f12-139">Pour plus d’informations, consultez [Utilisation de plusieurs environnements](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="75f12-139">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="75f12-140">Ne génère pas le projet avant l’exécution.</span><span class="sxs-lookup"><span data-stu-id="75f12-140">Doesn't build the project before running.</span></span>

`--no-dependencies`

<span data-ttu-id="75f12-141">En cas de restauration d’un projet avec des références entre projets (P2P), restaure le projet racine et non les références.</span><span class="sxs-lookup"><span data-stu-id="75f12-141">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="75f12-142">N’essaie pas d’utiliser *launchSettings.json* pour configurer l’application.</span><span class="sxs-lookup"><span data-stu-id="75f12-142">Doesn't attempt to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="75f12-143">N’effectue pas de restauration implicite à l’exécution de la commande.</span><span class="sxs-lookup"><span data-stu-id="75f12-143">Doesn't perform an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="75f12-144">Spécifie le chemin du fichier projet à exécuter (nom de dossier ou chemin complet).</span><span class="sxs-lookup"><span data-stu-id="75f12-144">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="75f12-145">Si aucune valeur n’est spécifiée, le répertoire actif est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="75f12-145">It defaults to the current directory if not specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="75f12-146">Spécifie le runtime cible pour lequel restaurer les packages.</span><span class="sxs-lookup"><span data-stu-id="75f12-146">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="75f12-147">Pour connaître les identificateurs de runtime, consultez le [catalogue des identificateurs de runtime](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="75f12-147">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="75f12-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="75f12-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="75f12-149">Délimite les arguments à `dotnet run` parmi les arguments de l’application en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="75f12-149">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="75f12-150">Tous les arguments après celui-ci sont passés à l’application exécutée.</span><span class="sxs-lookup"><span data-stu-id="75f12-150">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="75f12-151">Définit la configuration de build.</span><span class="sxs-lookup"><span data-stu-id="75f12-151">Defines the build configuration.</span></span> <span data-ttu-id="75f12-152">La valeur par défaut est `Debug`.</span><span class="sxs-lookup"><span data-stu-id="75f12-152">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="75f12-153">Crée et exécute l’application à l’aide du [framework](../../standard/frameworks.md) spécifié.</span><span class="sxs-lookup"><span data-stu-id="75f12-153">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="75f12-154">Le framework doit être spécifié dans le fichier projet.</span><span class="sxs-lookup"><span data-stu-id="75f12-154">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="75f12-155">Affiche une aide brève pour la commande.</span><span class="sxs-lookup"><span data-stu-id="75f12-155">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="75f12-156">Spécifie le chemin d’accès et le nom du fichier projet.</span><span class="sxs-lookup"><span data-stu-id="75f12-156">Specifies the path and name of the project file.</span></span> <span data-ttu-id="75f12-157">(Voir la REMARQUE.) Si aucune valeur n’est spécifiée, le répertoire actif est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="75f12-157">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="75f12-158">Utilisez le chemin d’accès et le nom du fichier projet avec l’option `-p|--project`.</span><span class="sxs-lookup"><span data-stu-id="75f12-158">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="75f12-159">Une régression dans l’interface CLI empêche de fournir un chemin de dossier avec le SDK .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="75f12-159">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="75f12-160">Pour plus d’informations sur ce problème, consultez la page [dotnet run -p, impossible de démarrer un projet (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="75f12-160">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="75f12-161">Exemples</span><span class="sxs-lookup"><span data-stu-id="75f12-161">Examples</span></span>

<span data-ttu-id="75f12-162">Exécutez le projet dans le répertoire actif :</span><span class="sxs-lookup"><span data-stu-id="75f12-162">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="75f12-163">Exécutez le projet spécifié :</span><span class="sxs-lookup"><span data-stu-id="75f12-163">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="75f12-164">Exécuter le projet situé dans le répertoire actif (l’argument `--help` de cet exemple est passé à l’application, puisque l’argument `--` est utilisé) :</span><span class="sxs-lookup"><span data-stu-id="75f12-164">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="75f12-165">Restaurer des dépendances et des outils pour le projet dans le répertoire actuel en montrant uniquement une sortie minimale, puis exécuter le projet : (SDK .NET Core 2.0 et ultérieur) :</span><span class="sxs-lookup"><span data-stu-id="75f12-165">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
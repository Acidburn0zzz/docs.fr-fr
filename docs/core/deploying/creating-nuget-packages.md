---
title: Création d’un Package NuGet avec les outils multiplateformes
description: Découvrez comment créer un package NuGet avec la commande « dotnet pack ».
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 0be8d302568bc08d2c3dacfdf5738eff4b97d4b2
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48848099"
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="a8023-103">Création d’un Package NuGet avec les outils multiplateformes</span><span class="sxs-lookup"><span data-stu-id="a8023-103">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="a8023-104">Voici des exemples de ligne de commande avec Unix.</span><span class="sxs-lookup"><span data-stu-id="a8023-104">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="a8023-105">La commande `dotnet pack` montrée ici fonctionne de la même façon sur Windows.</span><span class="sxs-lookup"><span data-stu-id="a8023-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="a8023-106">Pour .NET Core 1.0, les bibliothèques doivent être distribuées sous forme de packages NuGet.</span><span class="sxs-lookup"><span data-stu-id="a8023-106">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="a8023-107">Il s’agit en fait de la façon dont toutes les bibliothèques .NET Standard sont distribuées et consommées.</span><span class="sxs-lookup"><span data-stu-id="a8023-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="a8023-108">Cette opération est plus facile avec la commande `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="a8023-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="a8023-109">Imaginez que vous venez d’écrire une nouvelle bibliothèque que vous voulez distribuer via NuGet.</span><span class="sxs-lookup"><span data-stu-id="a8023-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="a8023-110">Pour cela, vous pouvez créer un package NuGet avec les outils multiplateformes.</span><span class="sxs-lookup"><span data-stu-id="a8023-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="a8023-111">L’exemple suivant suppose une bibliothèque nommée **SuperAwesomeLibrary** ciblant `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="a8023-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="a8023-112">Si vous avez des dépendances transitives (c’est-à-dire un projet qui dépend d’un autre package), veillez à restaurer les packages de l’ensemble de votre solution avec la commande `dotnet restore` avant de créer un package NuGet.</span><span class="sxs-lookup"><span data-stu-id="a8023-112">If you have transitive dependencies; that is, a project which depends on another package, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="a8023-113">Si vous ne le faites pas, la commande `dotnet pack` ne fonctionne pas correctement.</span><span class="sxs-lookup"><span data-stu-id="a8023-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


<span data-ttu-id="a8023-114">Après avoir vérifié que les packages sont restaurés, vous pouvez accéder au répertoire où se trouve une bibliothèque :</span><span class="sxs-lookup"><span data-stu-id="a8023-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="a8023-115">Il s’agit d’une seule commande à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="a8023-115">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="a8023-116">Votre dossier `/bin/Debug` doit maintenant ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="a8023-116">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="a8023-117">Notez que ceci génère un package qui peut être débogué.</span><span class="sxs-lookup"><span data-stu-id="a8023-117">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="a8023-118">Si vous voulez générer un package NuGet avec des fichiers binaires compilés, tout ce que vous devez faire est d’ajouter le commutateur `-c`/`--configuration` et d’utiliser `release` comme argument.</span><span class="sxs-lookup"><span data-stu-id="a8023-118">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="a8023-119">Votre dossier `/bin` a désormais un dossier `release` contenant votre package NuGet avec les fichiers binaires compilés :</span><span class="sxs-lookup"><span data-stu-id="a8023-119">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="a8023-120">Vous avez maintenant les fichiers nécessaires pour publier un package NuGet !</span><span class="sxs-lookup"><span data-stu-id="a8023-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="a8023-121">Ne confondez pas `dotnet pack` et `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="a8023-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="a8023-122">Il est important de noter qu’à aucun moment, la commande `dotnet publish` n’est impliquée.</span><span class="sxs-lookup"><span data-stu-id="a8023-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="a8023-123">La commande `dotnet publish` est destinée au déploiement des applications avec toutes leurs dépendances dans le même regroupement, et non pas à la génération d’un package NuGet à distribuer et à consommer via NuGet.</span><span class="sxs-lookup"><span data-stu-id="a8023-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

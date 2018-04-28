---
title: Commande dotnet nuget locals - Interface CLI .NET Core
description: La commande dotnet nuget locals efface ou répertorie les ressources NuGet locales telles que le cache de requête http, le cache temporaire ou le dossier de packages globaux à l’échelle de l’ordinateur.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 1dfa50ff0971a82b3f6aafd86492fd57d8cf6a82
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="e55ae-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="e55ae-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e55ae-104">Name</span><span class="sxs-lookup"><span data-stu-id="e55ae-104">Name</span></span>

<span data-ttu-id="e55ae-105">`dotnet nuget locals` - Efface ou liste les ressources NuGet locales.</span><span class="sxs-lookup"><span data-stu-id="e55ae-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e55ae-106">Résumé</span><span class="sxs-lookup"><span data-stu-id="e55ae-106">Synopsis</span></span>

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="e55ae-107">Description</span><span class="sxs-lookup"><span data-stu-id="e55ae-107">Description</span></span>

<span data-ttu-id="e55ae-108">La commande `dotnet nuget locals` efface ou liste les ressources NuGet locales dans le cache de requête HTTP, le cache temporaire ou le dossier des packages globaux à l’échelle de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e55ae-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="e55ae-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="e55ae-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="e55ae-110">Une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e55ae-110">One of the following values:</span></span>

* <span data-ttu-id="e55ae-111">`all` : indique que l’opération spécifiée est appliquée à tous les types de cache : le cache de requête HTTP, le cache des packages globaux et le cache temporaire.</span><span class="sxs-lookup"><span data-stu-id="e55ae-111">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="e55ae-112">`http-cache` : indique que l’opération spécifiée est appliquée uniquement au cache de requête HTTP.</span><span class="sxs-lookup"><span data-stu-id="e55ae-112">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="e55ae-113">Les autres emplacements de cache ne sont pas affectés.</span><span class="sxs-lookup"><span data-stu-id="e55ae-113">The other cache locations are not affected.</span></span>
* <span data-ttu-id="e55ae-114">`global-packages` : indique que l’opération spécifiée est appliquée uniquement au cache des packages globaux.</span><span class="sxs-lookup"><span data-stu-id="e55ae-114">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="e55ae-115">Les autres emplacements de cache ne sont pas affectés.</span><span class="sxs-lookup"><span data-stu-id="e55ae-115">The other cache locations are not affected.</span></span>
* <span data-ttu-id="e55ae-116">`temp` : indique que l’opération spécifiée est appliquée uniquement au cache temporaire.</span><span class="sxs-lookup"><span data-stu-id="e55ae-116">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="e55ae-117">Les autres emplacements de cache ne sont pas affectés.</span><span class="sxs-lookup"><span data-stu-id="e55ae-117">The other cache locations are not affected.</span></span>

## <a name="options"></a><span data-ttu-id="e55ae-118">Options</span><span class="sxs-lookup"><span data-stu-id="e55ae-118">Options</span></span>

`-h|--help`

<span data-ttu-id="e55ae-119">Affiche une aide brève pour la commande.</span><span class="sxs-lookup"><span data-stu-id="e55ae-119">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="e55ae-120">L’option clear effectue une opération d’effacement sur le type de cache spécifié.</span><span class="sxs-lookup"><span data-stu-id="e55ae-120">The clear option performs a clear operation on the specified cache type.</span></span> <span data-ttu-id="e55ae-121">Le contenu des répertoires de cache est supprimé de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="e55ae-121">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="e55ae-122">Le groupe ou l’utilisateur qui effectue l’opération doit disposer de droits sur les fichiers des répertoires de cache.</span><span class="sxs-lookup"><span data-stu-id="e55ae-122">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="e55ae-123">Sinon, une erreur s’affiche, indiquant les fichiers ou dossiers qui n’ont pas été effacés.</span><span class="sxs-lookup"><span data-stu-id="e55ae-123">If not, an error is displayed indicating the files/folders which were not cleared.</span></span>

`-l|--list`

<span data-ttu-id="e55ae-124">L’option list est utilisée pour afficher l’emplacement du type de cache spécifié.</span><span class="sxs-lookup"><span data-stu-id="e55ae-124">The list option is used to display the location of the specified cache type.</span></span> 

`--force-english-output`

<span data-ttu-id="e55ae-125">Oblige la sortie de la ligne de commande à être en anglais.</span><span class="sxs-lookup"><span data-stu-id="e55ae-125">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="e55ae-126">Exemples</span><span class="sxs-lookup"><span data-stu-id="e55ae-126">Examples</span></span>

<span data-ttu-id="e55ae-127">Afficher les chemins d’accès de tous les répertoires de cache local (le répertoire du cache HTTP, le répertoire du cache des packages globaux et le répertoire du cache temporaire) :</span><span class="sxs-lookup"><span data-stu-id="e55ae-127">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="e55ae-128">Affiche le chemin du répertoire du cache http local :</span><span class="sxs-lookup"><span data-stu-id="e55ae-128">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="e55ae-129">Effacer tous les fichiers de tous les répertoires de cache local (le répertoire du cache HTTP, le répertoire du cache des packages globaux et le répertoire du cache temporaire) :</span><span class="sxs-lookup"><span data-stu-id="e55ae-129">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="e55ae-130">Effacer tous les fichiers du répertoire du cache des packages globaux local :</span><span class="sxs-lookup"><span data-stu-id="e55ae-130">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="e55ae-131">Effacer tous les fichiers du répertoire du cache temporaire local :</span><span class="sxs-lookup"><span data-stu-id="e55ae-131">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="e55ae-132">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="e55ae-132">Troubleshooting</span></span>

<span data-ttu-id="e55ae-133">Pour plus d’informations sur les problèmes et erreurs courants liés à l’utilisation de la commande `dotnet nuget locals`, consultez la page [Gestion du cache NuGet](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="e55ae-133">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
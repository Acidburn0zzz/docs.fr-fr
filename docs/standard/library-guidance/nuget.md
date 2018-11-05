---
title: Bibliothèques NuGet et .NET
description: Meilleures pratiques recommandées pour l’empaquetage avec des bibliothèques NuGet pour .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 479d1786c232ef1f843877169954e847453681c9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185618"
---
# <a name="nuget"></a>NuGet

Gestionnaire de packages pour l’écosystème .NET, NuGet est le principal moyen permettant aux développeurs de découvrir et d’obtenir des bibliothèques .NET open source. [NuGet.org](https://www.nuget.org/), un service gratuit fourni par Microsoft pour l’hébergement de packages NuGet, est l’hôte principal pour les packages NuGet publiques, mais vous pouvez publier dans des services NuGet personnalisés tels que [MyGet](https://www.myget.org/) et [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Créer un package NuGet

Un package NuGet (`*.nupkg`) est un fichier zip qui contient des assemblys .NET et les métadonnées associées.

Il existe deux façons principales de créer un package NuGet. La plus récente et recommandée consiste à créer un package à partir d’un projet de style SDK (fichier projet dont le contenu commence par `<Project Sdk="Microsoft.NET.Sdk">`). Les assemblys et cibles sont automatiquement ajoutés au package et les métadonnées restantes sont ajoutées au fichier MSBuild, notamment le nom du package et le numéro de version. La compilation avec la commande [`dotnet pack`](../../core/tools/dotnet-pack.md) génère un fichier `*.nupkg` au lieu d’assemblys.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

L’ancienne méthode de création d’un package NuGet utilise un fichier `*.nuspec` et l’outil de ligne de commande `nuget.exe`. Un fichier nuspec vous donne plus de contrôle, mais vous devez spécifier soigneusement les assemblys et les cibles à inclure dans le package NuGet final. Il est facile de commettre une erreur ou d’oublier de mettre à jour le fichier nuspec lors des modifications. Un fichier nuspec offre l’avantage de vous permettre de créer des packages NuGet pour les infrastructures qui ne gèrent pas encore un fichier projet de style SDK.

**✔️ À ENVISAGER** : Utiliser un fichier projet de style SDK pour créer le package NuGet.

**✔️ À ENVISAGER** : Configurer SourceLink pour ajouter les métadonnées de contrôle source à vos assemblys et au package NuGet.

## <a name="package-dependencies"></a>Dépendances de package

Les dépendances de package NuGet sont traitées en détail dans l’article sur les [dépendances](./dependencies.md).

## <a name="important-nuget-package-metadata"></a>Métadonnées importantes de package NuGet

Un package NuGet prend en charge plusieurs [propriétés de métadonnées](/nuget/reference/nuspec). Le tableau suivant indique les principales métadonnées que chaque projet open source doit fournir :

| Nom de la propriété MSBuild              | Nom nuspec              | Description  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Identificateur du package. Un préfixe de l’identificateur peut être réservé s’il répond aux [critères](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | Version du package NuGet. Pour plus d’informations, consultez [Version du package NuGet](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Un titre convivial du package. Ce champ est défini sur `PackageId` par défaut.             |
| `Description`                      | `description`              | Longue description du package affiché dans l’interface utilisateur.             |
| `Authors`                          | `authors`                  | Liste séparée par des virgules des auteurs de packages, qui correspondent aux noms de profil sur nuget.org.             |
| `PackageTags`                      | `tags`                     | Liste délimitée par des espaces des balises et mots clés qui décrivent le package. Les balises sont utilisées lors de la recherche des packages.             |
| `PackageIconUrl`                   | `iconUrl`                  | URL d’une image à utiliser comme icône pour le package. L’URL doit être de type HTTPS et l’image doit être au format 64 x 64, avec un arrière-plan transparent.             |
| `PackageProjectUrl`                | `projectUrl`               | Une URL pour la page d'accueil du projet ou le référentiel source.             |
| `PackageLicenseUrl`                | `licenseUrl`               | Une URL vers la licence du projet. Peut être l’URL vers le fichier `LICENSE` dans le contrôle de code source.             |

**✔️ À ENVISAGER** : Choisir un nom de package NuGet avec un préfixe qui répond à la réservation du préfixe des [critères](/nuget/reference/id-prefix-reservation) NuGet.

**✔️ À ENVISAGER** : Utiliser le fichier `LICENSE` dans le contrôle de code source en tant que `LicenseUrl`. Par exemple, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).

> [!IMPORTANT]
> Par défaut, un projet sans licence possède un [copyright exclusif](https://choosealicense.com/no-permission/), ce qui empêche d’autres personnes de l’utiliser.

**✔️ À FAIRE** : Utiliser une href HTTPS pour l’icône de package.

> Des sites comme NuGet.org fonctionnent avec HTTPS et l’affichage d’une image non-HTTPS créera un avertissement de contenu mixte.

**✔️ À FAIRE** : Utiliser une image d’icône de package au format 64 x 64 et avec un arrière-plan transparent pour optimiser l’affichage.

## <a name="pre-release-packages"></a>Packages de préversion

Les packages NuGet avec un suffixe de version sont considérés comme des [préversions](/nuget/create-packages/prerelease-packages). Par défaut, l’interface utilisateur du Gestionnaire de package NuGet affiche des versions stables, sauf si un utilisateur choisit des packages en préversion, ce qui rend ces packages en préversion idéaux pour les tests utilisateur limités.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Un package stable ne peut pas dépendre d’un package en préversion. Votre package doit être en préversion ou dépendre d’une version stable antérieure.

![Dépendance d’un package NuGet en préversion](./media/nuget/nuget-prerelease-package.png "Dépendance d’un package NuGet en préversion")

**✔️ À FAIRE** : Publier un package en préversion lors de tests, de la prévisualisation ou de l’expérimentation.

**✔️ À FAIRE** : Publier un package stable lorsqu’il est prêt afin que d’autres packages stables puissent y faire référence.

## <a name="symbol-packages"></a>Packages de symboles

Les fichiers de symboles (`*.pdb`) sont produites par le compilateur .NET en même temps que les assemblys. Comme les fichiers de symboles mappent les emplacements d’exécution au code source d’origine, vous pouvez parcourir le code source en cours d’exécution à l’aide d’un débogueur. NuGet prend en charge la [génération d’un package de symboles distinct](/nuget/create-packages/symbol-packages) contenant des fichiers de symboles ainsi que le package principal contenant les assemblys .NET. Dans le concept des packages de symboles, ces packages sont hébergés sur un serveur de symboles et téléchargés à la demande uniquement par un outil tel que Visual Studio.

Actuellement, l’hôte publique principale pour les symboles - [SymbolSource](http://www.symbolsource.org/) - ne prend en charge les nouveaux [fichiers de symboles portables](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) créés par les projets de style SDK et les packages de symboles ne sont pas utiles. Jusqu'à ce qu’un hôte recommandé pour les packages de symboles soit désigné, les fichiers de symboles peuvent être incorporés dans le package NuGet principal. Si vous générez votre package NuGet à l’aide d’un projet de style SDK, vous pouvez incorporer les fichiers de symboles en définissant la propriété `AllowedOutputExtensionsInPackageBuildOutputFolder` : 

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

**✔️ À ENVISAGER** : Incorporer des fichiers de symboles dans le package NuGet principal.

**❌ À ÉVITER** : Créer un package de symboles contenant des fichiers de symboles.

>[!div class="step-by-step"]
[Précédent](./strong-naming.md)
[Suivant](./dependencies.md)
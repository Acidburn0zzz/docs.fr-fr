---
title: Guide .NET Core
description: .NET Core est une implémentation modulaire à hautes performances de .NET pour la création d’applications Windows, Linux et Mac. Découvrez .NET Core pour démarrer.
author: richlander
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 79a0c09074159160dd01b0c7970612f7058cc3fc
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920621"
---
# <a name="net-core-guide"></a>Guide .NET Core

[.NET Core](about.md) est une plateforme de développement généraliste [open source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) qui est tenue à jour par Microsoft et la communauté .NET sur [GitHub](https://github.com/dotnet/core). Cette multiplateforme prend en charge Windows, macOS et Linux. Elle permet de générer des applications destinées à des appareils, au cloud et à l’Internet des objets.

Consultez [À propos de .NET Core](about.md) pour en savoir plus sur .NET Core, notamment ses caractéristiques, les langues et frameworks pris en charge et les API clés.

Consultez les [Tutoriels .NET Core](tutorials/index.md) pour apprendre à créer une application .NET Core simple. Il suffit de quelques minutes pour créer votre première application et la rendre opérationnelle. Si vous souhaitez tester .NET Core dans votre navigateur, consultez le tutoriel en ligne [Nombres en C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml).

## <a name="download-net-core-22"></a>Télécharger .NET Core 2.2

Téléchargez le kit [SDK .NET Core 2.2](https://www.microsoft.com/net/download) pour tester .NET Core sur votre ordinateur Windows, macOS ou Linux. Visitez [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) si vous préférez utiliser des conteneurs Docker.

Toutes les versions de .NET Core sont disponibles sur [Téléchargements de .NET Core](https://www.microsoft.com/net/download/archives) si vous recherchez une autre version de .NET Core.

## <a name="net-core-22"></a>.NET Core 2.2

La dernière version est [.NET Core 2.2](whats-new/dotnet-core-2-2.md). Nouvelles fonctionnalités : déploiements dépendants du framework, hooks de démarrage, authentification AAD avec Azure SQL et prise en charge de Windows ARM32.

## <a name="create-your-first-application"></a>Créer votre première application

Après avoir installé le SDK .NET Core, ouvrez une invite de commandes. Tapez les commandes `dotnet` suivantes pour créer et exécuter une application C#.

```console
dotnet new console
dotnet run
```

Vous devez voir la sortie suivante :

```console
Hello World!
```

## <a name="support"></a>Support

.NET Core est [pris en charge par Microsoft](https://www.microsoft.com/net/support/policy) sur Windows, macOS et Linux. La sécurité et la qualité sont mises à jour plusieurs fois par an, en général, tous les mois.

Les distributions binaires .NET Core sont générées et testées sur des serveurs managés par Microsoft dans Azure et elles sont prises en charge comme tous les produits Microsoft.

[Red Hat prend en charge .NET Core](http://redhatloves.net/) sur Red Hat Enterprise Linux (RHEL). Red Hat génère .NET Core à partir de la source et le rend disponible dans les [collections logicielles Red Hat](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat et Microsoft collaborent pour s’assurer que .NET Core fonctionne correctement sur RHEL.

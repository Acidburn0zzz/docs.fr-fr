---
title: Commande dotnet nuget delete - Interface CLI .NET Core
description: La commande nuget-dotnet-delete supprime ou retire un package du serveur.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 1e81501d526ae92336b808f98c7c192b55e89f98
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet nuget delete` -Supprime ou retire un package du serveur.

## <a name="synopsis"></a>Résumé

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a>Description

La commande `dotnet nuget delete` supprime ou retire un package du serveur. Pour [nuget.org](https://www.nuget.org/), l’action consiste à supprimer le package de la liste.

## <a name="arguments"></a>Arguments

`PACKAGE_NAME`

Package à supprimer.

`PACKAGE_VERSION`

Version du package à supprimer.

## <a name="options"></a>Options

`-h|--help`

Affiche une aide brève pour la commande.

`-s|--source <SOURCE>`

Spécifie l’URL du serveur. Les URL prises en charge pour nuget.org incluent `http://www.nuget.org`, `http://www.nuget.org/api/v3` et `http://www.nuget.org/api/v2/package`. Pour les flux privés, remplacez le nom d’hôte (par exemple, `%hostname%/api/v3`).

`--non-interactive`

Ne demande pas de saisie ou de confirmation de la part de l’utilisateur.

`-k|--api-key <API_KEY>`

Clé d’API pour le serveur.

`--force-english-output`

Oblige la sortie de la ligne de commande à être en anglais.

## <a name="examples"></a>Exemples

Supprime la version 1.0 du package `Microsoft.AspNetCore.Mvc` :

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

Supprime la version 1.0 du package `Microsoft.AspNetCore.Mvc` sans inviter l’utilisateur à fournir ses informations d’identification ou d’autres données :

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
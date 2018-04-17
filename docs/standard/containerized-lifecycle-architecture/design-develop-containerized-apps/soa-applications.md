---
title: Applications SOA
description: Cycle de vie des applications Docker en conteneur avec la plateforme et les outils Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 48dc0f038cee8ddc9555881f2143b566df223a04
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="soa-applications"></a><span data-ttu-id="64a39-103">Applications SOA</span><span class="sxs-lookup"><span data-stu-id="64a39-103">SOA applications</span></span>

<span data-ttu-id="64a39-104">SOA a été un utilisation excessive du terme et vocation de nombreuses différentes choses pour différentes personnes.</span><span class="sxs-lookup"><span data-stu-id="64a39-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="64a39-105">Mais au minimum et comme dénominateur commun, SOA, ou l’orientation de service, moyenne structure l’architecture de votre application en décomposant il dans plusieurs services (généralement en tant que les services HTTP) qui peuvent être classées dans les différents types, tels que les sous-systèmes ou, dans d’autres cas, en tant que niveaux.</span><span class="sxs-lookup"><span data-stu-id="64a39-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="64a39-106">Aujourd'hui, vous pouvez déployer ces services en tant que conteneurs Docker, qui résout les problèmes liés au déploiement, car toutes les dépendances sont inclus dans l’image de conteneur.</span><span class="sxs-lookup"><span data-stu-id="64a39-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="64a39-107">Toutefois, lorsque vous devez SOA montée en puissance parallèle, vous pouvez rencontrer les défis si vous déployez des instances uniques en fonction de.</span><span class="sxs-lookup"><span data-stu-id="64a39-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="64a39-108">Il s’agit où une Docker clustering logiciel ou orchestrator vous aideront à.</span><span class="sxs-lookup"><span data-stu-id="64a39-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="64a39-109">Nous allons examiner cela plus en détail dans la section suivante lorsque nous examinons microservices approches.</span><span class="sxs-lookup"><span data-stu-id="64a39-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="64a39-110">À la fin de la journée, les solutions de clustering de conteneur sont utiles pour les deux une architecture SOA traditionnelle ou pour une architecture microservices plus avancée, dans laquelle chaque microservice possède son modèle de données.</span><span class="sxs-lookup"><span data-stu-id="64a39-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="64a39-111">De plus, grâce à plusieurs bases de données, vous également pouvez monter en charge la couche de données au lieu de travailler avec des bases de données monolithiques partagées par les services SOA.</span><span class="sxs-lookup"><span data-stu-id="64a39-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="64a39-112">Toutefois, la discussion sur la division des données est entièrement sur l’architecture et de conception.</span><span class="sxs-lookup"><span data-stu-id="64a39-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="64a39-113">[Précédente] (state-and-data-in-docker-applications.md) [suivant] (orchestrer-haute-évolutivité-availability.md)</span><span class="sxs-lookup"><span data-stu-id="64a39-113">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span></span>

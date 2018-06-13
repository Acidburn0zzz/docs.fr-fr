---
title: Applications SOA
description: Cycle de vie des applications Docker en conteneur avec la plateforme et les outils Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 37313c4eb437b6b7a362456a7d1ee3b3aecb6020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569416"
---
# <a name="soa-applications"></a>Applications SOA

SOA a été un utilisation excessive du terme et vocation de nombreuses différentes choses pour différentes personnes. Mais au minimum et comme dénominateur commun, SOA, ou l’orientation de service, moyenne structure l’architecture de votre application en décomposant il dans plusieurs services (généralement en tant que les services HTTP) qui peuvent être classées dans les différents types, tels que les sous-systèmes ou, dans d’autres cas, en tant que niveaux.

Aujourd'hui, vous pouvez déployer ces services en tant que conteneurs Docker, qui résout les problèmes liés au déploiement, car toutes les dépendances sont inclus dans l’image de conteneur. Toutefois, lorsque vous devez SOA montée en puissance parallèle, vous pouvez rencontrer les défis si vous déployez des instances uniques en fonction de. Il s’agit où une Docker clustering logiciel ou orchestrator vous aideront à. Nous allons examiner cela plus en détail dans la section suivante lorsque nous examinons microservices approches.

À la fin de la journée, les solutions de clustering de conteneur sont utiles pour les deux une architecture SOA traditionnelle ou pour une architecture microservices plus avancée, dans laquelle chaque microservice possède son modèle de données. De plus, grâce à plusieurs bases de données, vous également pouvez monter en charge la couche de données au lieu de travailler avec des bases de données monolithiques partagées par les services SOA. Toutefois, la discussion sur la division des données est entièrement sur l’architecture et de conception.


>[!div class="step-by-step"]
[Précédente] (state-and-data-in-docker-applications.md) [suivant] (orchestrer-haute-évolutivité-availability.md)

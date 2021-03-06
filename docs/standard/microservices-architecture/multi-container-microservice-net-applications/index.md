---
title: Conception et développement d’applications .NET à plusieurs conteneurs et basées sur des microservices
description: Architecture des Microservices .NET pour les applications .NET en conteneur | Comprendre l’architecture externe pour la conception et le développement d’applications .NET à plusieurs conteneurs et basées sur des microservices.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 3bbf746aa9c0b66a097b8c4df2964b5679342fd0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144141"
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a>Conception et développement d’applications .NET à plusieurs conteneurs et basées sur des microservices

*Le développement d’applications de microservice en conteneur signifie que vous générez des applications à plusieurs conteneurs. Toutefois, une application à plusieurs conteneurs pourrait aussi être plus simple, (par exemple, une application à trois niveaux) et non générée à l’aide d’une architecture de microservice.*

Précédemment, nous avons posé la question : « Docker est-il nécessaire pour générer une architecture de microservice ? » La réponse est clairement non. Docker est un activateur qui peut fournir des avantages significatifs, mais les conteneurs et Docker ne sont pas obligatoires pour les microservices. Par exemple, vous pouvez créer une application basée sur des microservices avec ou sans Docker en utilisant Azure Service Fabric, qui prend en charge des microservices exécutés en tant que processus simples ou en tant que conteneurs Docker.

Toutefois, si vous savez comment concevoir et développer une application basée sur des microservices qui est également basée sur des conteneurs Docker, vous serez en mesure de concevoir et développer n’importe quel modèle d’application plus simple. Par exemple, vous pouvez concevoir une application à trois niveaux qui requiert également une approche de plusieurs conteneurs. Par conséquent, et parce que les architectures de microservice sont une tendance majeure dans le milieu des conteneurs, cette section se concentre sur une implémentation d’architecture de microservice qui utilise des conteneurs Docker.

>[!div class="step-by-step"]
>[Précédent](../docker-application-development-process/docker-app-development-workflow.md)
>[Suivant](microservice-application-design.md)
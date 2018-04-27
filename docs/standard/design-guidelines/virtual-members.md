---
title: Membres virtuels
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1b7abe1dbeb7f4888dd8ee4001b410cc583935c4
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="virtual-members"></a>Membres virtuels
Membres virtuels peuvent être substituées, ce qui modifie le comportement de la sous-classe. Elles sont très similaires aux rappels en termes de l’extensibilité, qu'ils fournissent, mais ils sont mieux en termes de performances de l’exécution et la consommation de mémoire. En outre, les membres virtuels se sentent plus naturels dans les scénarios qui requièrent la création d’un spécial type d’un type existant (spécialisation).  
  
 Membres virtuels plus performants que les rappels et les événements, mais n’effectuent pas de meilleures performances que les méthodes non virtuelles.  
  
 Le principal inconvénient des membres virtuels est que le comportement d’un membre virtuel peut uniquement être modifié au moment de la compilation. Le comportement d’un rappel peut être modifié lors de l’exécution.  
  
 Les membres virtuels, comme des rappels (et peut-être plusieurs rappels), sont coûteuses à concevoir, tester et mettre à jour, car un appel à un membre virtuel peut être substitué de manière imprévisible et peut exécuter du code arbitraire. En outre, beaucoup plus d’effort est généralement requis pour définir clairement le contrat de membres virtuels, ce qui augmente le coût de la conception et à les documenter.  
  
 **X ne sont pas** rendre les membres virtuels sauf si vous avez une bonne raison à cela et que vous connaissez tous les coûts liés à la conception, de test et de maintenance des membres virtuels.  
  
 Membres virtuels sont moins indulgent en termes de modifications qui peuvent être mises sans rompre la compatibilité. En outre, ils sont plus lentes que les membres non virtuelle, principalement parce que les appels aux membres virtuels ne sont pas inline.  
  
 **✓ Envisagez** limiter l’extensibilité à celles qui sont absolument nécessaires.  
  
 **✓ FAIRE** accessibilité protégée préférer une accessibilité publique pour les membres virtuels. Les membres publics doivent fournir l’extensibilité (si nécessaire) en appelant un membre virtuel protégé.  
  
 Les membres publics d’une classe doivent fournir l’ensemble approprié de fonctionnalités pour les consommateurs directs de cette classe. Membres virtuels sont conçus pour être substitué dans les sous-classes et accessibilité protégée est un excellent moyen de l’étendue de tous les points d’extensibilité virtuel où elles peuvent être utilisées.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*  
  
 *Réimprimées avec l’autorisation de Pearson éducation, Inc. à partir de [règles de conception d’infrastructure : Conventions, idiomes et des modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement Microsoft Windows.*  
  
## <a name="see-also"></a>Voir aussi  
 [Règles de conception de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Conception en vue de l’extensibilité](../../../docs/standard/design-guidelines/designing-for-extensibility.md)

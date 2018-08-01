---
title: Sceller
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7202e10e41b9f114f42a4502ee2e6694bf3821
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573735"
---
# <a name="sealing"></a>Sceller
Une des fonctionnalités des infrastructures d’orientée objet est que les développeurs peuvent étendre et personnalisez-les de manières inattendues par les concepteurs de framework. Il s’agit la puissance et le risque de conception extensible. Lorsque vous concevez votre infrastructure, il est donc très important de concevoir soigneusement pour l’extensibilité lorsqu’il est nécessaire et pour limiter l’extensibilité lorsqu’il est dangereux.  
  
 Scellement d’un mécanisme puissant qui empêche d’extensibilité. Vous pouvez sceller à la classe ou des membres individuels. Le fait de sceller une classe d’empêche les utilisateurs d’hériter de la classe. Le fait de sceller un membre d’empêche les utilisateurs de substituer un membre particulier.  
  
 **X DO NOT** sceller des classes sans avoir une bonne raison de le faire.  
  
 Le fait de sceller une classe, car vous ne savez pas un scénario d’extensibilité n’est pas une bonne raison. Les utilisateurs de Framework tels que d’hériter des classes pour différentes raisons identifiable, telles que l’ajout de membres de commodité. Consultez [Classes Unsealed](../../../docs/standard/design-guidelines/unsealed-classes.md) pour obtenir des exemples de raisons identifiable les utilisateurs souhaitent hériter d’un type.  
  
 Raisons pour sceller une classe sont les suivantes :  
  
-   La classe est une classe statique. Consultez [conception d’une classe statique](../../../docs/standard/design-guidelines/static-class.md).  
  
-   La classe stocke des secrets de sécurité sensibles dans des membres protégés hérités.  
  
-   La classe hérite de nombreux membres virtuels et le coût de leur scellement individuellement serait dépassent les avantages de la classe non scellés.  
  
-   La classe est un attribut qui nécessite la recherche d’exécution très rapide. Les attributs sealed ont des niveaux de performance légèrement plus élevées que celles non scellés. consultez [attributs](../../../docs/standard/design-guidelines/attributes.md).  
  
 **X DO NOT** déclarer les membres virtuels ou protégés sur les types sealed.  
  
 Par définition, les types sealed ne peut pas être héritées. Cela signifie que les membres protégés sur les types sealed ne peut pas être appelées, et les méthodes virtuelles sur les types sealed ne peut pas être substituées.  
  
 **✓ CONSIDER** sceller les membres que vous substituez.  
  
 Des problèmes qui peuvent résulter de présentation des membres virtuels (présentés dans [membres virtuels](../../../docs/standard/design-guidelines/virtual-members.md)) s’appliquent aux substitutions, bien qu’à un degré moindre. Le fait de sceller un remplacement vous protège ces problèmes, en commençant à partir de ce point dans la hiérarchie d’héritage.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*  
  
 *Réimprimées avec l’autorisation de Pearson éducation, Inc. à partir de [règles de conception d’infrastructure : Conventions, idiomes et des modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement Microsoft Windows.*  
  
## <a name="see-also"></a>Voir aussi  
 [Règles de conception de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Conception en vue de l’extensibilité](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Classes unsealed](../../../docs/standard/design-guidelines/unsealed-classes.md)

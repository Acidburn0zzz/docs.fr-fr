---
title: Instructions de conception des membres
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c04b431224a1d4f03e85397b854a52856e114e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="member-design-guidelines"></a>Instructions de conception des membres
Méthodes, propriétés, événements, constructeurs et les champs sont collectivement en tant que membres. Les membres sont finalement les moyens par lesquels les fonctionnalités de framework sont exposées aux utilisateurs finaux d’une infrastructure.  
  
 Les membres peuvent être virtuel ou non virtuelle, concret ou abstrait, statique ou instance et peuvent avoir plusieurs étendues différentes d’accessibilité. Tous les différents fournit incroyable simplicité, mais en même temps requiert soins par le Concepteur de framework.  
  
 Ce chapitre propose des conseils de base qui doivent être suivies lors de la conception des membres de n’importe quel type.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Surcharge de membre](../../../docs/standard/design-guidelines/member-overloading.md)  
 [Conception des propriétés](../../../docs/standard/design-guidelines/property.md)  
 [Conception de constructeurs](../../../docs/standard/design-guidelines/constructor.md)  
 [Conception d’événements](../../../docs/standard/design-guidelines/event.md)  
 [Conception de champs](../../../docs/standard/design-guidelines/field.md)  
 [Méthodes d’extension](../../../docs/standard/design-guidelines/extension-methods.md)  
 [Surcharges d’opérateurs](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [Conception de paramètres](../../../docs/standard/design-guidelines/parameter-design.md)  
 *Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*  
  
 *Réimprimées avec l’autorisation de Pearson éducation, Inc. à partir de [règles de conception d’infrastructure : Conventions, idiomes et des modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement Microsoft Windows.*  
  
## <a name="see-also"></a>Voir aussi  
 [Règles de conception de .NET Framework](../../../docs/standard/design-guidelines/index.md)

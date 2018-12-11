---
title: Tableaux
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: KrzysztofCwalina
ms.openlocfilehash: d0332591be7659aafb5b3169f92c81d47d519dc2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127561"
---
# <a name="arrays"></a>Tableaux
**✓ DO** préférez l’utilisation de collections sur des tableaux dans les API publiques. Le [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section fournit des détails sur le choix entre les collections et tableaux.  
  
 **X DO NOT** utiliser les champs de tableau en lecture seule. Le champ lui-même est en lecture seule et ne peut pas être modifié, mais les éléments dans le tableau peuvent être modifiés.  
  
 **✓ CONSIDER** à l’aide de tableaux en escalier à la place de tableaux multidimensionnels.  
  
 Un tableau en escalier est un tableau avec des éléments qui sont également des tableaux. Les tableaux qui composent les éléments peuvent être de différentes tailles, ce qui conduit à un gaspillage d’espace pour certains jeux de données (par exemple, une matrice éparse) par rapport aux tableaux multidimensionnels. En outre, le CLR permet d’optimiser les opérations d’index sur des tableaux en escalier, afin qu’ils peuvent exposer les meilleures performances d’exécution dans certains scénarios.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*  
  
 *Réimprimé avec l’autorisation de Pearson éducation, Inc. à partir de [instructions de conception Framework : Conventions, les idiomes et les modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement de Microsoft Windows.*  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Array>  
- [Règles de conception de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Indications relatives à l’utilisation](../../../docs/standard/design-guidelines/usage-guidelines.md)

---
title: Les événements des variables WithEvents partagées ne peuvent pas être gérés par des méthodes non partagées
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 2b32043898986b3e3e68fab18c5f907843d7691c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838649"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Les événements des variables WithEvents partagées ne peuvent pas être gérés par des méthodes non partagées
Une variable déclarée avec le `Shared` modificateur est une variable partagée. Une variable partagée identifie exactement un emplacement de stockage. Une variable déclarée avec le `WithEvents` modificateur garantit que le type auquel appartient la variable gère l’ensemble de la variable déclenche des événements. Lorsqu’une valeur est attribuée à la variable, la propriété créée par le `WithEvents` déclaration déconnecte tout gestionnaire d’événements existant et raccorde le nouveau gestionnaire d’événements via le `Add` (méthode).  
  
 **ID d’erreur :** BC30594  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Déclarez votre gestionnaire d’événements `Shared`.  
  
## <a name="see-also"></a>Voir aussi

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)

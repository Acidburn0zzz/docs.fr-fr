---
title: "Procédure : Utiliser un dictionnaire pour stocker des instances d'événements - Guide de programmation C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 8f0284c5637890f35642346880d035619bc0e1e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560059"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Procédure : Utiliser un dictionnaire pour stocker des instances d'événements (Guide de programmation C#)
Une des façons d’utiliser `accessor-declarations` consiste à exposer un grand nombre d’événements sans allouer de champ à chaque événement, mais en utilisant à la place un dictionnaire pour stocker les instances d’événements. Cette méthode n’est utile qu’en présence d’un grand nombre d’événements dont la plupart ne seront pas implémentés.  
  
## <a name="example"></a>Exemple  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>Voir aussi

- [Guide de programmation C#](../../../csharp/programming-guide/index.md)
- [Événements](../../../csharp/programming-guide/events/index.md)
- [Délégués](../../../csharp/programming-guide/delegates/index.md)

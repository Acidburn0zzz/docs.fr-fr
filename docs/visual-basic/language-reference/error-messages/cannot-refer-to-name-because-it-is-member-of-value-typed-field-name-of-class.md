---
title: Impossible de faire référence à '<name>', car il est membre du champ de valeurs '<name>' de la classe '<classname>', qui a 'System.MarshalByRefObject' comme classe de base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: 78b0a3131b6e77ed257f200523ecebd4dfce3691
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316542"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a>Ne peut pas faire référence à '\<nom >', car il est membre du champ de valeurs '\<nom >' de la classe\<nom_classe >' qui a 'System.MarshalByRefObject' comme classe de base
Le `System.MarshalByRefObject` classe permet aux applications qui prennent en charge l’accès à distance à des objets entre les limites du domaine d’application. Types doivent hériter la `MarshalByRejectObject` classe lorsque le type est utilisé au-delà des limites du domaine d’application. L’état de l’objet ne doit pas être copié, car les membres de l’objet ne sont pas utilisables en dehors du domaine d’application dans lequel ils ont été créés.  
  
 **ID d’erreur :** BC30310  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1. Vérification de la référence de s’assurer que le membre fait référence est valide.  
  
2. Qualifier explicitement le membre avec le `Me` mot clé.  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.MarshalByRefObject>
- [Dim, instruction](../../../visual-basic/language-reference/statements/dim-statement.md)

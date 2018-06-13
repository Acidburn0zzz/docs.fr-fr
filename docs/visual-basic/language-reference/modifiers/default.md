---
title: Default (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: 555e15110c7af501de05d1f395a72ca4b7800054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595139"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifie une propriété comme propriété par défaut pour sa classe, structure ou interface.  
  
## <a name="remarks"></a>Notes  
 Une classe, structure ou interface peut désigner l’une de ses propriétés comme le *propriété par défaut*, à condition que la propriété prend au moins un paramètre. Si le code fait référence à une classe ou structure sans spécifier un membre, Visual Basic résout cette référence à la propriété par défaut.  
  
 Propriétés par défaut peuvent entraîner une légère réduction de caractères de code source, mais elles peuvent rendre votre code plus difficile à lire. Si le code appelant n’est pas familiarisé avec votre classe ou structure, lorsqu’il fait référence au nom de classe ou structure il ne peut pas être certain que cette référence accède à la classe ou structure elle-même ou une propriété par défaut. Cela peut entraîner des erreurs du compilateur ou des erreurs de logique d’exécution subtiles.  
  
 Vous pouvez légèrement réduire le risque d’erreurs de propriété par défaut en utilisant toujours le [Option Strict, instruction](../../../visual-basic/language-reference/statements/option-strict-statement.md) pour définir le contrôle de type du compilateur `On`.  
  
 Si vous envisagez d’utiliser une classe prédéfinie ou une structure dans votre code, vous devez déterminer si elle a une propriété par défaut et si tel est le cas, ce que son nom est.  
  
 En raison de ces inconvénients, vous devez envisager de ne pas définir de propriétés par défaut. Pour une meilleure lisibilité du code, vous devez également envisager de toujours faire explicitement référence à toutes les propriétés, même les propriétés par défaut.  
  
 Le `Default` modificateur peut être utilisé dans ce contexte :  
  
 [Property (instruction)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : déclarer et appeler une propriété par défaut en Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [Mots clés](../../../visual-basic/language-reference/keywords/index.md)

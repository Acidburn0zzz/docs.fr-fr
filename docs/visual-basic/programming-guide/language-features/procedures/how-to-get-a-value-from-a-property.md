---
title: "Comment : obtenir une valeur d'une propriété (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 9f97669e8d18e7fc633cb0e691d973a611a8cea0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Comment : obtenir une valeur d'une propriété (Visual Basic)
Y compris le nom de propriété dans une expression permet de récupérer une valeur de propriété.  
  
 La propriété `Get` procédure récupère la valeur, mais vous ne l’appelez pas explicitement par son nom. Vous utilisez la propriété comme vous utiliseriez une variable. Visual Basic effectue les appels aux procédures de la propriété.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Pour récupérer une valeur d’une propriété  
  
1.  Utilisez le nom de propriété dans une expression de la même façon que vous utiliseriez un nom de variable. Vous pouvez utiliser une propriété partout où vous pouvez utiliser une variable ou une constante.  
  
     - ou -  
  
     Utilisez le nom de propriété suivant égaux (`=`) connectez-vous à une instruction d’assignation.  
  
     L’exemple suivant lit la valeur de Visual Basic `Now` propriété implicitement en appelant son `Get` procédure.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  Si la propriété accepte des arguments, faites suivre le nom de propriété avec des parenthèses pour encadrer la liste d’arguments. S’il n’y a pas d’arguments, vous pouvez éventuellement omettre les parenthèses.  
  
3.  Placez les arguments dans la liste d’arguments entre parenthèses, séparées par des virgules. Assurez-vous de que fournir les arguments dans le même ordre que la propriété définit les paramètres correspondants.  
  
 La valeur de la propriété participe à l’expression comme une variable ou constante serait, ou il est stocké dans la variable ou propriété sur le côté gauche de l’instruction d’assignation.  
  
## <a name="see-also"></a>Voir aussi  
 [Procédures](./index.md)  
 [Procédures de propriété](./property-procedures.md)  
 [Paramètres et arguments d’une procédure](./procedure-parameters-and-arguments.md)  
 [Property (instruction)](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Différences entre les propriétés et les Variables en Visual Basic](./differences-between-properties-and-variables.md)  
 [Guide pratique : créer une propriété](./how-to-create-a-property.md)  
 [Guide pratique : déclarer une propriété avec des niveaux d’accès mixtes](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Guide pratique : appeler une procédure de propriété](./how-to-call-a-property-procedure.md)  
 [Comment : déclarer et appeler une propriété par défaut en Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Guide pratique : placer une valeur dans une propriété](./how-to-put-a-value-in-a-property.md)

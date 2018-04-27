---
title: 'Comment : déterminer si deux objets sont identiques (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 266e878e7f5fa8deb1c8cd91795af8d63ded0177
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Comment : déterminer si deux objets sont identiques (Visual Basic)
En Visual Basic, deux références de variable sont considérés comme identiques si leurs pointeurs sont les mêmes, autrement dit, si les deux variables pointent vers la même instance de classe en mémoire. Par exemple, dans une application Windows Forms, vous souhaiterez effectuer une comparaison pour déterminer si l’instance actuelle (`Me`) est identique à une instance particulière, tel que `Form2`.  
  
 Visual Basic fournit deux opérateurs pour comparer des pointeurs. Le [est un opérateur](../../../../visual-basic/language-reference/operators/is-operator.md) retourne `True` si les objets sont identiques et le [opérateur IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) retourne `True` si elles ne sont pas.  
  
## <a name="determining-if-two-objects-are-identical"></a>Comment déterminer si deux objets sont identiques  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Pour déterminer si deux objets sont identiques  
  
1.  Configurer un `Boolean` expression pour tester les deux objets.  
  
2.  Dans votre expression de test, utilisez le `Is` (opérateur) avec les deux objets comme opérandes.  
  
     `Is` Retourne `True` si les objets pointent vers la même instance de classe.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Déterminer si deux objets ne sont pas identiques  
 Vous souhaitez parfois exécuter une action si les deux objets ne sont pas identiques, et il peut s’avérer difficile de combiner `Not` et `Is`, par exemple `If Not obj1 Is obj2`. Dans ce cas, vous pouvez utiliser la `IsNot` opérateur.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Pour déterminer si deux objets ne sont pas identiques  
  
1.  Configurer un `Boolean` expression pour tester les deux objets.  
  
2.  Dans votre expression de test, utilisez le `IsNot` (opérateur) avec les deux objets comme opérandes.  
  
     `IsNot` Retourne `True` si les objets ne pointent pas vers la même instance de classe.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant teste des paires de `Object` variables pour voir si elles pointent vers la même instance de classe.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 L’exemple précédent affiche la sortie suivante.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Voir aussi  
 [Object (type de données)](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Variables objets](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Valeurs des variables objets](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Is (opérateur)](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot (opérateur)](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Guide pratique : déterminer si deux objets sont liés](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Me, My, MyBase et MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

---
title: override (référence C#)
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 8f692dfdf8bd34ddb62623d86ec3dadd2b8dead3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280151"
---
# <a name="override-c-reference"></a>override (référence C#)
Le modificateur `override` est nécessaire pour étendre ou modifier l’implémentation abstraite ou virtuelle d’une méthode, d’une propriété, d’un indexeur ou d’un événement hérités.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, la classe `Square` doit fournir une implémentation substituée de `Area`, car `Area` est héritée de la classe abstraite `ShapesClass` :  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 Une méthode `override` fournit une nouvelle implémentation d’un membre hérité d’une classe de base. La méthode substituée par une déclaration `override` est appelée méthode de base substituée. La méthode de base substituée doit avoir la même signature que la méthode `override`. Pour plus d’informations sur l’héritage, consultez [Héritage](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Vous ne pouvez pas surcharger une méthode statique ou non virtuelle. La méthode de base substituée doit être `virtual`, `abstract` ou `override`.  
  
 Une déclaration `override` ne peut pas changer l’accessibilité de la méthode `virtual`. Les deux méthodes `override` et `virtual` doivent avoir le même [modificateur de niveau d’accès](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Vous ne pouvez pas utiliser les modificateurs `new`, `static` ou `virtual` pour modifier une méthode `override`.  
  
 Une déclaration de propriété de substitution doit spécifier exactement les mêmes modificateur d’accès, type et nom que la propriété héritée, et la propriété substituée doit être `virtual`, `abstract` ou `override`.  
  
 Pour plus d’informations sur l’utilisation du mot clé `override`, consultez [Gestion de version avec les mots clés override et new](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) et [Savoir quand utiliser les mots clés override et new](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="example"></a>Exemple  
 Cet exemple définit une classe de base nommée `Employee` et une classe dérivée nommée `SalesEmployee`. La classe `SalesEmployee` inclut une propriété supplémentaire (`salesbonus`) et substitue la méthode `CalculatePay` afin de la prendre en compte.  
  
 [!code-csharp[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Référence C#](../../../csharp/language-reference/index.md)  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Héritage](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [Mots clés C#](../../../csharp/language-reference/keywords/index.md)  
 [Modificateurs](../../../csharp/language-reference/keywords/modifiers.md)  
 [abstract](../../../csharp/language-reference/keywords/abstract.md)  
 [virtual](../../../csharp/language-reference/keywords/virtual.md)  
 [new](../../../csharp/language-reference/keywords/new.md)  
 [Polymorphisme](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)

---
title: virtual - Référence C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: 0a6eb7bfcd598eb54b4b0cc5661d219367da2238
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237387"
---
# <a name="virtual-c-reference"></a>virtual (référence C#)
Le mot clé `virtual` sert à modifier une méthode, une propriété, un indexeur ou une déclaration event et leur permet d’être substitués dans une classe dérivée. Par exemple, cette méthode peut être substituée par toute classe qui en hérite :  
  
```csharp  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 L’implémentation d’un membre virtuel peut être modifiée par un [membre de substitution](../../../csharp/language-reference/keywords/override.md) dans une classe dérivée. Pour plus d’informations sur l’utilisation du mot clé `virtual`, consultez [Gestion de version avec les mots clés override et new](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) et [Savoir quand utiliser les mots clés override et new](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="remarks"></a>Notes  
 Quand une méthode virtuelle est appelée, un membre de substitution est recherché dans le type d’objet au moment de l’exécution. Le membre de substitution de la classe la plus dérivée est appelé (cela peut être le membre d’origine), si aucune classe dérivée n’a substitué le membre.  
  
 Par défaut, les méthodes ne sont pas virtuelles. Vous ne pouvez pas substituer une méthode non virtuelle.  
  
 Vous ne pouvez pas utiliser le modificateur `virtual` avec les modificateurs `static`, `abstract`, `private` ou `override`. L’exemple suivant illustre une propriété virtuelle :  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 Les propriétés virtuelles se comportent comme les méthodes abstraites, à l’exception des différences dans la syntaxe de déclaration et d’appel.  
  
-   L’utilisation du modificateur `virtual` sur une propriété statique est une erreur.  
  
-   Une propriété virtuelle héritée peut être substituée dans une classe dérivée en incluant une déclaration de propriété qui utilise le modificateur `override`.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, la classe `Shape` contient les deux coordonnées `x` et `y`, ainsi que la méthode virtuelle `Area()`. Différentes classes de formes, telles que `Circle`, `Cylinder` et `Sphere`, héritent de la classe `Shape`, et la surface est calculée pour chaque figure. Chaque classe dérivée a sa propre implémentation de substitution de `Area()`.  
  
 Notez que les classes héritées `Circle`, `Sphere` et `Cylinder` utilisent toutes des constructeurs qui initialisent la classe de base, comme indiqué dans la déclaration suivante.  
  
```csharp  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 Le programme suivant calcule et affiche la zone appropriée pour chaque figure en appelant l’implémentation appropriée de la méthode `Area()`, selon l’objet associé à la méthode.  
  
 [!code-csharp[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [Référence C#](../../../csharp/language-reference/index.md)  
- [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
- [Modificateurs](../../../csharp/language-reference/keywords/modifiers.md)  
- [Mots clés C#](../../../csharp/language-reference/keywords/index.md)  
- [Polymorphisme](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
- [abstract](../../../csharp/language-reference/keywords/abstract.md)  
- [override](../../../csharp/language-reference/keywords/override.md)  
- [new](../../../csharp/language-reference/keywords/new.md)

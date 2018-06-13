---
title: Initialiseurs d’objet et de collection (Guide de programmation C#)
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: ad8127bfdd7178051077e6f3fe75c777acf5d345
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321946"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Initialiseurs d’objet et de collection (Guide de programmation C#)
Les initialiseurs d'objet vous permettent d'affecter des valeurs aux champs ou propriétés accessibles d'un objet, au moment de sa création, sans devoir appeler un constructeur suivi de ses lignes d'instructions d'assignation. La syntaxe de l'initialiseur de l'objet vous permet de spécifier les arguments d'un constructeur ou de les omettre (et la syntaxe de parenthèses).  L'exemple suivant montre comment utiliser l'initialiseur de l'objet de type nommé, `Cat`, et comment appeler le constructeur par défaut. Notez l'utilisation de propriétés implémentées automatiquement dans la classe `Cat`. Pour plus d’informations, consultez [Propriétés implémentées automatiquement](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
La syntaxe des initialiseurs d’objet vous permet de créer une instance qui assigne l’objet nouvellement créé, avec ses propriétés, à la variable dans l’assignation.
  
## <a name="object-initializers-with-anonymous-types"></a>Initialiseurs d'objet avec des types anonymes  
 Les initialiseurs d’objet peuvent être utilisés dans tous les contextes, mais ils sont particulièrement utiles dans les expressions de requête [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Les expressions de requête utilisent souvent des [types anonymes](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), qui peuvent uniquement être initialisés à l’aide d’un initialiseur d’objet, comme indiqué dans la déclaration suivante.  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 Les types anonymes permettent à la clause `select` d’une expression de requête [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] de transformer les objets de la séquence d’origine en objets dont la valeur et la forme peuvent différer de l’original. Cela s'avère utile si vous souhaitez stocker uniquement une partie des informations de chaque objet d'une séquence. Dans l'exemple suivant, supposons qu'un objet de produit (`p`) contient de nombreux champs et méthodes et que vous souhaitez uniquement créer une séquence d'objets qui contiennent le nom de produit et le prix unitaire.  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 Lorsque cette requête est exécutée, la variable `productInfos` contient une séquence d'objets qui sont accessibles dans une instruction `foreach` comme indiqué dans cet exemple :  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 Chaque objet dans le nouveau type anonyme a deux propriétés publiques qui reçoivent les mêmes noms que les propriétés ou champs de l'objet d'origine. Vous pouvez également renommer un champ lorsque vous créez un type anonyme. L'exemple suivant renomme le champ `UnitPrice` en `Price`.  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a>Initialiseurs d'objets avec les types Nullable  
 C'est une erreur au moment de la compilation que d'utiliser un initialiseur d'objet avec un struct Nullable.  
  
## <a name="collection-initializers"></a>Initialiseurs de collection  
 Les initialiseurs de collection vous permettent de spécifier un ou plusieurs initialiseurs d’élément quand vous initialisez un type de collection qui implémente <xref:System.Collections.IEnumerable> et qui utilise `Add` comme méthode d’instance ou méthode d’extension avec la signature appropriée. Les initialiseurs d'élément peuvent être une valeur simple, une expression ou un initialiseur d'objet. En utilisant un initialiseur de collection, il n'est pas nécessaire de spécifier plusieurs appels à la méthode `Add` de la classe dans votre code source ; le compilateur ajoute les appels.  
  
 Les exemples suivants présentent deux initialiseurs de collection simples :  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 L'initialiseur de collection suivant utilise des initialiseurs d'objets pour initialiser les objets de la classe `Cat` définis dans un exemple précédent. Notez que les initialiseurs d'objets individuels sont placés entre accolades et séparés par une virgule.  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 Vous pouvez spécifier [Null](../../../csharp/language-reference/keywords/null.md) comme élément dans un initialiseur de collection si la méthode `Add` de la collection l’autorise.  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 Vous pouvez spécifier des éléments indexés si la collection prend en charge l’indexation.  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="examples"></a>Exemples

 L’exemple suivant combine les concepts d’initialiseurs d’objet et de collection.

 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
 
 Comme indiqué dans l’exemple suivant, un objet qui implémente <xref:System.Collections.IEnumerable> contenant une méthode `Add` avec plusieurs paramètres permet la collection d’initialiseurs avec plusieurs éléments dans la liste correspondant à la signature de la méthode `Add`. 
 
 [!code-csharp[csProgGuideLINQ#84](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_7.cs)]
 
 Les méthodes `Add` peuvent utiliser le mot clé `params` pour sélectionner un nombre variable d’arguments, comme indiqué dans l’exemple suivant. Cet exemple montre l’implémentation personnalisée d’un indexeur pour initialiser une collection à l’aide de plusieurs index.
 
 [!code-csharp[csProgGuideLINQ#85](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_8.cs)]
 
## <a name="see-also"></a>Voir aussi  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Expressions de requête LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Types anonymes](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

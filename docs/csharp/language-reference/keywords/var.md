---
title: var (référence C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2be56243f9c4ddafb3903d14fa6d6f9cb0e2f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="var-c-reference"></a>var (référence C#)
Depuis Visual C# 3.0, les variables déclarées à la portée de la méthode peuvent avoir un type implicite `var`. Une variable locale implicitement typée est fortement typée comme si vous aviez déclaré vous-même le type, alors que c’est le compilateur qui détermine le type. Les deux déclarations suivantes d’`i` sont équivalentes fonctionnellement :  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 Pour plus d’informations, consultez [Variables locales implicitement typées](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) et [Relations des types dans des opérations de requête LINQ](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant présente deux expressions de requête. Dans la première expression, l’utilisation de `var` est autorisée, mais n’est pas obligatoire parce que le type du résultat de la requête peut être déclaré explicitement en tant que `IEnumerable<string>`. Toutefois, `var` doit être utilisé dans la deuxième expression parce que le résultat est une collection de types anonymes et le nom de ce type n’est pas accessible sauf par le compilateur. Notez que, dans le deuxième exemple, la variable d’itération `foreach` `item` doit également être implicitement typée.  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>Voir aussi  
 [Référence C#](../../../csharp/language-reference/index.md)  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Variables locales implicitement typées](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)

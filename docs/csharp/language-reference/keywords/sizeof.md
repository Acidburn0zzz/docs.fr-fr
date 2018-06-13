---
title: sizeof (référence C#)
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 83038255160ec778c71120566cf8f99092761add
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270576"
---
# <a name="sizeof-c-reference"></a>sizeof (référence C#)
Permet d’obtenir la taille en octets d’un type non managé. Les types non managés incluent les types intégrés qui sont répertoriés dans le tableau ci-dessous, ainsi que les éléments suivants :  
  
-   Types d'enum  
  
-   Types de pointeur  
  
-   Les structs définis par l'utilisateur qui ne contiennent pas de champs ou de propriétés qui sont de type référence  
  
 L’exemple suivant montre comment extraire la taille d’un `int` :  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a>Notes  
 Depuis la version 2.0 de C#, l’application de `sizeof` à des types intégrés ne nécessite plus l’utilisation du mode [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
 L’opérateur `sizeof` ne peut pas être surchargé. Les valeurs retournées par l’opérateur `sizeof` sont du type `int`. Le tableau suivant indique les valeurs constantes qui sont substituées aux expressions `sizeof` qui ont certains types intégrés comme opérandes.  
  
|Expression|Valeur constante|  
|----------------|--------------------|  
|`sizeof(sbyte)`|1|  
|`sizeof(byte)`|1|  
|`sizeof(short)`|2|  
|`sizeof(ushort)`|2|  
|`sizeof(int)`|4|  
|`sizeof(uint)`|4|  
|`sizeof(long)`|8|  
|`sizeof(ulong)`|8|  
|`sizeof(char)`|2 (Unicode)|  
|`sizeof(float)`|4|  
|`sizeof(double)`|8|  
|`sizeof(decimal)`|16|  
|`sizeof(bool)`|1|  
  
 Pour tous les autres types, y compris les structs, l’opérateur `sizeof` peut être utilisé uniquement dans les blocs de code unsafe. Bien que vous puissiez utiliser la méthode <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, la valeur retournée par cette méthode n’est pas toujours identique à celle retournée par `sizeof`. <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> retourne la taille après que le type a été marshalé, alors que `sizeof` retourne la taille telle qu’elle a été allouée par le Common Language Runtime, dont la marge intérieure.  
  
## <a name="example"></a>Exemple  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Référence C#](../../../csharp/language-reference/index.md)  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Mots clés C#](../../../csharp/language-reference/keywords/index.md)  
 [Mots clés des opérateurs](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [enum](../../../csharp/language-reference/keywords/enum.md)  
 [Pointeurs et code unsafe](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md)

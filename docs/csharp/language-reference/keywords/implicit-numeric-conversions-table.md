---
title: Tableau des conversions numériques implicites (référence C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 4bbc6086dc5fd3838ef9361762c3068ca44efd0e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2018
ms.locfileid: "43417594"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Tableau des conversions numériques implicites (référence C#)
Le tableau suivant montre les conversions numériques implicites prédéfinies. Les conversions implicites peuvent se produire dans de nombreuses situations, comme les appels de méthode et les instructions d’assignation.  
  
|From|À|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`short`, `int`, `long`, `float`, `double` ou `decimal`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` ou `decimal`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`int`, `long`, `float`, `double` ou `decimal`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` ou `decimal`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`long`, `float`, `double` ou `decimal`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`long`, `ulong`, `float`, `double` ou `decimal`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`float`, `double`ou `decimal`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` ou `decimal`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`, `double`ou `decimal`|  
  
## <a name="remarks"></a>Notes  
  
-   C’est la précision, et non la magnitude, qui peut être perdue lors de conversions de `int`, `uint`, `long` ou `ulong` à `float`, et de `long` ou `ulong` à `double`.  
  
-   Il n’y a pas de conversion implicite possible vers le type `char`.  
  
-   Il n’y a pas non plus de conversion implicite possible entre les types virgule flottante et le type `decimal`.  
  
-   Une expression constante de type `int` peut être convertie en `sbyte`, `byte`, `short`, `ushort`, `uint` ou `ulong`, à condition que la valeur de l’expression constante se trouve dans la plage du type de destination.  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi  

- [Référence C#](../../../csharp/language-reference/index.md)  
- [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
- [Tableau des types intégraux](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Tableau des types intégrés](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Tableau des conversions numériques explicites](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [Cast et conversions de types](../../../csharp/programming-guide/types/casting-and-type-conversions.md)

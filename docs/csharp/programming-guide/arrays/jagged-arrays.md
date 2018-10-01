---
title: Tableaux en escalier (Guide de programmation C#)
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 2e4988439000712f4d1bd9b5abe412e7fd5d43eb
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396875"
---
# <a name="jagged-arrays-c-programming-guide"></a>Tableaux en escalier (Guide de programmation C#)

Un tableau en escalier est un tableau dont les éléments sont des tableaux. Les éléments d’un tableau en escalier peuvent être de dimensions et de tailles différentes. Un tableau en escalier est parfois appelé « tableau de tableaux ». Les exemples suivants montrent comment déclarer, initialiser et accéder aux tableaux en escalier.  
  
 Voici une déclaration d’un tableau unidimensionnel qui comporte trois éléments, chacun d’eux étant un tableau unidimensionnel d’entiers :  
  
 [!code-csharp[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 Pour pouvoir utiliser `jaggedArray`, vous devez initialiser ses éléments. Pour ce faire, procédez comme suit :  
  
 [!code-csharp[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 Chacun des éléments est un tableau unidimensionnel d’entiers. Le premier élément est un tableau de 5 entiers, le deuxième est un tableau de 4 entiers et le troisième est un tableau de 2 entiers.  
  
 Il est aussi possible d’utiliser des initialiseurs pour remplir les éléments de tableau de valeurs, auquel cas vous n’avez pas besoin de la taille du tableau. Exemple :  
  
 [!code-csharp[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 Vous pouvez aussi initialiser le tableau au moment de la déclaration, comme ceci :  
  
 [!code-csharp[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 Vous pouvez utiliser la forme abrégée suivante. Notez que vous ne pouvez pas omettre l’opérateur `new` dans l’initialisation des éléments, car il n’existe pas d’initialisation par défaut pour les éléments :  
  
 [!code-csharp[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 Un tableau en escalier est un tableau de tableaux, et par conséquent ses éléments sont des types référence et sont initialisés sur `null`.  
  
 Vous pouvez accéder aux éléments de tableau individuels comme dans ces exemples :  
  
 [!code-csharp[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 Il est possible de combiner des tableaux en escalier et des tableaux multidimensionnels. Vous trouverez ci-dessous une déclaration et une initialisation d’un tableau en escalier unidimensionnel composé de trois éléments de tableau à deux dimensions de tailles différentes. Pour plus d’informations sur les tableaux à deux dimensions, consultez [Tableaux multidimensionnels](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!code-csharp[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 Vous pouvez accéder aux différents éléments comme le montre cet exemple, qui présente la valeur de l’élément `[1,0]` du premier tableau (valeur `5`) :  
  
 [!code-csharp[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 La méthode `Length` retourne le nombre de tableaux contenus dans le tableau en escalier. Par exemple, en supposant que vous avez déclaré le tableau précédent, cette ligne :  
  
 [!code-csharp[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 retourne la valeur 3.  
  
## <a name="example"></a>Exemple

 Cet exemple génère un tableau dont les éléments sont eux-mêmes des tableaux. Chacun des éléments de tableau ont une taille différente.  
  
 [!code-csharp[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Array>  
- [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
- [Tableaux](../../../csharp/programming-guide/arrays/index.md)  
- [Tableaux unidimensionnels](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [Tableaux multidimensionnels](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)

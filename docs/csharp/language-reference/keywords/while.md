---
title: while (référence C#)
ms.date: 07/20/2015
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 23c5ca3bb7dc401a894a6c3918fbaec9a9306153
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="while-c-reference"></a>while (référence C#)
L’instruction `while` exécute une instruction ou un bloc d’instructions jusqu’à ce qu’une expression spécifique corresponde à la valeur `false`.  
  
## <a name="example"></a>Exemple  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>Exemple  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>Exemple  
 Comme le test de l’expression `while` a lieu avant chaque exécution de la boucle, une boucle `while` est exécutée plusieurs fois ou pas du tout. Cela diffère de la boucle [do](../../../csharp/language-reference/keywords/do.md), qui s’exécute une ou plusieurs fois.  
  
 Une boucle `while` peut être terminée quand une instruction [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) ou [throw](../../../csharp/language-reference/keywords/throw.md) transfère le contrôle à l’extérieur de la boucle. Pour transmettre le contrôle à la prochaine itération sans sortir de la boucle, utilisez l’instruction [continue](../../../csharp/language-reference/keywords/continue.md). Notez la différence de sortie des trois exemples précédents, selon l’emplacement où `int n` est incrémenté. Dans l’exemple ci-dessous, aucune sortie n’est générée.  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Référence C#](../../../csharp/language-reference/index.md)  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Mots clés C#](../../../csharp/language-reference/keywords/index.md)  
 [while, instruction (C++)](/cpp/cpp/while-statement-cpp)  
 [Instructions d’itération](../../../csharp/language-reference/keywords/iteration-statements.md)

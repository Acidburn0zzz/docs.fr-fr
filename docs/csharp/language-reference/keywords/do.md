---
title: do (référence C#)
ms.date: 07/20/2015
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5599f079e29fd094c4d6a6a75afba89fb562a166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="do-c-reference"></a>do (référence C#)
L’instruction `do` exécute une instruction ou un bloc d’instructions de manière répétée jusqu’à ce qu’une expression spécifiée corresponde à `false`. Le corps de la boucle doit être placée entre accolades, `{}`, sauf si elle se compose d’une seule instruction. Dans ce cas, les accolades sont facultatives.  
  
## <a name="example"></a>Exemple  
 Dans l’exemple suivant, les instructions de boucle `do-while` s’exécutent tant que la variable `x` est inférieure à 5.  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 Contrairement à une instruction [while](../../../csharp/language-reference/keywords/while.md), une boucle `do-while` est exécutée une fois avant que l’expression conditionnelle soit évaluée.  
  
 À tout endroit dans le bloc `do-while`, vous pouvez quitter la boucle à l’aide de l’instruction [break](../../../csharp/language-reference/keywords/break.md). Vous pouvez passer directement à l’instruction d’évaluation de l’expression `while` à l’aide de l’instruction [continue](../../../csharp/language-reference/keywords/continue.md). Si l’expression `while` a la valeur true, l’exécution se poursuit à la première instruction dans la boucle. Si l’expression a la valeur false, l’exécution se poursuit à la première instruction après la boucle `do-while`.  
  
 Vous pouvez aussi quitter une boucle `do-while` à l’aide des instructions [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) ou [throw](../../../csharp/language-reference/keywords/throw.md).  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Référence C#](../../../csharp/language-reference/index.md)  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Mots clés C#](../../../csharp/language-reference/keywords/index.md)  
 [do-while, instruction (C++)](/cpp/cpp/do-while-statement-cpp)  
 [Instructions d’itération](../../../csharp/language-reference/keywords/iteration-statements.md)

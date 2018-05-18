---
title: Guide pratique pour accéder à des arguments de ligne de commande à l’aide de foreach (Guide de programmation C#)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 2f1723efd4056539e12605bc1a4229f94bc9e055
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>Guide pratique pour accéder à des arguments de ligne de commande à l’aide de foreach (Guide de programmation C#)
Il existe une autre méthode d’itération au sein d’un tableau qui consiste à utiliser l’instruction [foreach](../../../csharp/language-reference/keywords/foreach-in.md), comme indiqué dans cet exemple. L’instruction `foreach` peut être utilisée pour effectuer une itération au sein d’un tableau, d’une classe de collection .NET Framework, ou d’une classe ou d’un struct qui implémente l’interface <xref:System.Collections.IEnumerable>.  
  
> [!NOTE]
>  Quand vous exécutez une application dans Visual Studio, vous pouvez spécifier des arguments de ligne de commande dans la [page Déboguer du Concepteur de projet](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Exemple  
 Cet exemple montre comment imprimer les arguments de ligne de commande à l’aide de `foreach`.  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Array>  
 <xref:System.Collections>  
 [Génération à partir de la ligne de commande avec csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [Main() et arguments de ligne de commande](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [Comment : afficher les arguments de ligne de commande](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [Valeurs de retour Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

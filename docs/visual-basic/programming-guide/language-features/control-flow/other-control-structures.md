---
title: "Autres Structures de contrôle (Visual Basic) | Documents Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8f8bd57f193be0d7f410f7325355ffc47ab10e3f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="a062d-102">Autres structures de contrôle (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a062d-102">Other Control Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="a062d-103">Fournit des structures de contrôle qui vous aident à supprimer une ressource ou de réduisent le nombre de fois où que vous devez répéter une référence d’objet.</span><span class="sxs-lookup"><span data-stu-id="a062d-103"> provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="a062d-104">À l’aide de... À l’aide de la Construction de fin</span><span class="sxs-lookup"><span data-stu-id="a062d-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="a062d-105">Le `Using...End Using` construction établit un bloc d’instruction dans laquelle vous utilisez une ressource telle qu’une connexion SQL.</span><span class="sxs-lookup"><span data-stu-id="a062d-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="a062d-106">Vous pouvez éventuellement acquérir la ressource avec la `Using` instruction.</span><span class="sxs-lookup"><span data-stu-id="a062d-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="a062d-107">Lorsque vous quittez la `Using` bloc, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supprime automatiquement la ressource afin qu’il soit disponible pour un autre code à utiliser.</span><span class="sxs-lookup"><span data-stu-id="a062d-107">When you exit the `Using` block, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="a062d-108">La ressource doit être locale et supprimable.</span><span class="sxs-lookup"><span data-stu-id="a062d-108">The resource must be local and disposable.</span></span> <span data-ttu-id="a062d-109">Pour plus d’informations, consultez [instruction à l’aide de](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a062d-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="a062d-110">Avec... Mettre fin à la Construction</span><span class="sxs-lookup"><span data-stu-id="a062d-110">With...End With Construction</span></span>  
 <span data-ttu-id="a062d-111">Le `With...End With` vous permet de spécifier une référence d’objet une fois, puis exécutez une série d’instructions qui accèdent à ses membres.</span><span class="sxs-lookup"><span data-stu-id="a062d-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="a062d-112">Cela peut simplifier votre code et améliorer les performances car [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] n’a pas à rétablir la référence pour chaque instruction qui y accède.</span><span class="sxs-lookup"><span data-stu-id="a062d-112">This can simplify your code and improve performance because [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="a062d-113">Pour plus d’informations, consultez [avec... End With, instruction](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a062d-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a062d-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a062d-114">See Also</span></span>  
 <span data-ttu-id="a062d-115">[Flux de contrôle](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="a062d-115">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="a062d-116"> [Structures de décision](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="a062d-116"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="a062d-117"> [Structures de boucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="a062d-117"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="a062d-118"> [Structures de contrôle imbriquées](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="a062d-118"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="a062d-119"> [Instruction using](../../../../visual-basic/language-reference/statements/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a062d-119"> [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md) </span></span>  
<span data-ttu-id="a062d-120"> [With...End With (instruction)](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a062d-120"> [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>

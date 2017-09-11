---
title: RemoveHandler (instruction) | Documents Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
dev_langs:
- VB
helpviewer_keywords:
- RemoveHandler keyword
- RemoveHandler statement
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
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
ms.openlocfilehash: 6e614a1dce4894dcd18509854f3cae149665cbf0
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="removehandler-statement"></a><span data-ttu-id="ba8aa-102">RemoveHandler, instruction</span><span class="sxs-lookup"><span data-stu-id="ba8aa-102">RemoveHandler Statement</span></span>
<span data-ttu-id="ba8aa-103">Supprime l’association entre un événement et un gestionnaire d’événements.</span><span class="sxs-lookup"><span data-stu-id="ba8aa-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8aa-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ba8aa-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="ba8aa-105">Composants</span><span class="sxs-lookup"><span data-stu-id="ba8aa-105">Parts</span></span>  
  
|<span data-ttu-id="ba8aa-106">Terme</span><span class="sxs-lookup"><span data-stu-id="ba8aa-106">Term</span></span>|<span data-ttu-id="ba8aa-107">Définition</span><span class="sxs-lookup"><span data-stu-id="ba8aa-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="ba8aa-108">Le nom de l’événement géré.</span><span class="sxs-lookup"><span data-stu-id="ba8aa-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="ba8aa-109">Le nom de la procédure en gérant l’événement.</span><span class="sxs-lookup"><span data-stu-id="ba8aa-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba8aa-110">Remarques</span><span class="sxs-lookup"><span data-stu-id="ba8aa-110">Remarks</span></span>  
 <span data-ttu-id="ba8aa-111">Le `AddHandler` et `RemoveHandler` vous permettent de démarrer et arrêter la gestion d’un événement spécifique à tout moment pendant l’exécution du programme.</span><span class="sxs-lookup"><span data-stu-id="ba8aa-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba8aa-112">Pour les événements personnalisés, les `RemoveHandler` instruction appelle l’événement `RemoveHandler` accesseur.</span><span class="sxs-lookup"><span data-stu-id="ba8aa-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="ba8aa-113">Pour plus d’informations sur les événements personnalisés, consultez la page [Event, instruction](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ba8aa-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba8aa-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="ba8aa-114">Example</span></span>  
 <span data-ttu-id="ba8aa-115">[!code-vb[VbVbalrEvents&#17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ba8aa-115">[!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8aa-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba8aa-116">See Also</span></span>  
 <span data-ttu-id="ba8aa-117">[AddHandler (instruction)](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ba8aa-117">[AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="ba8aa-118"> [Gère](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ba8aa-118"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="ba8aa-119"> [Event (instruction)](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ba8aa-119"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="ba8aa-120"> [Événements](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="ba8aa-120"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>

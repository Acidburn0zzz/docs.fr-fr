---
title: "Comment : appeler un gestionnaire d'événements en Visual Basic"
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b8a35459fdeb7cce0b494a9b3024a79bd4173cc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="8b17e-102">Comment : appeler un gestionnaire d'événements en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8b17e-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="8b17e-103">Un *événement* est une action ou une occurrence, telles que la souris, cliquez ou une limite de crédit dépassé : reconnue par un composant de programme pour lequel vous pouvez écrire du code en réponse.</span><span class="sxs-lookup"><span data-stu-id="8b17e-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="8b17e-104">Un *Gestionnaire d’événements* est le code que vous écrivez pour répondre à un événement.</span><span class="sxs-lookup"><span data-stu-id="8b17e-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="8b17e-105">Un gestionnaire d’événements en Visual Basic est un `Sub` procédure.</span><span class="sxs-lookup"><span data-stu-id="8b17e-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="8b17e-106">Toutefois, vous ne normalement l’appelez pas la même façon que d’autres `Sub` procédures.</span><span class="sxs-lookup"><span data-stu-id="8b17e-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="8b17e-107">Au lieu de cela, vous identifiez la procédure comme gestionnaire pour l’événement.</span><span class="sxs-lookup"><span data-stu-id="8b17e-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="8b17e-108">Vous pouvez effectuer ceci avec un [gère](../../../../visual-basic/language-reference/statements/handles-clause.md) clause et un [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, ou avec un [AddHandler, instruction](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8b17e-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="8b17e-109">À l’aide un `Handles` clause constitue la méthode par défaut de déclarer un gestionnaire d’événements en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8b17e-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="8b17e-110">Il s’agit de la manière dont les gestionnaires d’événements sont écrits par les concepteurs lorsque vous programmez dans l’environnement de développement intégré (IDE).</span><span class="sxs-lookup"><span data-stu-id="8b17e-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="8b17e-111">La `AddHandler` instruction convient pour déclencher des événements de manière dynamique au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="8b17e-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="8b17e-112">Lorsque l’événement se produit, Visual Basic appelle automatiquement la procédure de gestionnaire d’événements.</span><span class="sxs-lookup"><span data-stu-id="8b17e-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="8b17e-113">Tout code qui a accès à l’événement peut déclencher celui-ci en exécutant une [RaiseEvent, instruction](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8b17e-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="8b17e-114">Vous pouvez associer plusieurs gestionnaires d’événements avec le même événement.</span><span class="sxs-lookup"><span data-stu-id="8b17e-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="8b17e-115">Dans certains cas, vous pouvez dissocier un gestionnaire d’un événement.</span><span class="sxs-lookup"><span data-stu-id="8b17e-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="8b17e-116">Pour plus d’informations, consultez [Événements](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="8b17e-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="8b17e-117">Pour appeler un gestionnaire d’événements à l’aide de Handles et WithEvents</span><span class="sxs-lookup"><span data-stu-id="8b17e-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="8b17e-118">Assurez-vous que l’événement est déclaré avec un [Event, instruction](../../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8b17e-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="8b17e-119">Déclarez une variable objet au module ou la classe niveau, à l’aide de la [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) (mot clé).</span><span class="sxs-lookup"><span data-stu-id="8b17e-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="8b17e-120">Le `As` clause pour cette variable doit spécifier la classe qui déclenche l’événement.</span><span class="sxs-lookup"><span data-stu-id="8b17e-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="8b17e-121">Dans la déclaration de la gestion des événements `Sub` procédure, ajoutez un [gère](../../../../visual-basic/language-reference/statements/handles-clause.md) clause qui spécifie le `WithEvents` variable et le nom de l’événement.</span><span class="sxs-lookup"><span data-stu-id="8b17e-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="8b17e-122">Lorsque l’événement se produit, Visual Basic appelle automatiquement la `Sub` procédure.</span><span class="sxs-lookup"><span data-stu-id="8b17e-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="8b17e-123">Votre code peut utiliser un `RaiseEvent` instruction pour rendre l’événement se produit.</span><span class="sxs-lookup"><span data-stu-id="8b17e-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="8b17e-124">L’exemple suivant définit un événement et un `WithEvents` variable qui fait référence à la classe qui déclenche l’événement.</span><span class="sxs-lookup"><span data-stu-id="8b17e-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="8b17e-125">La gestion des événements `Sub` procédure utilise un `Handles` clause pour spécifier la classe et l’événement qu’elle gère.</span><span class="sxs-lookup"><span data-stu-id="8b17e-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="8b17e-126">Pour appeler un gestionnaire d’événements à l’aide de AddHandler</span><span class="sxs-lookup"><span data-stu-id="8b17e-126">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="8b17e-127">Assurez-vous que l’événement est déclaré avec un `Event` instruction.</span><span class="sxs-lookup"><span data-stu-id="8b17e-127">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="8b17e-128">Exécuter un [AddHandler, instruction](../../../../visual-basic/language-reference/statements/addhandler-statement.md) connecter dynamiquement la gestion des événements `Sub` procédure avec l’événement.</span><span class="sxs-lookup"><span data-stu-id="8b17e-128">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="8b17e-129">Lorsque l’événement se produit, Visual Basic appelle automatiquement la `Sub` procédure.</span><span class="sxs-lookup"><span data-stu-id="8b17e-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="8b17e-130">Votre code peut utiliser un `RaiseEvent` instruction pour rendre l’événement se produit.</span><span class="sxs-lookup"><span data-stu-id="8b17e-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="8b17e-131">L’exemple suivant définit un `Sub` procédure pour gérer les <xref:System.Windows.Forms.Form.Closing> événement d’un formulaire.</span><span class="sxs-lookup"><span data-stu-id="8b17e-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="8b17e-132">Il utilise ensuite la [AddHandler, instruction](../../../../visual-basic/language-reference/statements/addhandler-statement.md) pour associer le `catchClose` procédure comme gestionnaire d’événements pour <xref:System.Windows.Forms.Form.Closing>.</span><span class="sxs-lookup"><span data-stu-id="8b17e-132">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     <span data-ttu-id="8b17e-133">Vous pouvez dissocier un gestionnaire d’événements à partir d’un événement en exécutant le [RemoveHandler, instruction](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8b17e-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b17e-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b17e-134">See Also</span></span>  
 [<span data-ttu-id="8b17e-135">Procédures</span><span class="sxs-lookup"><span data-stu-id="8b17e-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8b17e-136">Procédures Sub</span><span class="sxs-lookup"><span data-stu-id="8b17e-136">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="8b17e-137">Sub (instruction)</span><span class="sxs-lookup"><span data-stu-id="8b17e-137">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="8b17e-138">AddressOf (opérateur)</span><span class="sxs-lookup"><span data-stu-id="8b17e-138">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="8b17e-139">Guide pratique : créer une procédure</span><span class="sxs-lookup"><span data-stu-id="8b17e-139">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="8b17e-140">Guide pratique : appeler une procédure qui ne retourne pas de valeur</span><span class="sxs-lookup"><span data-stu-id="8b17e-140">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)

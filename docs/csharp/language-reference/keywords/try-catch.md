---
title: try-catch (référence C#)
ms.date: 07/20/2015
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
ms.openlocfilehash: f917d662366dc8ff540cdee6222199fe8f5606c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="try-catch-c-reference"></a><span data-ttu-id="ab6bc-102">try-catch (référence C#)</span><span class="sxs-lookup"><span data-stu-id="ab6bc-102">try-catch (C# Reference)</span></span>
<span data-ttu-id="ab6bc-103">L'instruction try-catch consiste en un bloc `try` suivi d'une ou plusieurs clauses `catch` qui spécifient des gestionnaires pour différentes exceptions.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab6bc-104">Notes</span><span class="sxs-lookup"><span data-stu-id="ab6bc-104">Remarks</span></span>  
 <span data-ttu-id="ab6bc-105">Quand une exception est levée, le Common Language Runtime (CLR) recherche l'instruction `catch` qui gère cette exception.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-105">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="ab6bc-106">Si la méthode en cours d'exécution ne contient pas un tel bloc `catch`, le CLR examine la méthode qui a appelé la méthode actuelle, puis remonte la pile des appels.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-106">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="ab6bc-107">Si aucun bloc `catch` n'est trouvé, alors le CLR affiche un message d'exception non gérée à l'utilisateur et arrête l'exécution du programme.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-107">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>  
  
 <span data-ttu-id="ab6bc-108">Le bloc `try` contient le code protégé susceptible de provoquer l'exception.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-108">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="ab6bc-109">Le bloc est exécuté jusqu'à ce qu'une exception soit levée ou qu'il se soit correctement terminé.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-109">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="ab6bc-110">Par exemple, la tentative suivante d'effectuer un cast d'un objet `null` déclenche l'exception <xref:System.NullReferenceException> :</span><span class="sxs-lookup"><span data-stu-id="ab6bc-110">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>  
  
```csharp  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 <span data-ttu-id="ab6bc-111">Bien que la clause `catch` puisse être utilisée sans arguments pour intercepter tout type d'exception, cette utilisation est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-111">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="ab6bc-112">En général, vous devez intercepter uniquement les exceptions desquelles vous savez comment récupérer.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-112">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="ab6bc-113">Par conséquent, vous devez toujours spécifier un argument d'objet dérivé de <xref:System.Exception?displayProperty=nameWithType>, par exemple :</span><span class="sxs-lookup"><span data-stu-id="ab6bc-113">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=nameWithType> For example:</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
}  
```  
  
 <span data-ttu-id="ab6bc-114">Il est possible d'utiliser plusieurs clauses `catch` spécifiques dans la même instruction try-catch.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-114">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="ab6bc-115">Dans ce cas, l'ordre des clauses `catch` est important car les clauses `catch` sont examinées dans l'ordre.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-115">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="ab6bc-116">Interceptez les exceptions plus spécifiques avant les moins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-116">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="ab6bc-117">Le compilateur produit une erreur si vous organisez vos blocs catch de sorte qu'un bloc ultérieur ne puisse jamais être atteint.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-117">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>  
  
 <span data-ttu-id="ab6bc-118">L'utilisation d'arguments `catch` constitue un moyen de filtrer les exceptions à gérer.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-118">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="ab6bc-119">Vous pouvez également utiliser une expression de prédicat qui examine l'exception de plus près pour déterminer si elle doit être gérée.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-119">You can also use a predicate expression that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="ab6bc-120">Si l'expression de prédicat retourne la valeur false, alors la recherche d'un gestionnaire se poursuit.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-120">If the predicate expression returns false, then the search for a handler continues.</span></span>  
  
```csharp  
catch (ArgumentException e) when (e.ParamName == "…")  
{  
}  
```  
  
 <span data-ttu-id="ab6bc-121">L'utilisation de filtres d'exceptions est préférable à une interception et une nouvelle levée (voir explication ci-dessous), car les filtres laissent la pile intact.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-121">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="ab6bc-122">Si un gestionnaire ultérieur vide la pile, vous pouvez déterminer d'où l'exception provient à l'origine, au lieu de déterminer simplement le dernier emplacement auquel elle a été levée.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-122">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="ab6bc-123">Une utilisation courante des expressions de filtre d'exception est liée à la journalisation.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-123">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="ab6bc-124">Vous pouvez créer une fonction de prédicat qui retourne toujours false et dont la sortie est journalisée ; vous pouvez journaliser des exceptions au fur et à mesure sans avoir à les gérer ni à les lever de nouveau.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-124">You can create a predicate function that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>  
  
 <span data-ttu-id="ab6bc-125">Une instruction [throw](../../../csharp/language-reference/keywords/throw.md) peut être utilisée dans un bloc `catch` pour lever une nouvelle fois l’exception interceptée par l’instruction `catch`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-125">A [throw](../../../csharp/language-reference/keywords/throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="ab6bc-126">L'exemple suivant extrait des informations sources d'une exception <xref:System.IO.IOException>, puis lève l'exception à la méthode parente.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-126">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>  
  
```csharp  
catch (FileNotFoundException e)  
{  
    // FileNotFoundExceptions are handled here.  
}  
catch (IOException e)  
{  
    // Extract some information from this exception, and then   
    // throw it to the parent method.  
    if (e.Source != null)  
        Console.WriteLine("IOException source: {0}", e.Source);  
    throw;  
}  
```  
  
 <span data-ttu-id="ab6bc-127">Vous pouvez intercepter une seule exception et lever une exception différente.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-127">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="ab6bc-128">Dans ce cas, spécifiez l'exception que vous interceptez en tant qu'exception interne, comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-128">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
    // Perform some action here, and then throw a new exception.  
    throw new YourCustomException("Put your error message here.", e);  
}  
```  
  
 <span data-ttu-id="ab6bc-129">Vous pouvez également lever à nouveau une exception quand une condition spécifiée a la valeur true, comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-129">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)  
{  
    if (e.Data == null)  
    {  
        throw;  
    }  
    else  
    {  
        // Take some action.  
    }  
 }  
```  
  
 <span data-ttu-id="ab6bc-130">Dans un bloc `try`, initialisez uniquement les variables qui y sont déclarées.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-130">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="ab6bc-131">Sinon, une exception peut se produire avant la fin de l'exécution du bloc.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-131">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="ab6bc-132">Par exemple, dans l'exemple de code suivant, la variable `n` est initialisée à l'intérieur du bloc `try`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-132">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="ab6bc-133">Une tentative d'utilisation de cette variable en dehors du bloc `try` dans l'instruction `Write(n)` génère une erreur du compilateur.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-133">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>  
  
```csharp  
static void Main()   
{  
    int n;  
    try   
    {  
        // Do not initialize this variable here.  
        n = 123;  
    }  
    catch  
    {  
    }  
    // Error: Use of unassigned local variable 'n'.  
    Console.Write(n);  
}  
```  
  
 <span data-ttu-id="ab6bc-134">Pour plus d’informations sur l’interception, consultez [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="ab6bc-134">For more information about catch, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
## <a name="exceptions-in-async-methods"></a><span data-ttu-id="ab6bc-135">Exceptions dans les méthodes async</span><span class="sxs-lookup"><span data-stu-id="ab6bc-135">Exceptions in Async Methods</span></span>  
 <span data-ttu-id="ab6bc-136">Une méthode async est marquée par un modificateur [async](../../../csharp/language-reference/keywords/async.md) et contient généralement une ou plusieurs expressions ou instructions await.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-136">An async method is marked  by an  [async](../../../csharp/language-reference/keywords/async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="ab6bc-137">Une expression await applique l’opérateur [await](../../../csharp/language-reference/keywords/await.md) à un <xref:System.Threading.Tasks.Task> ou <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-137">An await expression applies the [await](../../../csharp/language-reference/keywords/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="ab6bc-138">Quand le contrôle atteint un `await` dans la méthode async, la progression de la méthode est interrompue jusqu'à ce que la tâche attendue se termine.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-138">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="ab6bc-139">Quand la tâche est terminée, l’exécution peut reprendre dans la méthode.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-139">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="ab6bc-140">Pour plus d’informations, consultez [Programmation asynchrone avec Async et Await](../../../csharp/programming-guide/concepts/async/index.md) et [Flux de contrôle dans les programmes Async](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="ab6bc-140">For more information, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
 <span data-ttu-id="ab6bc-141">La tâche terminée à laquelle `await` est appliqué peut être dans un état d'erreur en raison d'une exception non gérée dans la méthode qui retourne la tâche.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-141">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="ab6bc-142">L'attente de la tâche lève une exception.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-142">Awaiting the task throws an exception.</span></span> <span data-ttu-id="ab6bc-143">Une tâche peut également se terminer dans un état annulé si le processus asynchrone qui la retourne est annulé.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-143">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="ab6bc-144">L'attente d'une tâche annulée lève une `OperationCanceledException`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-144">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="ab6bc-145">Pour plus d’informations sur la façon d’annuler un processus asynchrone, consultez [Réglage de votre application Async](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="ab6bc-145">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>  
  
 <span data-ttu-id="ab6bc-146">Pour intercepter l'exception, attendez la tâche dans un bloc `try`, puis interceptez l'exception dans le bloc `catch` associé.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-146">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="ab6bc-147">Pour obtenir un exemple, consultez la section « Exemple ».</span><span class="sxs-lookup"><span data-stu-id="ab6bc-147">For an example, see the "Example" section.</span></span>  
  
 <span data-ttu-id="ab6bc-148">Une tâche peut être dans un état d'erreur car plusieurs exceptions se sont produites dans la méthode async attendue.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-148">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="ab6bc-149">Par exemple, la tâche peut être le résultat d'un appel à <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-149">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ab6bc-150">Quand vous attendez une telle tâche, une seule des exceptions est interceptée et vous ne pouvez pas prévoir laquelle.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-150">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="ab6bc-151">Pour obtenir un exemple, consultez la section « Exemple ».</span><span class="sxs-lookup"><span data-stu-id="ab6bc-151">For an example, see the "Example" section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab6bc-152">Exemple</span><span class="sxs-lookup"><span data-stu-id="ab6bc-152">Example</span></span>  
 <span data-ttu-id="ab6bc-153">Dans l'exemple suivant, le bloc `try` contient un appel à la méthode `ProcessString` qui risque de provoquer une exception.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-153">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="ab6bc-154">La clause `catch` clause contient le gestionnaire d'exceptions qui affiche simplement un message à l'écran.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-154">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="ab6bc-155">Quand l'instruction `throw` est appelée depuis `MyMethod`, le système recherche l'instruction `catch` et affiche le message `Exception caught`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-155">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>  
  
 [!code-csharp[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="ab6bc-156">Exemple</span><span class="sxs-lookup"><span data-stu-id="ab6bc-156">Example</span></span>  
 <span data-ttu-id="ab6bc-157">Dans l'exemple suivant, deux blocs catch sont utilisés, et l'exception la plus spécifique, qui apparaît la première, est interceptée.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-157">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>  
  
 <span data-ttu-id="ab6bc-158">Pour intercepter l'exception la moins spécifique, vous pouvez remplacer l'instruction throw dans `ProcessString` par l'instruction suivante : `throw new Exception()`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-158">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>  
  
 <span data-ttu-id="ab6bc-159">Si vous placez le bloc catch le moins spécifique en premier dans l'exemple, le message d'erreur suivant s'affiche : `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-159">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>  
  
 [!code-csharp[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="ab6bc-160">Exemple</span><span class="sxs-lookup"><span data-stu-id="ab6bc-160">Example</span></span>  
 <span data-ttu-id="ab6bc-161">L'exemple suivant illustre la gestion des exceptions pour les méthodes async.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-161">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="ab6bc-162">Pour intercepter une exception levée par une tâche async, placez l'expression `await` dans un bloc `try` et interceptez-la dans un bloc `catch`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-162">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>  
  
 <span data-ttu-id="ab6bc-163">Supprimez les marques de commentaire de la ligne `throw new Exception` dans l'exemple pour illustrer la gestion des exceptions.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-163">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="ab6bc-164">La propriété `IsFaulted` de la tâche a la valeur `True`, la propriété `Exception.InnerException` de la tâche a la valeur de l'exception et l'exception est interceptée dans le bloc `catch`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-164">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>  
  
 <span data-ttu-id="ab6bc-165">Supprimez les marques de commentaire de la ligne `throw new OperationCancelledException` pour montrer ce qui se passe quand vous annulez un processus asynchrone.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-165">Uncomment the `throw new OperationCancelledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="ab6bc-166">La propriété `IsCanceled` de la tâche a la valeur `true` et l'exception est interceptée dans le bloc `catch`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-166">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="ab6bc-167">Sous certaines conditions qui s'appliquent à cet exemple, la propriété `IsFaulted` de la tâche a la valeur `true` et `IsCanceled` a la valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-167">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>  
  
 [!code-csharp[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="ab6bc-168">Exemple</span><span class="sxs-lookup"><span data-stu-id="ab6bc-168">Example</span></span>  
 <span data-ttu-id="ab6bc-169">L’exemple suivant illustre la gestion des exceptions quand plusieurs tâches peuvent entraîner plusieurs exceptions.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-169">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="ab6bc-170">Le bloc `try` attend la tâche retournée par un appel à <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-170">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ab6bc-171">La tâche est terminée quand les trois tâches auxquelles WhenAll est appliqué sont terminées.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-171">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>  
  
 <span data-ttu-id="ab6bc-172">Chacune de ces trois tâches provoque une exception.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-172">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="ab6bc-173">Le bloc `catch` itère au sein des exceptions, qui sont trouvent dans la propriété `Exception.InnerExceptions` de la tâche retournée par <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ab6bc-173">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ab6bc-174">Spécification du langage C#</span><span class="sxs-lookup"><span data-stu-id="ab6bc-174">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab6bc-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab6bc-175">See Also</span></span>  
 [<span data-ttu-id="ab6bc-176">Référence C#</span><span class="sxs-lookup"><span data-stu-id="ab6bc-176">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ab6bc-177">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="ab6bc-177">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ab6bc-178">Mots clés C#</span><span class="sxs-lookup"><span data-stu-id="ab6bc-178">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ab6bc-179">Instructions try, throw et catch (C++)</span><span class="sxs-lookup"><span data-stu-id="ab6bc-179">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)  
 [<span data-ttu-id="ab6bc-180">Instructions de gestion des exceptions</span><span class="sxs-lookup"><span data-stu-id="ab6bc-180">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="ab6bc-181">throw</span><span class="sxs-lookup"><span data-stu-id="ab6bc-181">throw</span></span>](../../../csharp/language-reference/keywords/throw.md)  
 [<span data-ttu-id="ab6bc-182">try-finally</span><span class="sxs-lookup"><span data-stu-id="ab6bc-182">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
 [<span data-ttu-id="ab6bc-183">Guide pratique pour lever explicitement des exceptions</span><span class="sxs-lookup"><span data-stu-id="ab6bc-183">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)

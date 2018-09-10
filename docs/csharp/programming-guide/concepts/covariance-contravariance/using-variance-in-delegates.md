---
title: Utilisation de la variance dans les délégués (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 5be4f786d2e1b8a0ead3fd58fe056e188faa916a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501722"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="8c5e4-102">Utilisation de la variance dans les délégués (C#)</span><span class="sxs-lookup"><span data-stu-id="8c5e4-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="8c5e4-103">Quand vous assignez une méthode à un délégué, la *covariance* et la *contravariance* offrent une grande flexibilité pour la mise en correspondance d’un type délégué avec une signature de méthode.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="8c5e4-104">La covariance permet à une méthode d’avoir un type de retour qui est plus dérivé que celui défini dans le délégué.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="8c5e4-105">La contravariance autorise une méthode qui a des types de paramètres moins dérivés que ceux du type délégué.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="8c5e4-106">Exemple 1 : Covariance</span><span class="sxs-lookup"><span data-stu-id="8c5e4-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="8c5e4-107">Description</span><span class="sxs-lookup"><span data-stu-id="8c5e4-107">Description</span></span>  
 <span data-ttu-id="8c5e4-108">Cet exemple montre comment vous pouvez utiliser des délégués avec des méthodes ayant des types de retour dérivés du type de retour dans la signature du délégué.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="8c5e4-109">Le type de données retourné par `DogsHandler` est `Dogs`, qui dérive du type `Mammals` défini dans le délégué.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8c5e4-110">Code</span><span class="sxs-lookup"><span data-stu-id="8c5e4-110">Code</span></span>  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="8c5e4-111">Exemple 2 : Contravariance</span><span class="sxs-lookup"><span data-stu-id="8c5e4-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="8c5e4-112">Description</span><span class="sxs-lookup"><span data-stu-id="8c5e4-112">Description</span></span>  
 <span data-ttu-id="8c5e4-113">Cet exemple montre comment vous pouvez utiliser des délégués avec des méthodes ayant des paramètres d’un type qui sont des types de base du type de paramètre de la signature de délégué.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="8c5e4-114">Avec la contravariance, vous pouvez maintenant utiliser un gestionnaire d’événements plutôt que des gestionnaires distincts.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="8c5e4-115">Par exemple, vous pouvez créer un gestionnaire d’événements qui accepte un paramètre d’entrée `EventArgs` et l’utiliser avec un événement `Button.MouseClick` qui envoie un type `MouseEventArgs` comme paramètre, ainsi qu’avec un événement `TextBox.KeyDown` qui envoie un paramètre `KeyEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="8c5e4-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8c5e4-116">Code</span><span class="sxs-lookup"><span data-stu-id="8c5e4-116">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method   
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c5e4-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c5e4-117">See Also</span></span>

- [<span data-ttu-id="8c5e4-118">Variance dans les délégués (C#)</span><span class="sxs-lookup"><span data-stu-id="8c5e4-118">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)  
- [<span data-ttu-id="8c5e4-119">Utilisation de la variance pour les délégués génériques Func et Action (C#)</span><span class="sxs-lookup"><span data-stu-id="8c5e4-119">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)

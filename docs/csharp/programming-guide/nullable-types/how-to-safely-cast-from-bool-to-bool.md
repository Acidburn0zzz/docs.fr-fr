---
title: 'Comment : effectuer sans risque un cast du type bool? en bool (Guide de programmation C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
ms.openlocfilehash: e04e34abd477730f9dd01486ec6bddcde4943edc
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2018
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a><span data-ttu-id="2cc0d-102">Comment : effectuer sans risque un cast du type bool? en bool (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="2cc0d-102">How to: Safely Cast from bool? to bool (C# Programming Guide)</span></span>
<span data-ttu-id="2cc0d-103">Le type Nullable `bool?` peut contenir trois valeurs différentes : `true`, `false` et `null`.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-103">The `bool?` nullable type can contain three different values: `true`, `false`, and `null`.</span></span> <span data-ttu-id="2cc0d-104">Par conséquent, le type `bool?` ne peut pas être utilisé dans des instructions conditionnelles comme `if`, `for` ou `while`.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-104">Therefore, the `bool?` type cannot be used in conditionals such as with `if`, `for`, or `while`.</span></span> <span data-ttu-id="2cc0d-105">Par exemple, le code suivant génère une erreur du compilateur.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-105">For example, the following code causes a compiler error.</span></span>  
  
```csharp  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 <span data-ttu-id="2cc0d-106">Cela n’est pas autorisé, car il est difficile de savoir ce que `null` signifie dans le contexte d’une instruction conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-106">This is not allowed because it is unclear what `null` means in the context of a conditional.</span></span> <span data-ttu-id="2cc0d-107">Pour utiliser un `bool?` dans une instruction conditionnelle, examinez d’abord sa propriété <xref:System.Nullable%601.HasValue%2A> pour vérifier que sa valeur n’est pas `null`, puis castez-le en `bool`.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-107">To use a `bool?` in a conditional statement, first check its <xref:System.Nullable%601.HasValue%2A> property to ensure that its value is not `null`, and then cast it to `bool`.</span></span> <span data-ttu-id="2cc0d-108">Pour plus d'informations, consultez [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="2cc0d-108">For more information, see [bool](../../../csharp/language-reference/keywords/bool.md).</span></span> <span data-ttu-id="2cc0d-109">Si vous effectuez le cast sur un `bool?` avec la valeur `null`, une exception <xref:System.InvalidOperationException> est levée dans le test conditionnel.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-109">If you perform the cast on a `bool?` with a value of `null`, a <xref:System.InvalidOperationException> will be thrown in the conditional test.</span></span> <span data-ttu-id="2cc0d-110">L’exemple suivant illustre une façon d’effectuer sans risque un cast de `bool?` en `bool` :</span><span class="sxs-lookup"><span data-stu-id="2cc0d-110">The following example shows one way to safely cast from `bool?` to `bool`:</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cc0d-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="2cc0d-111">Example</span></span>  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cc0d-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2cc0d-112">See Also</span></span>  
 [<span data-ttu-id="2cc0d-113">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="2cc0d-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2cc0d-114">Mots clés littéraux</span><span class="sxs-lookup"><span data-stu-id="2cc0d-114">Literal Keywords</span></span>](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [<span data-ttu-id="2cc0d-115">Types Nullable</span><span class="sxs-lookup"><span data-stu-id="2cc0d-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="2cc0d-116">?? Opérateur</span><span class="sxs-lookup"><span data-stu-id="2cc0d-116">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)

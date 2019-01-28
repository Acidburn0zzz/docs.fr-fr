---
title: const, mot clé - Référence C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: f0b2b3632e767710bd31f5f6edaccaf0c2ef8c85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526975"
---
# <a name="const-c-reference"></a><span data-ttu-id="80eb2-102">const (référence C#)</span><span class="sxs-lookup"><span data-stu-id="80eb2-102">const (C# Reference)</span></span>

<span data-ttu-id="80eb2-103">Vous utilisez le mot clé `const` pour déclarer un champ constant ou un élément local constant.</span><span class="sxs-lookup"><span data-stu-id="80eb2-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="80eb2-104">Les champs et les éléments locaux constants ne sont pas des variables et ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="80eb2-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="80eb2-105">Les constantes peuvent être des chiffres, des valeurs booléennes, des chaînes ou une référence null.</span><span class="sxs-lookup"><span data-stu-id="80eb2-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="80eb2-106">Ne créez pas une constante pour représenter des informations qui doivent être modifiées.</span><span class="sxs-lookup"><span data-stu-id="80eb2-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="80eb2-107">Par exemple, n'utilisez pas un champ constant pour stocker le prix d'un service, le numéro de version du produit ou le nom de la marque d'une société.</span><span class="sxs-lookup"><span data-stu-id="80eb2-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="80eb2-108">Ces valeurs peuvent changer dans le temps, et dans la mesure où les compilateurs propagent les constantes, le code compilé avec vos bibliothèques devra être recompilé pour refléter ces modifications.</span><span class="sxs-lookup"><span data-stu-id="80eb2-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="80eb2-109">Consultez également le mot clé [readonly](../../../csharp/language-reference/keywords/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="80eb2-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="80eb2-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="80eb2-110">For example:</span></span>

```csharp
const int x = 0;
public const double gravitationalConstant = 6.673e-11;
private const string productName = "Visual C#";
```

## <a name="remarks"></a><span data-ttu-id="80eb2-111">Notes</span><span class="sxs-lookup"><span data-stu-id="80eb2-111">Remarks</span></span>

<span data-ttu-id="80eb2-112">Le type d'une déclaration constante indique le type des membres introduit par la déclaration.</span><span class="sxs-lookup"><span data-stu-id="80eb2-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="80eb2-113">L'initialiseur d'un élément local constant ou d'un champ constant doit être une expression constante qui peut être implicitement convertie en type cible.</span><span class="sxs-lookup"><span data-stu-id="80eb2-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>

<span data-ttu-id="80eb2-114">Une expression constante est une expression qui peut être complètement évaluée au moment de la compilation.</span><span class="sxs-lookup"><span data-stu-id="80eb2-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="80eb2-115">C'est pourquoi, les seules valeurs possibles pour les constantes des types référence sont `string` et une référence null.</span><span class="sxs-lookup"><span data-stu-id="80eb2-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>

<span data-ttu-id="80eb2-116">La déclaration constante peut déclarer plusieurs constantes, notamment :</span><span class="sxs-lookup"><span data-stu-id="80eb2-116">The constant declaration can declare multiple constants, such as:</span></span>

```csharp
public const double x = 1.0, y = 2.0, z = 3.0;
```

<span data-ttu-id="80eb2-117">Le modificateur `static` n'est pas autorisé dans une déclaration constante.</span><span class="sxs-lookup"><span data-stu-id="80eb2-117">The `static` modifier is not allowed in a constant declaration.</span></span>

<span data-ttu-id="80eb2-118">Une constante peut être utilisée dans une expression constante, comme suit :</span><span class="sxs-lookup"><span data-stu-id="80eb2-118">A constant can participate in a constant expression, as follows:</span></span>

```csharp
public const int c1 = 5;
public const int c2 = c1 + 100;
```

> [!NOTE]
> <span data-ttu-id="80eb2-119">Le mot clé [readonly](../../../csharp/language-reference/keywords/readonly.md) est différent du mot clé `const`.</span><span class="sxs-lookup"><span data-stu-id="80eb2-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="80eb2-120">Un champ `const` ne peut être initialisé qu'au moment de la déclaration du champ.</span><span class="sxs-lookup"><span data-stu-id="80eb2-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="80eb2-121">Un champ `readonly` peut être initialisé dans la déclaration ou dans un constructeur.</span><span class="sxs-lookup"><span data-stu-id="80eb2-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="80eb2-122">C'est pourquoi, les champs `readonly` peuvent avoir des valeurs différentes en fonction du constructeur utilisé.</span><span class="sxs-lookup"><span data-stu-id="80eb2-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="80eb2-123">De même, bien qu'un champ `const` soit une constante au moment de la compilation, le champ `readonly` peut être utilisé pour des constantes au moment de l'exécution, comme ci-après : `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="80eb2-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>

## <a name="example"></a><span data-ttu-id="80eb2-124">Exemple</span><span class="sxs-lookup"><span data-stu-id="80eb2-124">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a><span data-ttu-id="80eb2-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="80eb2-125">Example</span></span>

<span data-ttu-id="80eb2-126">Cet exemple montre comment utiliser des constantes en tant que variables locales.</span><span class="sxs-lookup"><span data-stu-id="80eb2-126">This example demonstrates how to use constants as local variables.</span></span>

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="80eb2-127">spécification du langage C#</span><span class="sxs-lookup"><span data-stu-id="80eb2-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="80eb2-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80eb2-128">See also</span></span>

- [<span data-ttu-id="80eb2-129">Référence C#</span><span class="sxs-lookup"><span data-stu-id="80eb2-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="80eb2-130">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="80eb2-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="80eb2-131">Mots clés C#</span><span class="sxs-lookup"><span data-stu-id="80eb2-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="80eb2-132">Modificateurs</span><span class="sxs-lookup"><span data-stu-id="80eb2-132">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
- [<span data-ttu-id="80eb2-133">readonly</span><span class="sxs-lookup"><span data-stu-id="80eb2-133">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)

---
title: "Procédure : Utiliser l'alias d'espace de noms global - Guide de programmation C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: 19d8d20ae630573b44399f8f5c5351f02b9fb1df
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236605"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="2e931-102">Procédure : Utiliser l'alias d'espace de noms global (Guide de programmation C#)</span><span class="sxs-lookup"><span data-stu-id="2e931-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="2e931-103">La possibilité d’accéder à un membre dans l’[espace de noms ](../../../csharp/language-reference/keywords/namespace.md) global est utile quand le membre peut être masqué par une autre entité de même nom.</span><span class="sxs-lookup"><span data-stu-id="2e931-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="2e931-104">Par exemple, dans le code suivant, `Console` est résolu en `TestApp.Console` plutôt qu’en type `Console` dans l’espace de noms <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="2e931-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 <span data-ttu-id="2e931-105">L’utilisation de `System.Console` continue de générer une erreur, car l’espace de noms `System` est masqué par la classe `TestApp.System` :</span><span class="sxs-lookup"><span data-stu-id="2e931-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 <span data-ttu-id="2e931-106">Cependant, vous pouvez contourner cette erreur en utilisant `global::System.Console`, comme ceci :</span><span class="sxs-lookup"><span data-stu-id="2e931-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 <span data-ttu-id="2e931-107">Quand l’identificateur de gauche est `global`, la recherche de l’identificateur de droite débute dans l’espace de noms global.</span><span class="sxs-lookup"><span data-stu-id="2e931-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="2e931-108">Par exemple, la déclaration suivante fait référence à `TestApp` en tant que membre de l’espace global.</span><span class="sxs-lookup"><span data-stu-id="2e931-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 <span data-ttu-id="2e931-109">Bien entendu, il n’est pas recommandé de créer des espaces de noms personnalisés sous le nom `System`, et il est peu probable que vous en rencontriez dans du code.</span><span class="sxs-lookup"><span data-stu-id="2e931-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="2e931-110">Cependant, dans les projets à grande échelle, il est tout à fait possible qu’un espace de noms soit dupliqué d’une façon ou d’une autre.</span><span class="sxs-lookup"><span data-stu-id="2e931-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="2e931-111">En pareil cas, le qualificateur d’espace de noms global est la garantie que vous pouvez spécifier l’espace de noms racine.</span><span class="sxs-lookup"><span data-stu-id="2e931-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e931-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="2e931-112">Example</span></span>  
 <span data-ttu-id="2e931-113">Dans cet exemple, l’espace de noms `System` est utilisé pour inclure la classe `TestClass`. De ce fait, `global::System.Console` doit être utilisé pour faire référence à la classe `System.Console`, qui est masquée par l’espace de noms `System`.</span><span class="sxs-lookup"><span data-stu-id="2e931-113">In this example, the namespace `System` is used to include the class `TestClass` therefore, `global::System.Console` must be used to reference the `System.Console` class, which is hidden by the `System` namespace.</span></span> <span data-ttu-id="2e931-114">Par ailleurs, l’alias `colAlias` est utilisé pour faire référence à l’espace de noms `System.Collections` ; par conséquent, l’instance d’un <xref:System.Collections.Hashtable?displayProperty=nameWithType> a été créée en utilisant cet alias plutôt que l’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="2e931-114">Also, the alias `colAlias` is used to refer to the namespace `System.Collections`; therefore, the instance of a <xref:System.Collections.Hashtable?displayProperty=nameWithType> was created using this alias instead of the namespace.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
<span data-ttu-id="2e931-115">**A 1**
**B 2**
**C 3**</span><span class="sxs-lookup"><span data-stu-id="2e931-115">**A 1**
**B 2**
**C 3**</span></span>

## <a name="see-also"></a><span data-ttu-id="2e931-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e931-116">See Also</span></span>

- [<span data-ttu-id="2e931-117">Guide de programmation C#</span><span class="sxs-lookup"><span data-stu-id="2e931-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2e931-118">Espaces de noms</span><span class="sxs-lookup"><span data-stu-id="2e931-118">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
- [<span data-ttu-id="2e931-119">. Opérateur</span><span class="sxs-lookup"><span data-stu-id="2e931-119">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="2e931-120">:: Opérateur</span><span class="sxs-lookup"><span data-stu-id="2e931-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="2e931-121">extern</span><span class="sxs-lookup"><span data-stu-id="2e931-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

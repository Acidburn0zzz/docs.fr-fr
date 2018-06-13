---
title: Types de méthodes de manipulation de chaînes en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 11903e067c064f129ecd2df80244edb6741c73be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648692"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="622c2-102">Types de méthodes de manipulation de chaînes en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="622c2-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="622c2-103">Il existe plusieurs façons différentes pour analyser et manipuler des chaînes.</span><span class="sxs-lookup"><span data-stu-id="622c2-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="622c2-104">Certaines méthodes font partie du langage Visual Basic, et d’autres sont inhérentes à la `String` classe.</span><span class="sxs-lookup"><span data-stu-id="622c2-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="622c2-105">Langage Visual Basic et .NET Framework</span><span class="sxs-lookup"><span data-stu-id="622c2-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="622c2-106">Les méthodes de Visual Basic sont utilisées en tant que fonctions inhérentes du langage.</span><span class="sxs-lookup"><span data-stu-id="622c2-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="622c2-107">Ils peuvent être utilisés sans qualification dans votre code.</span><span class="sxs-lookup"><span data-stu-id="622c2-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="622c2-108">L’exemple suivant illustre une utilisation classique d’une commande de manipulation de chaînes Visual Basic :</span><span class="sxs-lookup"><span data-stu-id="622c2-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="622c2-109">Dans cet exemple, le `Mid` fonction effectue une opération directe sur `aString` et affecte la valeur à `bString`.</span><span class="sxs-lookup"><span data-stu-id="622c2-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="622c2-110">Pour obtenir la liste des méthodes de manipulation de chaîne Visual Basic, consultez [résumé de Manipulation de chaîne](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="622c2-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="622c2-111">Méthodes partagées et des méthodes d’Instance</span><span class="sxs-lookup"><span data-stu-id="622c2-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="622c2-112">Vous pouvez également manipuler des chaînes avec les méthodes de la `String` classe.</span><span class="sxs-lookup"><span data-stu-id="622c2-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="622c2-113">Il existe deux types de méthodes de `String`: *partagé* méthodes et *instance* méthodes.</span><span class="sxs-lookup"><span data-stu-id="622c2-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="622c2-114">Méthodes partagées</span><span class="sxs-lookup"><span data-stu-id="622c2-114">Shared Methods</span></span>  
 <span data-ttu-id="622c2-115">Une méthode partagée est une méthode qui provient du `String` classe proprement dit et ne nécessite pas une instance de cette classe.</span><span class="sxs-lookup"><span data-stu-id="622c2-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="622c2-116">Ces méthodes peuvent être qualifiés avec le nom de la classe (`String`) plutôt qu’avec une instance de la `String` classe.</span><span class="sxs-lookup"><span data-stu-id="622c2-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="622c2-117">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622c2-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="622c2-118">Dans l’exemple précédent, le <xref:System.String.Copy%2A?displayProperty=nameWithType> méthode est une méthode statique, qui agit sur une expression qui lui est attribuée et affecte la valeur obtenue dans `bString`.</span><span class="sxs-lookup"><span data-stu-id="622c2-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="622c2-119">Méthodes d’instance</span><span class="sxs-lookup"><span data-stu-id="622c2-119">Instance Methods</span></span>  
 <span data-ttu-id="622c2-120">Méthodes d’instance, en revanche, proviennent d’une instance particulière de `String` et doit être qualifié avec le nom d’instance.</span><span class="sxs-lookup"><span data-stu-id="622c2-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="622c2-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="622c2-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="622c2-122">Dans cet exemple, le <xref:System.String.Substring%2A?displayProperty=nameWithType> méthode est une méthode de l’instance de `String` (autrement dit, `aString`).</span><span class="sxs-lookup"><span data-stu-id="622c2-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="622c2-123">Il effectue une opération sur `aString` et assigne la valeur à `bString`.</span><span class="sxs-lookup"><span data-stu-id="622c2-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="622c2-124">Pour plus d’informations, consultez la documentation relative à la <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="622c2-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="622c2-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="622c2-125">See Also</span></span>  
 [<span data-ttu-id="622c2-126">Introduction aux chaînes en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="622c2-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

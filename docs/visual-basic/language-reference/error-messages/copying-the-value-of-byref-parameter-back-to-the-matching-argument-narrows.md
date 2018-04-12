---
title: Copie la valeur des &#39; ByRef &#39; paramètre &#39; &lt;nom_paramètre&gt;&#39; retour à la correspondance restreint d’argument de type &#39;&lt; NomType1&gt;&#39; en type &#39;&lt; nom_type2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4bf993639007162e2e17d4b8cb9dfe8d5316acaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="3eb3a-102">Copie la valeur des &#39; ByRef &#39; paramètre &#39; &lt;nom_paramètre&gt;&#39; retour à la correspondance restreint d’argument de type &#39;&lt; NomType1&gt;&#39; en type &#39;&lt; nom_type2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="3eb3a-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="3eb3a-103">Une procédure est appelée avec un argument qui s’étend au type de paramètre correspondant, et la conversion à partir du paramètre à l’argument est restrictive.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="3eb3a-104">Quand vous définissez une classe ou une structure, vous pouvez définir un ou plusieurs opérateurs de conversion pour convertir le type de la classe ou de la structure en d’autres types.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="3eb3a-105">Vous pouvez également définir des opérateurs de conversion inverse pour convertir ces autres types vers le type de votre classe ou de votre structure.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="3eb3a-106">Quand vous utilisez votre type de classe ou de structure dans un appel de procédure, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] peut utiliser ces opérateurs de conversion pour convertir le type d’un argument vers le type de son paramètre correspondant.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-106">When you use your class or structure type in a procedure call, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="3eb3a-107">Si vous passez l’argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] copie parfois la valeur d’argument dans une variable locale de la procédure au lieu de passer une référence.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="3eb3a-108">Dans ce cas, quand la procédure est retournée, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] doit recopier la valeur de la variable locale dans l’argument du code appelant.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-108">In such a case, when the procedure returns, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="3eb3a-109">Si une valeur d’argument `ByRef` est copiée dans la procédure, et si l’argument et le paramètre sont du même type, aucune conversion n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="3eb3a-110">Toutefois, si les types sont différents, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] doit effectuer une conversion dans les deux sens.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-110">But if the types are different, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert in both directions.</span></span> <span data-ttu-id="3eb3a-111">Si l’un des types est celui de votre classe ou de votre structure, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] doit le convertir vers et à partir de l’autre type.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-111">If one of the types is your class or structure type, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert it both to and from the other type.</span></span> <span data-ttu-id="3eb3a-112">Si une de ces conversions est étendue, la conversion inverse peut être restrictive.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="3eb3a-113">**ID d’erreur :** BC32053</span><span class="sxs-lookup"><span data-stu-id="3eb3a-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3eb3a-114">Pour corriger cette erreur</span><span class="sxs-lookup"><span data-stu-id="3eb3a-114">To correct this error</span></span>  
  
-   <span data-ttu-id="3eb3a-115">Si possible, utilisez un argument d’appel du même type que celui du paramètre de procédure, pour que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] n’ait pas besoin d’effectuer de conversion.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-115">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="3eb3a-116">Si vous avez besoin d’appeler la procédure avec un argument de type différent du type de paramètre, mais n’avez pas besoin de retourner une valeur dans l’argument d’appel, définissez le paramètre [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) au lieu de `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="3eb3a-117">Si vous devez retourner une valeur dans l’argument d’appel, définissez l’opérateur de conversion inverse comme [Widening](../../../visual-basic/language-reference/modifiers/widening.md), si possible.</span><span class="sxs-lookup"><span data-stu-id="3eb3a-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb3a-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3eb3a-118">See Also</span></span>  
 [<span data-ttu-id="3eb3a-119">Procédures</span><span class="sxs-lookup"><span data-stu-id="3eb3a-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="3eb3a-120">Paramètres et arguments d’une procédure</span><span class="sxs-lookup"><span data-stu-id="3eb3a-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="3eb3a-121">Passage d’un argument par valeur et par référence</span><span class="sxs-lookup"><span data-stu-id="3eb3a-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="3eb3a-122">Procédures d’opérateur</span><span class="sxs-lookup"><span data-stu-id="3eb3a-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="3eb3a-123">Operator (instruction)</span><span class="sxs-lookup"><span data-stu-id="3eb3a-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="3eb3a-124">Guide pratique : définir un opérateur</span><span class="sxs-lookup"><span data-stu-id="3eb3a-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="3eb3a-125">Guide pratique : définir un opérateur de conversion</span><span class="sxs-lookup"><span data-stu-id="3eb3a-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="3eb3a-126">Conversions de type dans Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3eb3a-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="3eb3a-127">Conversions étendues et restrictives</span><span class="sxs-lookup"><span data-stu-id="3eb3a-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)

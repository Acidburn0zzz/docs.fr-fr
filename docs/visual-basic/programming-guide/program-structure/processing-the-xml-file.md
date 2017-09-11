---
title: Traitement du fichier XML (Visual Basic) | Documents Microsoft
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
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
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
ms.openlocfilehash: cf15cf59413e0e019086dd1a79951ccb212f037b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="ab73f-102">Traitement du fichier XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab73f-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="ab73f-103">Le compilateur génère une chaîne d’identification pour chaque construction de votre code qui est marqué pour générer la documentation.</span><span class="sxs-lookup"><span data-stu-id="ab73f-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="ab73f-104">(Pour plus d’informations sur la façon de balises à votre code, consultez [balises de commentaire XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) La chaîne d’ID identifie de façon unique la construction.</span><span class="sxs-lookup"><span data-stu-id="ab73f-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="ab73f-105">Les programmes qui traitent le fichier XML peuvent utiliser la chaîne d’ID pour identifier le correspondant [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] élément de métadonnées/réflexion.</span><span class="sxs-lookup"><span data-stu-id="ab73f-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="ab73f-106">Le fichier XML n’est pas une représentation hiérarchique de votre code. Il est une simple liste comportant un identificateur généré pour chaque élément.</span><span class="sxs-lookup"><span data-stu-id="ab73f-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="ab73f-107">Le compilateur respecte les règles suivantes lorsqu’il génère les chaînes d’identification :</span><span class="sxs-lookup"><span data-stu-id="ab73f-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="ab73f-108">Aucun espace blanc n’est placé dans la chaîne.</span><span class="sxs-lookup"><span data-stu-id="ab73f-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="ab73f-109">La première partie de la chaîne d’identification identifie le type de membre identifié, avec un caractère unique suivi par un signe deux-points.</span><span class="sxs-lookup"><span data-stu-id="ab73f-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="ab73f-110">Les membres suivants sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="ab73f-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="ab73f-111">Caractère</span><span class="sxs-lookup"><span data-stu-id="ab73f-111">Character</span></span>|<span data-ttu-id="ab73f-112">Description</span><span class="sxs-lookup"><span data-stu-id="ab73f-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="ab73f-113">N</span><span class="sxs-lookup"><span data-stu-id="ab73f-113">N</span></span>|<span data-ttu-id="ab73f-114">namespace</span><span class="sxs-lookup"><span data-stu-id="ab73f-114">namespace</span></span><br /><br /> <span data-ttu-id="ab73f-115">Vous ne pouvez pas ajouter des commentaires de documentation à un espace de noms, mais vous pouvez effectuer les références CREF, prise en charge.</span><span class="sxs-lookup"><span data-stu-id="ab73f-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="ab73f-116">T</span><span class="sxs-lookup"><span data-stu-id="ab73f-116">T</span></span>|<span data-ttu-id="ab73f-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`</span><span class="sxs-lookup"><span data-stu-id="ab73f-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="ab73f-118">F</span><span class="sxs-lookup"><span data-stu-id="ab73f-118">F</span></span>|<span data-ttu-id="ab73f-119">champ :`Dim`</span><span class="sxs-lookup"><span data-stu-id="ab73f-119">field: `Dim`</span></span>|  
|<span data-ttu-id="ab73f-120">P</span><span class="sxs-lookup"><span data-stu-id="ab73f-120">P</span></span>|<span data-ttu-id="ab73f-121">propriété : `Property` (y compris les propriétés par défaut)</span><span class="sxs-lookup"><span data-stu-id="ab73f-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="ab73f-122">M</span><span class="sxs-lookup"><span data-stu-id="ab73f-122">M</span></span>|<span data-ttu-id="ab73f-123">method: `Sub`, `Function`, `Declare`,`Operator`</span><span class="sxs-lookup"><span data-stu-id="ab73f-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="ab73f-124">E</span><span class="sxs-lookup"><span data-stu-id="ab73f-124">E</span></span>|<span data-ttu-id="ab73f-125">événement :`Event`</span><span class="sxs-lookup"><span data-stu-id="ab73f-125">event: `Event`</span></span>|  
|<span data-ttu-id="ab73f-126">!</span><span class="sxs-lookup"><span data-stu-id="ab73f-126">!</span></span>|<span data-ttu-id="ab73f-127">chaîne d’erreur</span><span class="sxs-lookup"><span data-stu-id="ab73f-127">error string</span></span><br /><br /> <span data-ttu-id="ab73f-128">Le reste de la chaîne fournit des informations sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="ab73f-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="ab73f-129">Le [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilateur génère des informations d’erreur pour les liens qui ne peut pas être résolus.</span><span class="sxs-lookup"><span data-stu-id="ab73f-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="ab73f-130">La deuxième partie de la `String` est le nom qualifié complet de l’élément, en commençant à la racine de l’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="ab73f-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="ab73f-131">Le nom de l’élément, ses types englobants et l’espace de noms sont séparés par des points.</span><span class="sxs-lookup"><span data-stu-id="ab73f-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="ab73f-132">Si le nom de l’élément lui-même comporte des points, ils sont remplacés par le signe dièse (#).</span><span class="sxs-lookup"><span data-stu-id="ab73f-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="ab73f-133">Il est supposé qu’aucun élément n’a un signe dièse directement dans son nom.</span><span class="sxs-lookup"><span data-stu-id="ab73f-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="ab73f-134">Par exemple, le nom qualifié complet de le `String` constructeur serait `System.String.#ctor`.</span><span class="sxs-lookup"><span data-stu-id="ab73f-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="ab73f-135">Pour les propriétés et méthodes, s’il existe des arguments de la méthode, la liste d’arguments entre parenthèses suit.</span><span class="sxs-lookup"><span data-stu-id="ab73f-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="ab73f-136">S’il n’y a pas d’arguments, aucune parenthèse n’est présent.</span><span class="sxs-lookup"><span data-stu-id="ab73f-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="ab73f-137">Les arguments sont séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="ab73f-137">The arguments are separated by commas.</span></span> <span data-ttu-id="ab73f-138">L’encodage de chaque argument correspond directement à son encodage dans une [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] signature.</span><span class="sxs-lookup"><span data-stu-id="ab73f-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab73f-139">Exemple</span><span class="sxs-lookup"><span data-stu-id="ab73f-139">Example</span></span>  
 <span data-ttu-id="ab73f-140">Le code suivant montre comment les chaînes d’identification pour une classe et ses membres sont générés.</span><span class="sxs-lookup"><span data-stu-id="ab73f-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 <span data-ttu-id="ab73f-141">[!code-vb[VbVbcnXmlDocComments&#10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ab73f-141">[!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab73f-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab73f-142">See Also</span></span>  
 <span data-ttu-id="ab73f-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="ab73f-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="ab73f-144"> [Guide pratique : créer une documentation XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="ab73f-144"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>

---
title: Conventions de codage Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: b686747b46529b53b0802a7deb38b5b4949f4d5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655359"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="8e0cf-102">Conventions de codage Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e0cf-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="8e0cf-103">Microsoft développe des exemples et la documentation qui suivent les instructions de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="8e0cf-104">Si vous suivez les mêmes conventions de codage, vous pouvez profiter des avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="8e0cf-105">Votre code aura une apparence cohérente, afin que les lecteurs peuvent mieux se concentrer sur le contenu, pas de disposition.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="8e0cf-106">Lecteurs de comprennent votre code plus rapidement, car ils peuvent émettre des hypothèses selon leur expérience précédente.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="8e0cf-107">Vous pouvez copier, modifier et gérer le code plus facilement.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="8e0cf-108">Vous permettent de garantir que votre code illustre les « meilleures pratiques » pour Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="8e0cf-109">Conventions d'affectation de noms</span><span class="sxs-lookup"><span data-stu-id="8e0cf-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="8e0cf-110">Pour plus d’informations sur les règles d’affectation de noms, consultez [les instructions d’affectation de noms](../../../standard/design-guidelines/naming-guidelines.md) rubrique.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="8e0cf-111">N’utilisez pas « Mon » ou « my » en tant que partie d’un nom de variable.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="8e0cf-112">Cette pratique peut créer une confusion avec les `My` objets.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="8e0cf-113">Il est inutile de modifier les noms des objets dans le code généré automatiquement pour les rendre conformes aux indications.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="8e0cf-114">Conventions de disposition</span><span class="sxs-lookup"><span data-stu-id="8e0cf-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="8e0cf-115">Insérer des tabulations en espaces et utiliser la mise en retrait intelligente avec tirets de quatre espaces.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="8e0cf-116">Utilisez **(Reformatage) d’un code de liste automatique** à remettre en forme votre code dans l’éditeur de code.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="8e0cf-117">Pour plus d’informations, consultez [Options, éditeur de texte, base (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8e0cf-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="8e0cf-118">Utilisez une seule instruction par ligne.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-118">Use only one statement per line.</span></span> <span data-ttu-id="8e0cf-119">N’utilisez pas le caractère de séparation de ligne Visual Basic ( :).</span><span class="sxs-lookup"><span data-stu-id="8e0cf-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="8e0cf-120">Évitez d’utiliser le caractère de continuation de ligne explicite « _ » en faveur de la continuation de ligne implicite, partout où il permet à la langue.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="8e0cf-121">Utiliser une seule déclaration par ligne.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="8e0cf-122">Si **(Reformatage) d’un code de liste automatique** ne format des lignes de continuation automatiquement, manuellement mettre en retrait continuation lignes un taquet de tabulation.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="8e0cf-123">Toutefois, toujours aligner à gauche des éléments dans une liste.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="8e0cf-124">Ajoutez au moins une ligne vide entre les définitions de méthode et la propriété.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="8e0cf-125">Conventions de commentaires</span><span class="sxs-lookup"><span data-stu-id="8e0cf-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="8e0cf-126">Placer des commentaires sur une ligne distincte et non à la fin d’une ligne de code.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="8e0cf-127">Démarrez le texte de commentaire par une lettre majuscule et texte de commentaire de fin avec une période.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="8e0cf-128">Insérer un espace entre le délimiteur de commentaire (') et le texte du commentaire.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   <span data-ttu-id="8e0cf-129">N’encadrez pas de commentaires avec les blocs d’astérisques mis en forme.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="8e0cf-130">Structure du programme</span><span class="sxs-lookup"><span data-stu-id="8e0cf-130">Program Structure</span></span>  
  
-   <span data-ttu-id="8e0cf-131">Lorsque vous utilisez la `Main` (méthode), utilisez la construction par défaut pour les nouvelles applications de console et `My` pour les arguments de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="8e0cf-132">Directives du langage</span><span class="sxs-lookup"><span data-stu-id="8e0cf-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="8e0cf-133">String, type de données</span><span class="sxs-lookup"><span data-stu-id="8e0cf-133">String Data Type</span></span>  
  
-   <span data-ttu-id="8e0cf-134">Pour concaténer des chaînes, utilisez une esperluette (&).</span><span class="sxs-lookup"><span data-stu-id="8e0cf-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   <span data-ttu-id="8e0cf-135">Pour ajouter des chaînes dans des boucles, utilisez le <xref:System.Text.StringBuilder> objet.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="8e0cf-136">Délégués souples dans les gestionnaires d’événements</span><span class="sxs-lookup"><span data-stu-id="8e0cf-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="8e0cf-137">Ne relèvent pas explicitement les arguments (objet et EventArgs) aux gestionnaires d’événements.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="8e0cf-138">Si vous n’utilisez pas les arguments d’événement sont passés à un événement (par exemple, l’expéditeur en tant qu’objet, e en tant que EventArgs), utilisez des délégués souples et omettre les arguments d’événement dans votre code :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="8e0cf-139">Type de données non signé</span><span class="sxs-lookup"><span data-stu-id="8e0cf-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="8e0cf-140">Utilisez `Integer` plutôt que des types non signés, sauf s’ils sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="8e0cf-141">Tableaux</span><span class="sxs-lookup"><span data-stu-id="8e0cf-141">Arrays</span></span>  
  
-   <span data-ttu-id="8e0cf-142">Utilisez la syntaxe courte lorsque vous initialisez des tableaux sur la ligne de déclaration.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="8e0cf-143">Par exemple, utilisez la syntaxe suivante.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     <span data-ttu-id="8e0cf-144">N’utilisez pas la syntaxe suivante.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   <span data-ttu-id="8e0cf-145">Placez l’indicateur de tableau sur le type, et non sur la variable.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="8e0cf-146">Par exemple, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     <span data-ttu-id="8e0cf-147">N’utilisez pas la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   <span data-ttu-id="8e0cf-148">Utilisez la syntaxe {} lorsque vous déclarez et initialisez des tableaux de types de base de données.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="8e0cf-149">Par exemple, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="8e0cf-150">N’utilisez pas la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="8e0cf-151">Utilisez le mot clé</span><span class="sxs-lookup"><span data-stu-id="8e0cf-151">Use the With Keyword</span></span>  
 <span data-ttu-id="8e0cf-152">Lorsque vous effectuez une série d’appels à un objet, envisagez d’utiliser le `With` (mot clé) :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="8e0cf-153">Utilisez les instructions Try... Capture et à l’aide des instructions lorsque vous utilisez la gestion des exceptions</span><span class="sxs-lookup"><span data-stu-id="8e0cf-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="8e0cf-154">N’utilisez pas `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="8e0cf-155">Utilisez le mot clé IsNot</span><span class="sxs-lookup"><span data-stu-id="8e0cf-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="8e0cf-156">Utilisez le `IsNot` (mot clé) au lieu de `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="8e0cf-157">Nouveau mot clé</span><span class="sxs-lookup"><span data-stu-id="8e0cf-157">New Keyword</span></span>  
  
-   <span data-ttu-id="8e0cf-158">Utilisez l’instanciation courte.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-158">Use short instantiation.</span></span> <span data-ttu-id="8e0cf-159">Par exemple, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     <span data-ttu-id="8e0cf-160">La ligne précédente est équivalente à ceci :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   <span data-ttu-id="8e0cf-161">Utiliser des initialiseurs d’objets pour les nouveaux objets au lieu du constructeur sans paramètre :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a><span data-ttu-id="8e0cf-162">Gestion des événements</span><span class="sxs-lookup"><span data-stu-id="8e0cf-162">Event Handling</span></span>  
  
-   <span data-ttu-id="8e0cf-163">Utilisez `Handles` plutôt que `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="8e0cf-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   <span data-ttu-id="8e0cf-164">Utilisez `AddressOf`et n’instanciez pas le délégué explicitement :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   <span data-ttu-id="8e0cf-165">Lorsque vous définissez un événement, utilisez la syntaxe courte et laissez le compilateur définir le délégué :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   <span data-ttu-id="8e0cf-166">Ne vérifient pas si un événement est `Nothing` (null) avant d’appeler le `RaiseEvent` (méthode).</span><span class="sxs-lookup"><span data-stu-id="8e0cf-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="8e0cf-167">`RaiseEvent` vérifie les `Nothing` avant de déclencher l’événement.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="8e0cf-168">À l’aide de membres partagés</span><span class="sxs-lookup"><span data-stu-id="8e0cf-168">Using Shared Members</span></span>  
 <span data-ttu-id="8e0cf-169">Appelez `Shared` membres en utilisant le nom de classe, pas à partir d’une variable d’instance.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="8e0cf-170">Utiliser des littéraux XML</span><span class="sxs-lookup"><span data-stu-id="8e0cf-170">Use XML Literals</span></span>  
 <span data-ttu-id="8e0cf-171">Les littéraux XML simplifient les tâches les plus courantes que vous rencontrez lorsque vous travaillez avec XML (par exemple, chargement, requête et transformation).</span><span class="sxs-lookup"><span data-stu-id="8e0cf-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="8e0cf-172">Lorsque vous développez avec XML, suivez ces instructions :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="8e0cf-173">Utiliser des littéraux XML pour créer des documents XML et des fragments au lieu d’appeler directement des API XML.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="8e0cf-174">Importez les espaces de noms XML au niveau du fichier ou du projet pour tirer parti des optimisations des performances des littéraux XML.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="8e0cf-175">Utilisez les propriétés d’axe XML pour accéder aux éléments et attributs dans un document XML.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="8e0cf-176">Utiliser des expressions incorporées pour inclure des valeurs et créer du code XML à partir de valeurs existantes au lieu d’utiliser des appels d’API tels que le `Add` méthode :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a><span data-ttu-id="8e0cf-177">Requêtes LINQ</span><span class="sxs-lookup"><span data-stu-id="8e0cf-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="8e0cf-178">Utilisez des noms explicites pour les variables de requête :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   <span data-ttu-id="8e0cf-179">Fournir des noms pour les éléments d’une requête pour vous assurer que les noms de propriété des types anonymes sont correctement écrits en majuscules à l’aide de la casse Pascal casse :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   <span data-ttu-id="8e0cf-180">Renommez les propriétés lorsque les noms de propriétés dans le résultat sont ambigus.</span><span class="sxs-lookup"><span data-stu-id="8e0cf-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="8e0cf-181">Par exemple, si votre requête retourne un client, nom et un ID de commande, les renommer au lieu de les laisser en tant que `Name` et `ID` dans le résultat :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   <span data-ttu-id="8e0cf-182">Utiliser l’inférence de type dans la déclaration de variables de requête et les variables de portée :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   <span data-ttu-id="8e0cf-183">Alignez les clauses de requête sous la `From` instruction :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   <span data-ttu-id="8e0cf-184">Utilisez `Where` clauses avant les autres clauses de requête afin que les clauses de requête ultérieures opèrent sur l’ensemble filtré de données :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   <span data-ttu-id="8e0cf-185">Utilisez le `Join` clause pour définir explicitement une opération de jointure au lieu d’utiliser le `Where` clause définir implicitement une opération de jointure :</span><span class="sxs-lookup"><span data-stu-id="8e0cf-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8e0cf-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e0cf-186">See Also</span></span>  
 [<span data-ttu-id="8e0cf-187">Instructions de codage sécurisé</span><span class="sxs-lookup"><span data-stu-id="8e0cf-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)

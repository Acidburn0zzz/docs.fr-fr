---
title: "Génération d’une bibliothèque de classes avec Visual Basic et .NET Core dans Visual Studio 2017"
description: "Découvrez comment créer une bibliothèque de classes écrite en Visual Basic à l’aide de Visual Studio 2017"
keywords: ".NET Core, bibliothèque de classes .NET Standard, Visual Studio 2017, Visual Basic"
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-vb
dev_langs:
- vb
ms.workload:
- dotnetcore
ms.openlocfilehash: b8d87e3a97e2ffeb8e8712bfa5d178bb855f402d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/23/2017
---
# <a name="building-a-class-library-with-visual-basic-and-net-core-in-visual-studio-2017"></a><span data-ttu-id="b347d-104">Génération d’une bibliothèque de classes avec Visual Basic et .NET Core dans Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="b347d-104">Building a class library with Visual Basic and .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="b347d-105">Une *bibliothèque de classes* définit des types et des méthodes qui peuvent être appelés par une application.</span><span class="sxs-lookup"><span data-stu-id="b347d-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="b347d-106">Une bibliothèque de classes qui cible .NET Standard 2.0 permet à votre bibliothèque d’être appelée par n’importe quelle implémentation .NET qui prend en charge cette version de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="b347d-106">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="b347d-107">Quand vous avez terminé votre bibliothèque de classes, vous pouvez décider de la distribuer ou non comme un composant tiers, ou de l’inclure ou non dans un composant groupé avec une ou plusieurs applications.</span><span class="sxs-lookup"><span data-stu-id="b347d-107">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="b347d-108">Pour obtenir la liste des versions de .NET Standard et des plateformes prises en charge, consultez [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="b347d-108">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="b347d-109">Dans cette rubrique, vous créez une bibliothèque d’utilitaire simple qui contient une seule méthode de gestion de chaîne.</span><span class="sxs-lookup"><span data-stu-id="b347d-109">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="b347d-110">Vous l’implémentez en tant que [méthode d’extension](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md), pour pouvoir l’appeler comme s’il s’agissait d’un membre de la classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="b347d-110">You'll implement it as an [extension method](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="b347d-111">Création d'une solution de bibliothèque de classes</span><span class="sxs-lookup"><span data-stu-id="b347d-111">Creating a class library solution</span></span>

<span data-ttu-id="b347d-112">Commencez par créer une solution pour votre projet de bibliothèque de classes et ses projets connexes.</span><span class="sxs-lookup"><span data-stu-id="b347d-112">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="b347d-113">Une solution Visual Studio sert simplement de conteneur pour un ou plusieurs projets.</span><span class="sxs-lookup"><span data-stu-id="b347d-113">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="b347d-114">Pour créer la solution :</span><span class="sxs-lookup"><span data-stu-id="b347d-114">To create the solution:</span></span>

1. <span data-ttu-id="b347d-115">Dans la barre de menus de Visual Studio, choisissez **Fichier** > **Nouveau** > **Projet**.</span><span class="sxs-lookup"><span data-stu-id="b347d-115">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="b347d-116">Dans la boîte de dialogue **Nouveau projet**, développez le nœud **Autres types de projets** et sélectionnez **Solutions Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b347d-116">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="b347d-117">Nommez la solution « ClassLibraryProjects » puis sélectionnez le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="b347d-117">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Boîte de dialogue Nouveau projet](./media/library-with-visual-studio/newproject.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="b347d-119">Création du projet de bibliothèque de classes</span><span class="sxs-lookup"><span data-stu-id="b347d-119">Creating the class library project</span></span>

<span data-ttu-id="b347d-120">Créez votre projet de bibliothèque de classes :</span><span class="sxs-lookup"><span data-stu-id="b347d-120">Create your class library project:</span></span>

1. <span data-ttu-id="b347d-121">Dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur la solution **ClassLibraryProjects** et, dans le menu contextuel, sélectionnez **Ajouter** > **Nouveau projet**.</span><span class="sxs-lookup"><span data-stu-id="b347d-121">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="b347d-122">Dans la boîte de dialogue **Ajouter un nouveau projet**, développez le nœud **Visual Basic**, puis sélectionnez le nœud **.NET Standard** et choisissez le modèle de projet **Bibliothèque de classes (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="b347d-122">In the **Add New Project** dialog, expand the **Visual Basic** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="b347d-123">Dans la zone de texte **Nom**, entrez « StringLibrary » comme nom de projet.</span><span class="sxs-lookup"><span data-stu-id="b347d-123">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="b347d-124">Sélectionnez **OK** pour créer le projet de bibliothèque de classes.</span><span class="sxs-lookup"><span data-stu-id="b347d-124">Select **OK** to create the class library project.</span></span>

   ![Boîte de dialogue Ajouter un nouveau projet](./media/vb-library-with-visual-studio/libproject.png)

   <span data-ttu-id="b347d-126">Ensuite, la fenêtre de code s’ouvre dans l’environnement de développement Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b347d-126">The code window then opens in the Visual Studio development environment.</span></span> 
 
   ![Fenêtre d’application Visual Studio montrant le code du modèle de bibliothèque de classes par défaut](./media/vb-library-with-visual-studio/stringlibrary.png)

1. <span data-ttu-id="b347d-128">Vérifiez que notre bibliothèque cible la version appropriée de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="b347d-128">Check to make sure that the library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="b347d-129">Dans la fenêtre **Explorateur de solutions**, cliquez avec le bouton droit sur le projet de bibliothèque, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b347d-129">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="b347d-130">La zone de texte **framework cible** indique que nous ciblons .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="b347d-130">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Propriétés de projet pour la bibliothèque de classes](./media/library-with-visual-studio/properties.png)

1. <span data-ttu-id="b347d-132">Dans la boîte de dialogue **Propriétés**, effacez le texte de la zone de texte **Espace de noms racine**.</span><span class="sxs-lookup"><span data-stu-id="b347d-132">Also in the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="b347d-133">Pour chaque projet, Visual Basic crée automatiquement un espace de noms qui correspond au nom du projet, et tous les espaces de noms définis dans les fichiers de code source sont des parents de cet espace de noms.</span><span class="sxs-lookup"><span data-stu-id="b347d-133">For each project, Visual Basic automatically creates a namespace that corresponds to the project name, and any namespaces defined in source code files are parents of that namespace.</span></span> <span data-ttu-id="b347d-134">Nous souhaitons définir un espace de noms de niveau supérieur à l’aide du mot clé [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b347d-134">We want to define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword.</span></span>
  
1. <span data-ttu-id="b347d-135">Remplacez le code de la fenêtre de code par le code suivant et enregistrez le fichier :</span><span class="sxs-lookup"><span data-stu-id="b347d-135">Replace the code in the code window with the following code and save the file:</span></span>

  [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="b347d-136">La bibliothèque de classes, `UtilityLibraries.StringLibrary`, contient une méthode nommée `StartsWithUpper`, qui retourne une valeur <xref:System.Boolean> qui indique si l’instance actuelle de la chaîne commence par une majuscule.</span><span class="sxs-lookup"><span data-stu-id="b347d-136">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="b347d-137">La norme Unicode distingue les caractères minuscules des caractères majuscules.</span><span class="sxs-lookup"><span data-stu-id="b347d-137">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="b347d-138">La méthode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> retourne `true` si un caractère est en majuscule.</span><span class="sxs-lookup"><span data-stu-id="b347d-138">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="b347d-139">Dans la barre de menus, sélectionnez **Générer** > **Générer la solution**.</span><span class="sxs-lookup"><span data-stu-id="b347d-139">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="b347d-140">Le projet devrait être compilé sans erreur.</span><span class="sxs-lookup"><span data-stu-id="b347d-140">The project should compile without error.</span></span>

   ![Volet de sortie indiquant que la génération a réussi](./media/library-with-visual-studio/buildsucceeds.png)



## <a name="next-step"></a><span data-ttu-id="b347d-142">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="b347d-142">Next step</span></span>

<span data-ttu-id="b347d-143">Vous avez créé la bibliothèque correctement.</span><span class="sxs-lookup"><span data-stu-id="b347d-143">You've successfully built the library.</span></span> <span data-ttu-id="b347d-144">Comme vous n’avez appelé aucune de ses méthodes, vous ne savez pas si elle fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="b347d-144">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="b347d-145">L’étape suivante du développement de votre bibliothèque consiste à la tester en utilisant un [Projet de test unitaire](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b347d-145">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>

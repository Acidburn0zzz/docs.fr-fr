---
title: '&lt;message&gt; cette erreur peut résulter également une référence de fichier avec une référence de projet à l’assembly &#39; &lt;assemblyname&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 37a152da06a36756b86576bad9c6c5d6a392dc8d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="24333-102">&lt;message&gt; cette erreur peut résulter également une référence de fichier avec une référence de projet à l’assembly &#39; &lt;assemblyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="24333-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="24333-103">\<message > Cette erreur peut résulter également une référence de fichier avec une référence de projet à l’assembly '\<assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="24333-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="24333-104">Dans ce cas, essayez de remplacer la référence de fichier pour '\<nom_fichier_assembly >' dans le projet '\<nom_projet1 >' avec une référence de projet à '\<nom_projet2 >'.</span><span class="sxs-lookup"><span data-stu-id="24333-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="24333-105">Code de votre projet accède à un membre d’un autre projet, mais la configuration de votre solution n’autorise pas le compilateur Visual Basic résoudre la référence.</span><span class="sxs-lookup"><span data-stu-id="24333-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="24333-106">Pour accéder à un type défini dans un autre assembly, le compilateur Visual Basic doit avoir une référence à cet assembly.</span><span class="sxs-lookup"><span data-stu-id="24333-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="24333-107">Il doit s’agir d’une référence unique et non équivoque qui ne provoque pas de références circulaires parmi des projets.</span><span class="sxs-lookup"><span data-stu-id="24333-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="24333-108">**ID d’erreur :** BC30971</span><span class="sxs-lookup"><span data-stu-id="24333-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="24333-109">Pour corriger cette erreur</span><span class="sxs-lookup"><span data-stu-id="24333-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="24333-110">Identifiez le projet qui produit le meilleur assembly pour votre projet à référencer.</span><span class="sxs-lookup"><span data-stu-id="24333-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="24333-111">Pour prendre cette décision, vous pouvez utiliser des critères, tels que la facilité d’accès au fichier et la fréquence des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="24333-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="24333-112">Dans les propriétés de votre projet, ajoutez une référence au projet contenant l’assembly qui définit le type que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="24333-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24333-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24333-113">See Also</span></span>  
 [<span data-ttu-id="24333-114">Gestion des références dans un projet</span><span class="sxs-lookup"><span data-stu-id="24333-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="24333-115">Références aux éléments déclarés</span><span class="sxs-lookup"><span data-stu-id="24333-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="24333-116">Gestion des propriétés des projets et des solutions</span><span class="sxs-lookup"><span data-stu-id="24333-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="24333-117">Dépannage de références rompues</span><span class="sxs-lookup"><span data-stu-id="24333-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)

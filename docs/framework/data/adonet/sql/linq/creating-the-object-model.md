---
title: Création du modèle objet
ms.date: 03/30/2017
ms.assetid: 27afce86-9b1d-45fb-8e0b-636bf671a236
ms.openlocfilehash: 7724d6e75b350e5c57f090d42ef1f49c4d3593b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359931"
---
# <a name="creating-the-object-model"></a><span data-ttu-id="d3ff2-102">Création du modèle objet</span><span class="sxs-lookup"><span data-stu-id="d3ff2-102">Creating the Object Model</span></span>
<span data-ttu-id="d3ff2-103">Vous pouvez créer votre modèle objet à partir d'une base de données existante et l'utiliser dans son état par défaut.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-103">You can create your object model from an existing database and use the model in its default state.</span></span> <span data-ttu-id="d3ff2-104">Vous pouvez également personnaliser de nombreux aspects du modèle ainsi que son comportement.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-104">You can also customize many aspects of the model and its behavior.</span></span>  
  
 <span data-ttu-id="d3ff2-105">Si vous utilisez Visual Studio, vous pouvez utiliser la [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] pour créer votre modèle objet.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3ff2-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d3ff2-106">In This Section</span></span>  
 [<span data-ttu-id="d3ff2-107">Guide pratique pour générer le modèle objet en Visual Basic ou C#</span><span class="sxs-lookup"><span data-stu-id="d3ff2-107">How to: Generate the Object Model in Visual Basic or C#</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)  
 <span data-ttu-id="d3ff2-108">Explique comment utiliser l'outil en ligne de commande SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-108">Describes how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="d3ff2-109">Fournit également un lien vers le [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] pour les utilisateurs de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d3ff2-109">Also provides a link to the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for Visual Studio users</span></span>  
  
 [<span data-ttu-id="d3ff2-110">Guide pratique pour générer le modèle objet sous forme de fichier externe</span><span class="sxs-lookup"><span data-stu-id="d3ff2-110">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)  
 <span data-ttu-id="d3ff2-111">Décrit comment générer un fichier de mappage externe au lieu d'utiliser le mappage basé sur les attributs.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-111">Describes how to generate an external mapping file instead of using attribute-based mapping.</span></span>  
  
 [<span data-ttu-id="d3ff2-112">Guide pratique pour générer du code personnalisé en modifiant un fichier DBML</span><span class="sxs-lookup"><span data-stu-id="d3ff2-112">How to: Generate Customized Code by Modifying a DBML File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-customized-code-by-modifying-a-dbml-file.md)  
 <span data-ttu-id="d3ff2-113">Décrit comment générer du code Visual Basic ou c# à partir d’un fichier de métadonnées DBML.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-113">Describes how to generate Visual Basic or C# code from a DBML metadata file.</span></span>  
  
 [<span data-ttu-id="d3ff2-114">Guide pratique pour valider des fichiers de mappage externes et DBML</span><span class="sxs-lookup"><span data-stu-id="d3ff2-114">How to: Validate DBML and External Mapping Files</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)  
 <span data-ttu-id="d3ff2-115">Décrit comment valider des fichiers de mappage que vous avez modifiés (avancé).</span><span class="sxs-lookup"><span data-stu-id="d3ff2-115">Describes how to validate mapping files that you have modified (advanced).</span></span>  
  
 [<span data-ttu-id="d3ff2-116">Guide pratique pour rendre les entités sérialisables</span><span class="sxs-lookup"><span data-stu-id="d3ff2-116">How to: Make Entities Serializable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-make-entities-serializable.md)  
 <span data-ttu-id="d3ff2-117">Décrit comment ajouter des attributs appropriés pour rendre des entités sérialisables.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-117">Describes how to add appropriate attributes to make entities serializable.</span></span>  
  
 [<span data-ttu-id="d3ff2-118">Guide pratique pour personnaliser des classes d’entité à l’aide de l’éditeur de code</span><span class="sxs-lookup"><span data-stu-id="d3ff2-118">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 <span data-ttu-id="d3ff2-119">Décrit comment utiliser l'éditeur de code pour écrire votre propre code de mappage ou personnaliser du code qui a été généré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-119">Describes how to use the code editor to write your own mapping code, or customize code that has been autogenerated.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d3ff2-120">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="d3ff2-120">Related Sections</span></span>  
 [<span data-ttu-id="d3ff2-121">Modèle objet LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d3ff2-121">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 <span data-ttu-id="d3ff2-122">Fournit des détails sur la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modèle objet.</span><span class="sxs-lookup"><span data-stu-id="d3ff2-122">Provides details about the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="d3ff2-123">Procédure standard d’utilisation de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d3ff2-123">Typical Steps for Using LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)  
 <span data-ttu-id="d3ff2-124">Décrit la procédure standard à suivre pour implémenter une application [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3ff2-124">Explains the typical steps that you follow to implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application.</span></span>

---
title: '&lt;inclure&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: da7a6c15c558fc56dbc6a874d4a28c4434f67668
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46473185"
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="d68d7-102">&lt;inclure&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d68d7-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="d68d7-103">Fait référence à un autre fichier qui décrit les types et membres dans votre code source.</span><span class="sxs-lookup"><span data-stu-id="d68d7-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d68d7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d68d7-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d68d7-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d68d7-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="d68d7-106">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d68d7-106">Required.</span></span> <span data-ttu-id="d68d7-107">Nom du fichier contenant la documentation.</span><span class="sxs-lookup"><span data-stu-id="d68d7-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="d68d7-108">Le nom de fichier peut être qualifié avec un chemin.</span><span class="sxs-lookup"><span data-stu-id="d68d7-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="d68d7-109">Placez `filename` dans des guillemets doubles ( » «).</span><span class="sxs-lookup"><span data-stu-id="d68d7-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="d68d7-110">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d68d7-110">Required.</span></span> <span data-ttu-id="d68d7-111">Chemin des balises contenues dans `filename` qui mène à la balise `name`.</span><span class="sxs-lookup"><span data-stu-id="d68d7-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="d68d7-112">Placez le chemin d’accès entre guillemets doubles ( » «).</span><span class="sxs-lookup"><span data-stu-id="d68d7-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="d68d7-113">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d68d7-113">Required.</span></span> <span data-ttu-id="d68d7-114">Le spécificateur de nom dans la balise qui précède les commentaires.</span><span class="sxs-lookup"><span data-stu-id="d68d7-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="d68d7-115">`Name` aura un `id`.</span><span class="sxs-lookup"><span data-stu-id="d68d7-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="d68d7-116">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="d68d7-116">Required.</span></span> <span data-ttu-id="d68d7-117">ID de la balise qui précède les commentaires.</span><span class="sxs-lookup"><span data-stu-id="d68d7-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="d68d7-118">Mettez l’ID entre guillemets simples (' ').</span><span class="sxs-lookup"><span data-stu-id="d68d7-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d68d7-119">Notes</span><span class="sxs-lookup"><span data-stu-id="d68d7-119">Remarks</span></span>  
 <span data-ttu-id="d68d7-120">Utilisez le `<include>` balise pour faire référence à des commentaires dans un autre fichier qui décrivent les types et membres dans votre code source.</span><span class="sxs-lookup"><span data-stu-id="d68d7-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="d68d7-121">Il s’agit d’une solution alternative au placement direct des commentaires de la documentation dans votre fichier de code source.</span><span class="sxs-lookup"><span data-stu-id="d68d7-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="d68d7-122">Le `<include>` balise utilise la recommandation de la Version 1.0 W3C XML Path Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="d68d7-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="d68d7-123">Plus d’informations pour savoir comment personnaliser votre `<include>` utilisation est disponible à l’adresse http://www.w3.org/TR/xpath.</span><span class="sxs-lookup"><span data-stu-id="d68d7-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d68d7-124">Exemple</span><span class="sxs-lookup"><span data-stu-id="d68d7-124">Example</span></span>  
 <span data-ttu-id="d68d7-125">Cet exemple utilise le `<include>` balise pour importer des commentaires de documentation de membre à partir d’un fichier appelé `commentFile.xml`.</span><span class="sxs-lookup"><span data-stu-id="d68d7-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="d68d7-126">Le format de la `commentFile.xml` se présente comme suit.</span><span class="sxs-lookup"><span data-stu-id="d68d7-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d68d7-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d68d7-127">See Also</span></span>  
 [<span data-ttu-id="d68d7-128">Étiquettes XML pour les commentaires</span><span class="sxs-lookup"><span data-stu-id="d68d7-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

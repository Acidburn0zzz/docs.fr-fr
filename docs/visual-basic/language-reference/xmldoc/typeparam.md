---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 76e0e8d4757f29bb5df82ea1482beff3dd43c0e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598012"
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="fc0b7-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc0b7-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="fc0b7-103">Définit un nom de paramètre de type et une description.</span><span class="sxs-lookup"><span data-stu-id="fc0b7-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc0b7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fc0b7-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc0b7-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="fc0b7-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="fc0b7-106">Nom du paramètre de type.</span><span class="sxs-lookup"><span data-stu-id="fc0b7-106">The name of the type parameter.</span></span> <span data-ttu-id="fc0b7-107">Mettez le nom entre guillemets doubles (" ").</span><span class="sxs-lookup"><span data-stu-id="fc0b7-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="fc0b7-108">Description du paramètre de type.</span><span class="sxs-lookup"><span data-stu-id="fc0b7-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc0b7-109">Notes</span><span class="sxs-lookup"><span data-stu-id="fc0b7-109">Remarks</span></span>  
 <span data-ttu-id="fc0b7-110">Utilisez le `<typeparam>` balise dans le commentaire pour un type générique ou une déclaration de membre générique décrire l’un des paramètres de type.</span><span class="sxs-lookup"><span data-stu-id="fc0b7-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="fc0b7-111">Compilez avec [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) pour placer les commentaires de documentation dans un fichier en vue de les traiter.</span><span class="sxs-lookup"><span data-stu-id="fc0b7-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc0b7-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="fc0b7-112">Example</span></span>  
 <span data-ttu-id="fc0b7-113">Cet exemple utilise le `<typeparam>` balises pour décrire le `id` paramètre.</span><span class="sxs-lookup"><span data-stu-id="fc0b7-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fc0b7-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc0b7-114">See Also</span></span>  
 [<span data-ttu-id="fc0b7-115">Étiquettes XML pour les commentaires</span><span class="sxs-lookup"><span data-stu-id="fc0b7-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)

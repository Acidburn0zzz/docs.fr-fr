---
title: Exception de commentaire XML doit avoir un &#39;cref&#39; attribut
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: ee91513ef94e2abbe01d3ac09796b7fdf8e129ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597381"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a><span data-ttu-id="33247-102">Exception de commentaire XML doit avoir un &#39;cref&#39; attribut</span><span class="sxs-lookup"><span data-stu-id="33247-102">XML comment exception must have a &#39;cref&#39; attribute</span></span>
<span data-ttu-id="33247-103">Le \<exception > balise permet de documenter les exceptions qui peuvent être levées par une méthode.</span><span class="sxs-lookup"><span data-stu-id="33247-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="33247-104">Requis `cref` attribut désigne le nom d’un membre qui est vérifié par le Générateur de documentation.</span><span class="sxs-lookup"><span data-stu-id="33247-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="33247-105">Si le membre existe, il est converti en nom d’élément canonique dans le fichier de documentation.</span><span class="sxs-lookup"><span data-stu-id="33247-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="33247-106">**ID d’erreur :** BC42319</span><span class="sxs-lookup"><span data-stu-id="33247-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33247-107">Pour corriger cette erreur</span><span class="sxs-lookup"><span data-stu-id="33247-107">To correct this error</span></span>  
  
-   <span data-ttu-id="33247-108">Ajouter le `cref` attribut à l’exception, comme suit :</span><span class="sxs-lookup"><span data-stu-id="33247-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="33247-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33247-109">See Also</span></span>  
 [<span data-ttu-id="33247-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="33247-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [<span data-ttu-id="33247-111">Guide pratique : créer une documentation XML</span><span class="sxs-lookup"><span data-stu-id="33247-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="33247-112">Étiquettes XML pour les commentaires</span><span class="sxs-lookup"><span data-stu-id="33247-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)

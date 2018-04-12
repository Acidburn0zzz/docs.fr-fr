---
title: '&#39; &lt;nom1&gt;&#39; est ambigu, importé des espaces de noms ou les types de &#39;&lt; name2&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30561
- bc30561
helpviewer_keywords:
- BC30561
ms.assetid: 761091f7-1018-4299-b481-3966a4a2c126
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6ebc9b75d171a28b4388d48625b772ac6f20dc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="39ltname1gt39-is-ambiguous-imported-from-the-namespaces-or-types-39ltname2gt39"></a><span data-ttu-id="f823a-102">&#39; &lt;nom1&gt;&#39; est ambigu, importé des espaces de noms ou les types de &#39;&lt; name2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="f823a-102">&#39;&lt;name1&gt;&#39; is ambiguous, imported from the namespaces or types &#39;&lt;name2&gt;&#39;</span></span>
<span data-ttu-id="f823a-103">Vous avez fourni un nom qui est ambigu et donc en conflit avec un autre nom.</span><span class="sxs-lookup"><span data-stu-id="f823a-103">You have provided a name that is ambiguous and therefore conflicts with another name.</span></span> <span data-ttu-id="f823a-104">Le compilateur [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ne possède aucune règle de résolution de conflit ; vous devez lever vous-même toute ambiguïté sur les noms.</span><span class="sxs-lookup"><span data-stu-id="f823a-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler does not have any conflict resolution rules; you must disambiguate names yourself.</span></span>  
  
 <span data-ttu-id="f823a-105">**ID d’erreur :** BC30561</span><span class="sxs-lookup"><span data-stu-id="f823a-105">**Error ID:** BC30561</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f823a-106">Pour corriger cette erreur</span><span class="sxs-lookup"><span data-stu-id="f823a-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f823a-107">Lever l’ambiguïté de nom en supprimant les importations d’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="f823a-107">Disambiguate the name by removing namespace imports.</span></span>  
  
2.  <span data-ttu-id="f823a-108">Utilisez un nom qualifié complet.</span><span class="sxs-lookup"><span data-stu-id="f823a-108">Fully qualify the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f823a-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f823a-109">See Also</span></span>  
 [<span data-ttu-id="f823a-110">Imports (instruction) (espace de noms et type .NET)</span><span class="sxs-lookup"><span data-stu-id="f823a-110">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="f823a-111">Espaces de noms dans Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f823a-111">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="f823a-112">Namespace (instruction)</span><span class="sxs-lookup"><span data-stu-id="f823a-112">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)

---
title: Tableaux
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2945ead7c22b759ce88f6585e2254e9bc540a7ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570394"
---
# <a name="arrays"></a><span data-ttu-id="2974d-102">Tableaux</span><span class="sxs-lookup"><span data-stu-id="2974d-102">Arrays</span></span>
<span data-ttu-id="2974d-103">**✓ DO** préférez l’utilisation de collections sur des tableaux dans les API publiques.</span><span class="sxs-lookup"><span data-stu-id="2974d-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="2974d-104">Le [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section fournit des détails sur le choix entre les collections et tableaux.</span><span class="sxs-lookup"><span data-stu-id="2974d-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="2974d-105">**X DO NOT** utiliser les champs de tableau en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="2974d-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="2974d-106">Le champ lui-même est en lecture seule et ne peut pas être modifié, mais les éléments du tableau peuvent être modifiés.</span><span class="sxs-lookup"><span data-stu-id="2974d-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="2974d-107">**✓ CONSIDER** à l’aide de tableaux en escalier à la place de tableaux multidimensionnels.</span><span class="sxs-lookup"><span data-stu-id="2974d-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="2974d-108">Un tableau en escalier est un tableau comportant des éléments qui sont également des tableaux.</span><span class="sxs-lookup"><span data-stu-id="2974d-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="2974d-109">Les tableaux qui composent les éléments peuvent être de différentes tailles, conduisant à un gaspillage d’espace pour certains jeux de données (par exemple, une matrice éparse) par rapport aux tableaux multidimensionnels.</span><span class="sxs-lookup"><span data-stu-id="2974d-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="2974d-110">En outre, le CLR optimise les opérations d’index sur des tableaux en escalier, afin qu’ils peuvent exposer les meilleures performances dans certains scénarios d’exécution.</span><span class="sxs-lookup"><span data-stu-id="2974d-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="2974d-111">*Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*</span><span class="sxs-lookup"><span data-stu-id="2974d-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2974d-112">*Réimprimées avec l’autorisation de Pearson éducation, Inc. à partir de [règles de conception d’infrastructure : Conventions, idiomes et des modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2974d-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2974d-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2974d-113">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="2974d-114">Règles de conception de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2974d-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="2974d-115">Indications relatives à l’utilisation</span><span class="sxs-lookup"><span data-stu-id="2974d-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)

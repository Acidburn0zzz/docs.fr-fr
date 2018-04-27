---
title: Noms d'assemblys et de DLL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ff14d3d804329e591486a7eb2a2ee7ed430f622c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="0c7a3-102">Noms d'assemblys et de DLL</span><span class="sxs-lookup"><span data-stu-id="0c7a3-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="0c7a3-103">Un assembly est l’unité de déploiement et d’identité pour les programmes de code managé.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="0c7a3-104">Bien que les assemblys peuvent s’étendre sur un ou plusieurs fichiers, en général, un assembly mappe un à un avec une DLL.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="0c7a3-105">Par conséquent, cette section décrit les conventions d’affectation de noms d’uniquement DLL peuvent être mappées à des conventions d’affectation des noms d’assembly.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="0c7a3-106">**✓ FAIRE** choisissez des noms pour vos DLL d’assembly qui suggèrent des grands segments de fonctionnalités, telles que System.Data.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="0c7a3-107">Noms d’assembly et la DLL n’êtes pas obligé de correspondent aux noms d’espace de noms, mais il est conseillé d’utiliser l’espace de noms lorsque vous nommez des assemblys.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="0c7a3-108">Une règle empirique consiste pour nommer la DLL en fonction du préfixe commun des espaces de noms contenus dans l’assembly.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="0c7a3-109">Par exemple, un assembly avec deux espaces de noms, `MyCompany.MyTechnology.FirstFeature` et `MyCompany.MyTechnology.SecondFeature`, peut être appelée `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="0c7a3-110">**✓ Envisagez** nommer les DLL selon le modèle suivant :</span><span class="sxs-lookup"><span data-stu-id="0c7a3-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="0c7a3-111">où `<Component>` contient une ou plusieurs clauses séparées par un point.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="0c7a3-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0c7a3-112">For example:</span></span>  
  
 <span data-ttu-id="0c7a3-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="0c7a3-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="0c7a3-114">*Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*</span><span class="sxs-lookup"><span data-stu-id="0c7a3-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0c7a3-115">*Réimprimées avec l’autorisation de Pearson éducation, Inc. à partir de [règles de conception d’infrastructure : Conventions, idiomes et des modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="0c7a3-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7a3-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c7a3-116">See Also</span></span>  
 [<span data-ttu-id="0c7a3-117">Règles de conception de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0c7a3-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="0c7a3-118">Directives de nommage</span><span class="sxs-lookup"><span data-stu-id="0c7a3-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)

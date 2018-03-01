---
title: "Conversion de types .NET Framework en chaînes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6ca134e13593fdacd759b0000e0e159f76ea067f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/23/2017
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="334b4-102">Conversion de types .NET Framework en chaînes</span><span class="sxs-lookup"><span data-stu-id="334b4-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="334b4-103">Si vous voulez convertir un type .NET Framework en chaîne, utilisez la méthode **ToString**.</span><span class="sxs-lookup"><span data-stu-id="334b4-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="334b4-104">La méthode **ToString** retourne une représentation sous forme de chaîne du type passé.</span><span class="sxs-lookup"><span data-stu-id="334b4-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="334b4-105">Le tableau suivant répertorie les types .NET Framework qui retournent une chaîne dans un format qui mappe aux spécifications de schéma XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="334b4-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="334b4-106">Type .NET Framework</span><span class="sxs-lookup"><span data-stu-id="334b4-106">.NET Framework type</span></span>|<span data-ttu-id="334b4-107">Type de chaîne de retour</span><span class="sxs-lookup"><span data-stu-id="334b4-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="334b4-108">Booléen</span><span class="sxs-lookup"><span data-stu-id="334b4-108">Boolean</span></span>|<span data-ttu-id="334b4-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="334b4-109">"true", "false"</span></span>|  
|<span data-ttu-id="334b4-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="334b4-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="334b4-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="334b4-111">"INF"</span></span>|  
|<span data-ttu-id="334b4-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="334b4-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="334b4-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="334b4-113">"-INF"</span></span>|  
|<span data-ttu-id="334b4-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="334b4-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="334b4-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="334b4-115">"INF"</span></span>|  
|<span data-ttu-id="334b4-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="334b4-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="334b4-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="334b4-117">"-INF"</span></span>|  
|<span data-ttu-id="334b4-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="334b4-118">DateTime</span></span>|<span data-ttu-id="334b4-119">Le format est yyyy-MM-ddTHH:mm:sszzzzzz et ses sous-ensembles.</span><span class="sxs-lookup"><span data-stu-id="334b4-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="334b4-120">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="334b4-120">Timespan</span></span>|<span data-ttu-id="334b4-121">Le format est PnYnMnTnHnMnS. Par exemple, `P2Y10M15DT10H30M20S` est la durée de 2 années, 10 mois, 15 jours, 10 heures, 30 minutes et 20 secondes.</span><span class="sxs-lookup"><span data-stu-id="334b4-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="334b4-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="334b4-122">See Also</span></span>  
 [<span data-ttu-id="334b4-123">Conversion des types de données XML</span><span class="sxs-lookup"><span data-stu-id="334b4-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="334b4-124">Conversion de chaînes en types de données .NET Framework</span><span class="sxs-lookup"><span data-stu-id="334b4-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)

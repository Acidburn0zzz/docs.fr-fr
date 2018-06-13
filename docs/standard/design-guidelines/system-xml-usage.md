---
title: System.Xml, utilisation
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce9869d538b69af9beaa74be3300175f279b8f53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572812"
---
# <a name="systemxml-usage"></a><span data-ttu-id="43b5a-102">System.Xml, utilisation</span><span class="sxs-lookup"><span data-stu-id="43b5a-102">System.Xml Usage</span></span>
<span data-ttu-id="43b5a-103">Cette section aborde l’utilisation de plusieurs types résidant dans <xref:System.Xml?displayProperty=nameWithType> espaces de noms peut être utilisé pour représenter les données XML.</span><span class="sxs-lookup"><span data-stu-id="43b5a-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="43b5a-104">**X ne sont pas** utiliser <xref:System.Xml.XmlNode> ou <xref:System.Xml.XmlDocument> pour représenter les données XML.</span><span class="sxs-lookup"><span data-stu-id="43b5a-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="43b5a-105">Favoriser l’utilisation d’instances de <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, ou un sous-type de <xref:System.Xml.Linq.XNode> à la place.</span><span class="sxs-lookup"><span data-stu-id="43b5a-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="43b5a-106">`XmlNode` et `XmlDocument` ne sont pas conçus pour exposer des API publiques.</span><span class="sxs-lookup"><span data-stu-id="43b5a-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="43b5a-107">**✓ FAIRE** utiliser `XmlReader`, `IXPathNavigable`, ou un sous-type de `XNode` en tant qu’entrée ou sortie de membres qui acceptent ou retournent XML.</span><span class="sxs-lookup"><span data-stu-id="43b5a-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="43b5a-108">Utilisez ces abstractions au lieu de `XmlDocument`, `XmlNode`, ou <xref:System.Xml.XPath.XPathDocument>, car cela dissocie les méthodes à partir des implémentations spécifiques d’un document XML en mémoire et permet de travailler avec les sources de données XML virtuels qui exposent `XNode` , `XmlReader`, ou <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="43b5a-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="43b5a-109">**X ne sont pas** sous-classe `XmlDocument` si vous souhaitez créer un type qui représente une vue XML d’une source de données ou du modèle objet sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="43b5a-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="43b5a-110">*Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*</span><span class="sxs-lookup"><span data-stu-id="43b5a-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="43b5a-111">*Réimprimées avec l’autorisation de Pearson éducation, Inc. à partir de [règles de conception d’infrastructure : Conventions, idiomes et des modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="43b5a-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b5a-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43b5a-112">See Also</span></span>  
 [<span data-ttu-id="43b5a-113">Règles de conception de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="43b5a-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="43b5a-114">Indications relatives à l’utilisation</span><span class="sxs-lookup"><span data-stu-id="43b5a-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)

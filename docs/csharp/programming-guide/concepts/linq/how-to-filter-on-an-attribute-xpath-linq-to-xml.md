---
title: Guide pratique pour filtrer sur un attribut (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 208d6256-1bd7-4237-b2c9-909f26dfd0e2
ms.openlocfilehash: 9d99387be6683dcc46d36b5fdefbcd09f998eab1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516235"
---
# <a name="how-to-filter-on-an-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="ad0f6-102">Guide pratique pour filtrer sur un attribut (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ad0f6-102">How to: Filter on an Attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="ad0f6-103">Cette rubrique montre comment obtenir les éléments descendants avec un nom spécifié et avec un attribut avec une valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ad0f6-103">This topic shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="ad0f6-104">L’expression XPath est la suivante :</span><span class="sxs-lookup"><span data-stu-id="ad0f6-104">The XPath expression is:</span></span>  
  
 `.//Address[@Type='Shipping']`  
  
## <a name="example"></a><span data-ttu-id="ad0f6-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="ad0f6-105">Example</span></span>  
 <span data-ttu-id="ad0f6-106">Cet exemple recherche tous les éléments descendants avec le nom `Address` et avec un attribut `Type` avec une valeur de « Shipping ».</span><span class="sxs-lookup"><span data-stu-id="ad0f6-106">This example finds all descendants elements with the name of `Address`, and with a `Type` attribute with a value of "Shipping".</span></span>  
  
 <span data-ttu-id="ad0f6-107">Cet exemple utilise le document XML suivant : [Exemple de fichier XML : Plusieurs commandes fournisseur (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ad0f6-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements(".//Address[@Type='Shipping']");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="ad0f6-108">Cet exemple génère la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="ad0f6-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Address Type="Shipping">  
  <Name>Ellen Adams</Name>  
  <Street>123 Maple Street</Street>  
  <City>Mill Valley</City>  
  <State>CA</State>  
  <Zip>10999</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Cristian Osorio</Name>  
  <Street>456 Main Street</Street>  
  <City>Buffalo</City>  
  <State>NY</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Jessica Arnold</Name>  
  <Street>4055 Madison Ave</Street>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad0f6-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad0f6-109">See Also</span></span>

- [<span data-ttu-id="ad0f6-110">LINQ to XML pour les utilisateurs XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="ad0f6-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

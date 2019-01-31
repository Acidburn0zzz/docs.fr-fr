---
title: 'Procédure : Rechercher un élément enfant (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 4fa6182d-6196-4ed1-9c9e-82949ff89c71
ms.openlocfilehash: 6ce31c803e1f0877a6029bda9de73e4bf8e79279
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737479"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-c"></a>Procédure : Rechercher un élément enfant (XPath-LINQ to XML) (C#)
Cette rubrique compare l’axe des éléments enfants XPath à la méthode <xref:System.Xml.Linq.XContainer.Element%2A> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 L'expression XPath est `DeliveryNotes`.  
  
## <a name="example"></a>Exemple  
 Cet exemple recherche l'élément enfant `DeliveryNotes`.  
  
 Cet exemple utilise le document XML suivant : [Exemple de fichier XML : Plusieurs commandes fournisseur (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder");  
  
// LINQ to XML query  
XElement el1 = po.Element("DeliveryNotes");  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("DeliveryNotes");  
// same as "child::DeliveryNotes"  
// same as "./DeliveryNotes"  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 Cet exemple génère la sortie suivante :  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a>Voir aussi

- [LINQ to XML pour les utilisateurs XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

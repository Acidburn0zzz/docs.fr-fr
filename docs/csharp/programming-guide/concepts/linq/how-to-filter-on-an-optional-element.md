---
title: Guide pratique pour filtrer sur un élément facultatif (C#)
ms.date: 07/20/2015
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: c781db261dbf673af7a11150971956b4c07da774
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076595"
---
# <a name="how-to-filter-on-an-optional-element-c"></a>Guide pratique pour filtrer sur un élément facultatif (C#)
Parfois, vous souhaitez appliquer un filtrage sur un élément sans être certain qu'il existe dans votre document XML. La recherche doit être exécutée de telle sorte que, si l'élément particulier ne possède pas l'élément enfant, aucune exception de référence Null ne soit déclenchée suite au filtrage. Dans l'exemple suivant, l'élément `Child5` ne possède pas d'élément enfant `Type`, mais la requête s'exécute tout de même correctement.  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise la méthode d'extension <xref:System.Xml.Linq.Extensions.Elements%2A>.  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
var cList =  
    from typeElement in root.Elements().Elements("Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element("Text");  
foreach(string str in cList)  
    Console.WriteLine(str);  
```  
  
 Ce code génère la sortie suivante :  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a>Exemple  
 L'exemple suivant illustre la même requête pour du code XML qui est dans un espace de noms. Pour plus d’informations, consultez [Utilisation des espaces de noms XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```csharp  
XElement root = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
XNamespace ad = "http://www.adatum.com";  
var cList =  
    from typeElement in root.Elements().Elements(ad + "Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element(ad + "Text");  
foreach (string str in cList)  
    Console.WriteLine(str);  
```  
  
 Ce code génère la sortie suivante :  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>  
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>  
- [Requêtes de base (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
- [Présentation des opérateurs de requête standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [Opérations de projection (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)

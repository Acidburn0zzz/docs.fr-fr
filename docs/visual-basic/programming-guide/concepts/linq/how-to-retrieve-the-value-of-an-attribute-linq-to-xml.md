---
title: 'Comment : récupérer la valeur d’un attribut (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 96d5e5a0c7ee294b140385c93b13ee56f3f92491
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a>Comment : récupérer la valeur d’un attribut (LINQ to XML) (Visual Basic)
Cette rubrique montre comment obtenir la valeur d'attributs. Vous pouvez procéder de deux manières : tout d'abord, vous pouvez convertir un objet <xref:System.Xml.Linq.XAttribute> vers le type souhaité ; l'opérateur de conversion. explicite convertit alors le contenu de l'élément ou attribut vers le type spécifié. En guise d'alternative, vous pouvez utiliser la propriété <xref:System.Xml.Linq.XAttribute.Value%2A>. Toutefois, la conversion est généralement la meilleure approche. Si vous convertissez l'attribut vers un type Nullable, le code est plus simple à écrire lors de la récupération de la valeur d'un attribut qui peut exister ou ne pas exister. Pour obtenir des exemples de cette technique, consultez [Comment : récupérer la valeur d’un élément (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Exemple  
 En Visual Basic, vous pouvez utiliser la propriété d'attribut intégrée pour récupérer la valeur d'un attribut.  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 Cet exemple génère la sortie suivante :  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Exemple  
 En Visual Basic, vous pouvez utiliser la propriété d'attribut intégrée pour définir la valeur d'un attribut. En outre, si vous utilisez la propriété d'attribut intégrée pour définir la valeur d'un attribut qui n'existe pas, l'attribut sera créé.  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 Cet exemple génère la sortie suivante :  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment récupérer la valeur d'un attribut lorsque celui-ci se trouve dans un espace de noms. Pour plus d’informations, consultez [utilisation des espaces de noms XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 Cet exemple génère la sortie suivante :  
  
```  
abcde  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Axes LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)

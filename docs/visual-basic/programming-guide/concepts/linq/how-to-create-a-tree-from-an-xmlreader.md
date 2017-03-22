---
title: "Comment : créer une arborescence à partir d’un XmlReader (Visual Basic) | Documents Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a8dff4e518d8850b4050389e5677ac81ecd1e074
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Comment : créer une arborescence à partir d’un XmlReader (Visual Basic)
Cette rubrique montre comment créer une arborescence XML directement à partir d’un <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> Pour créer un <xref:System.Xml.Linq.XElement>d’un <xref:System.Xml.XmlReader>, vous devez positionner le <xref:System.Xml.XmlReader>sur un nœud d’élément.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XElement> Le <xref:System.Xml.XmlReader>ignorera les commentaires et instructions de traitement, mais si le <xref:System.Xml.XmlReader>est positionné sur un nœud de texte, une erreur sera renvoyée.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> Pour éviter ces erreurs, placez toujours le <xref:System.Xml.XmlReader>sur un élément avant de créer une arborescence XML à partir de <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader>  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le document XML suivant : [exemple de fichier XML : livres (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 Le code suivant crée un objet `T:System.Xml.XmlReader`, puis il lit les nœuds jusqu'à trouver le premier nœud d'élément. Il charge ensuite le <xref:System.Xml.Linq.XElement>objet.</xref:System.Xml.Linq.XElement>  
  
```vb  
Dim r As XmlReader = XmlReader.Create("books.xml")  
Do While r.NodeType <> XmlNodeType.Element  
    r.Read()  
Loop  
Dim e As XElement = XElement.Load(r)  
Console.WriteLine(e)  
```  
  
 Cet exemple génère la sortie suivante :  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications   
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [L’analyse XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)

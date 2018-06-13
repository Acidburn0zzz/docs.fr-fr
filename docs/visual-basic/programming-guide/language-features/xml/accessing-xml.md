---
title: Accès au code XML dans Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: b000b3f6846f800b2a96ce10cdd408a355f78a81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649592"
---
# <a name="accessing-xml-in-visual-basic"></a>Accès au code XML dans Visual Basic
Visual Basic fournit des propriétés d’axe XML pour accéder à et naviguer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures. Ces propriétés utilisent une syntaxe spéciale pour vous permettre d’accéder aux éléments et attributs en spécifiant les noms XML.  
  
 Le tableau suivant répertorie les fonctionnalités de langage qui vous permettent d’accéder aux éléments XML et des attributs en Visual Basic.  
  
### <a name="xml-axis-properties"></a>Propriétés d'axe XML  
  
|Description de la propriété|Exemple|Description|  
|--------------------------|-------------|-----------------|  
|*axe d’enfant*|`contact.<phone>`|Obtient tous les `phone` les éléments qui sont des éléments enfants de le `contact` élément.|  
|*axe d’attribut*|`phone.@type`|Obtient tous les `type` les attributs de la `phone` élément.|  
|*axe descendant*|`contacts...<name>`|Obtient tous les `name` les éléments de la `contacts` élément, quelle que soit la profondeur dans la hiérarchie.|  
|*indexeur d’extension*|`contacts...<name>(0)`|Obtient le premier `name` élément de la séquence.|  
|*valeur*|`contacts...<name>.Value`|Obtient la représentation sous forme de chaîne du premier objet dans la séquence, ou `Nothing` si la séquence est vide.|  
  
## <a name="in-this-section"></a>Dans cette section  
 [Guide pratique : accéder à des éléments descendants XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Montre comment utiliser une propriété d’axe descendant pour accéder à tous les éléments XML qui ont un nom spécifié et qui sont contenus sous un élément XML spécifié.  
  
 [Guide pratique : accéder à des éléments enfants XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Montre comment utiliser un enfant de propriété d’axe pour accéder à tous les éléments enfants XML portant un nom spécifié dans un élément XML.  
  
 [Guide pratique : accéder à des attributs XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Montre comment utiliser la propriété d’axe d’attribut pour accéder à tous les attributs XML qui ont un nom spécifié dans un élément XML.  
  
 [Guide pratique : déclarer et utiliser des préfixes d’espaces de noms XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Montre comment déclarer un préfixe d’espace de noms XML et l’utiliser pour créer et accéder à des éléments XML.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Propriétés d’axe XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Fournit des liens vers des sections qui décrivent les différentes propriétés d’accès XML.  
  
 [Vue d’ensemble de LINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Fournit une introduction à l’utilisation de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.  
  
 [Création de code XML dans Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Fournit une introduction à l’aide de littéraux XML en Visual Basic.  
  
 [Manipulation de code XML dans Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Fournit des liens vers les sections sur le chargement et la modification de XML en Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Fournit des liens vers des sections qui décrivent comment utiliser [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] dans Visual Basic.

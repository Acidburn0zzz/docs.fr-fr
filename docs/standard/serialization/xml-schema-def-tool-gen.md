---
title: 'Procédure : utiliser l’outil de définition de schéma XML pour générer des classes et des documents de schéma XML'
ms.date: 03/30/2017
helpviewer_keywords:
- generating XML classes using XML Schema Definition tool
- generating XML Schema Document using XML Schema Definition tool
- XML Schema Definition tool, using to generate classes that conform to specific schema
- XML Schema Definition tool, using to generate XML Schema Document
ms.assetid: 51f0edc3-993d-4051-b7f2-77753694d3d1
ms.openlocfilehash: 77bb567d2b7b8fff2b1b8de43b2d5fa36fffb3b3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346130"
---
# <a name="how-to-use-the-xml-schema-definition-tool-to-generate-classes-and-xml-schema-documents"></a>Procédure : utiliser l’outil de définition de schéma XML pour générer des classes et des documents de schéma XML
L'outil XML Schema Definition (Xsd.exe) vous permet de générer un schéma XML qui décrit une classe ou de générer la classe définie par un schéma XML. Les procédures suivantes indiquent comment exécuter ces opérations.  
  
### <a name="to-generate-classes-that-conform-to-a-specific-schema"></a>Pour générer des classes qui se conforment à un schéma spécifique  
  
1. Ouvrez une invite de commandes.  
  
2. Passez par exemple le schéma XML en tant qu'argument à l'outil XML Schema Definition, qui crée un ensemble de classes correspondant précisément au schéma XML :  
  
    ```  
    xsd mySchema.xsd  
    ```  
  
     L'outil ne peut traiter que les schémas qui référencent la spécification XML du W3C (World Wide Web Consortium) du 16 mars 2001. En d’autres termes, l’espace de noms du schéma XML doit être "http://www.w3.org/2001/XMLSchema" comme indiqué dans l’exemple suivant.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <xs:schema attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    ```  
  
3. Modifiez si nécessaire les classes avec les méthodes, les propriétés ou les champs. Pour plus d’informations sur la modification d’une classe avec des attributs, consultez [Contrôle de la sérialisation XML à l’aide d’attributs](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md) et [Attributs qui contrôlent la sérialisation encodée selon le protocole SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md).  
  
 Il est souvent utile d'examiner le schéma du flux de données XML généré lorsque les instances d'une ou de plusieurs classes sont sérialisées. Par exemple, vous pouvez publier votre schéma pour d'autres utilisateurs ou le comparer à un schéma auquel vous tentez de vous conformer.  
  
#### <a name="to-generate-an-xml-schema-document-from-a-set-of-classes"></a>Pour générer un document de schéma XML à partir d'un ensemble de classes  
  
1. Compilez la ou les classes dans une DLL.  
  
2. Ouvrez une invite de commandes.  
  
3. Passez la DLL en tant qu'argument dans Xsd.exe, par exemple :  
  
    ```  
    xsd MyFile.dll  
    ```  
  
     Le ou les schémas sont écrits et commencent par le nom "schema0.xsd."  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Data.DataSet>
- [Outil XML Schema Definition et sérialisation XML](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)
- [Introduction à la sérialisation XML](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Outil XML Schema Definition (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Procédure : sérialiser un objet](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Procédure : désérialiser un objet](../../../docs/standard/serialization/how-to-deserialize-an-object.md)

---
title: Mapper les contraintes clés de schéma XML (XSD) aux contraintes de DataSet
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: ad39fd75a3f8872ed2c24a65481209e3c772a638
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757864"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Mapper les contraintes clés de schéma XML (XSD) aux contraintes de DataSet
Dans un schéma, vous pouvez spécifier une contrainte de clé sur un élément ou d’attribut à l’aide de la **clé** élément. L'élément ou attribut sur lequel une contrainte de clé est spécifiée doit avoir des valeurs uniques dans toute instance du schéma et ne peut pas avoir de valeurs null.  
  
 La contrainte de clé est similaire à la contrainte unique, si ce n'est que la colonne sur laquelle une contrainte de clé est définie ne peut pas comporter de valeurs null.  
  
 Le tableau suivant décrit les **msdata** les attributs que vous pouvez spécifier dans le **clé** élément.  
  
|Nom d'attribut|Description|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Si cet attribut est spécifié, sa valeur est utilisée comme nom de la contrainte. Dans le cas contraire, le **nom** attribut fournit la valeur de la contrainte.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` est présent, le **IsPrimaryKey** contrainte est définie sur **true**, ce qui rend une clé primaire. Le **AllowDBNull** colonne est définie sur **false**, car les clés primaires ne peuvent pas avoir de valeurs null.|  
  
 En convertissant un schéma dans lequel une contrainte de clé est spécifiée, le processus de mappage crée une contrainte unique sur la table avec la **AllowDBNull** propriété column définie sur **false** pour chaque colonne dans le contrainte. Le **IsPrimaryKey** de la contrainte unique est également définie sur **false** , sauf si vous avez spécifié `msdata:PrimaryKey="true"` sur la **clé** élément. Ce mode de fonctionnement est identique à celui d'une contrainte unique dans le schéma faisant apparaître `PrimaryKey="true"`.  
  
 Dans l’exemple qui suit, la **clé** élément spécifie la contrainte de clé sur le **CustomerID** élément.  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 Le **clé** élément spécifie que les valeurs de la **CustomerID** élément enfant de le **clients** élément doivent avoir des valeurs uniques et ne peut pas avoir de valeurs null. En convertissant le schéma en langage XSD (XML Schema Definition), le processus de mappage crée la table suivante :  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Le mappage de schéma XML crée également un **UniqueConstraint** sur la **CustomerID** colonne, comme le montre l’exemple suivant <xref:System.Data.DataSet>. (Par souci de simplicité, seules les propriétés pertinentes sont représentées.)  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 Dans le **DataSet** qui est généré, le **IsPrimaryKey** propriété de la **UniqueConstraint** a la valeur **true** , car le schéma Spécifie `msdata:PrimaryKey="true"` dans les **clé** élément.  
  
 La valeur de la **ConstraintName** propriété de la **UniqueConstraint** dans les **DataSet** est la valeur de la **msdata : ConstraintName** attribut spécifié dans le **clé** élément dans le schéma.  
  
## <a name="see-also"></a>Voir aussi  
 [Mappage des contraintes de schéma XML (XSD) aux contraintes de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Génération de relations de DataSet à partir du schéma XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Fournisseurs managés ADO.NET et centre de développement DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

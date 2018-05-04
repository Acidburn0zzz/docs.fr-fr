---
title: Définition de schéma de DataTable
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: 81da3937b709d4ef046eb1c470546f168bde4132
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="datatable-schema-definition"></a>Définition de schéma de DataTable
Le schéma, ou structure, d'une table est représenté par des colonnes et des contraintes. Vous définissez le schéma d'un objet <xref:System.Data.DataTable> à l'aide d'objets <xref:System.Data.DataColumn> ainsi que d'objets <xref:System.Data.ForeignKeyConstraint> et <xref:System.Data.UniqueConstraint>. Les colonnes d'une table peuvent mapper aux colonnes d'une source de données. Elles contiennent des valeurs calculées à partir d'expressions, incrémentent automatiquement leurs valeurs ou contiennent des valeurs de clé primaire.  
  
 Les références par nom aux colonnes, relations et contraintes d'une table respectent la casse. Une table peut donc contenir plusieurs colonnes, relations ou contraintes dont les noms ne diffèrent que par la casse. Par exemple, vous pouvez avoir **Col1** et **col1**. Dans ce cas, une référence par nom à l'une des colonnes doit correspondre exactement à la casse du nom de colonne. Sinon, une exception est levée. Par exemple, si la table **myTable** contient les colonnes **Col1** et **col1**, vous devez référencer **Col1** par nom comme  **myTable.Columns["Col1 »]**, et **col1** en tant que **myTable.Columns["col1 »]**. Tentative de référencer une des colonnes en tant que **myTable.Columns["COL1 »]** génèrent une exception.  
  
 La règle de respect de la casse ne s'applique pas s'il n'existe qu'une seule colonne, relation ou contrainte ayant un nom particulier. En d'autres termes, si aucun autre objet de colonne, relation ou contrainte de la table ne correspond au nom de cet objet de colonne, relation ou contrainte, vous pouvez référencer l'objet par son nom sans respecter la casse, sans qu'une exception ne soit levée. Par exemple, si la table n’a que **Col1**, vous pouvez faire référence à l’aide de **mon. Colonnes [« COL1 »]**.  
  
> [!NOTE]
>  Le <xref:System.Data.DataTable.CaseSensitive%2A> propriété de la **DataTable** n’affecte pas ce comportement. Le **CaseSensitive** propriété s’applique aux données dans une table et affecte le tri, la recherche, le filtrage, en appliquant des contraintes et ainsi de suite, mais pas pour les références aux colonnes, relations et contraintes.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Ajout de colonnes à un DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 Décrit comment définir les colonnes d’une table à l’aide de **DataColumn** objets.  
  
 [Création de colonnes d’expressions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 Explique comment la **Expression** propriété d’une colonne peut être utilisée pour calculer des valeurs basées sur les valeurs des autres colonnes dans la ligne.  
  
 [Création de colonnes AutoIncrement](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 Décrit comment définir une colonne afin qu'elle incrémente automatiquement des valeurs numériques de façon à garantir le caractère unique des valeurs de colonne d'une ligne.  
  
 [Définition des clés primaires](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 Explique comment spécifier la clé primaire d’une table à partir d’un ou plusieurs **DataColumn** objets.  
  
 [Contraintes de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 Décrit comment définir des contraintes uniques et de clé étrangère pour les colonnes d'une table.  
  
## <a name="see-also"></a>Voir aussi  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Fournisseurs managés ADO.NET et centre de développement DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: 'Comment : spécifier des types de données de base de données'
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 6b13af9be0fd3b10b4849694134b8cf8290a8dfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-database-data-types"></a>Comment : spécifier des types de données de base de données
Utilisez le [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> propriété sur un <xref:System.Data.Linq.Mapping.ColumnAttribute> attribut pour spécifier le texte exact qui définit la colonne dans une déclaration de table T-SQL.  
  
 Vous devez spécifier la propriété <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> uniquement si vous envisagez d'utiliser <xref:System.Data.Linq.DataContext.CreateDatabase%2A> pour créer une instance de la base de données.  
  
 Pour obtenir des exemples de code, consultez <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>Pour spécifier du texte afin de définir un type de données dans une table T-SQL  
  
1.  Ajoutez la propriété <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> à l'attribut <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Affectez la valeur de la propriété <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> au texte exact utilisé par T-SQL.  
  
## <a name="see-also"></a>Voir aussi  
 [Modèle objet LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Guide pratique pour personnaliser des classes d’entité à l’aide de l’éditeur de code](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)

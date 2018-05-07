---
title: Extraction des informations de schéma de base de données
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 1ac39a556fd7539550b12cb71b701c4bd3224a0b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="retrieving-database-schema-information"></a>Extraction des informations de schéma de base de données
L'obtention des informations de schéma à partir d'une base de données est effectuée avec le processus de découverte de schéma. La découverte de schéma permet aux applications de demander que les fournisseurs managés trouvent et retournent des informations sur le schéma de base de données, également appelé *métadonnées*, d’une base de données. Différents éléments de schéma de base de données tels que des tables, des colonnes et des procédures stockées, sont exposés à l’aide de collections de schémas. Chaque collection de schémas contient une série d’informations de schéma spécifiques au fournisseur utilisé.  
  
 Chacune de l’implémentation de fournisseurs managés .NET Framework le **GetSchema** méthode dans le **connexion** classe et les informations de schéma qui sont retournées à partir de la **GetSchema**méthode se présente sous la forme d’un <xref:System.Data.DataTable>. Le **GetSchema** méthode est une méthode surchargée qui fournit des paramètres facultatifs pour spécifier la collection de schémas à retourner et restreindre la quantité d’informations retournées.  
  
 Les fournisseurs de données .NET Framework pour OLE DB, ODBC, Oracle et SqlClient fournissent un **GetSchemaTable** méthode qui retourne un objet DataTable décrivant les métadonnées de colonne de la **DataReader**.  
  
 Le fournisseur de données .NET Framework pour OLE DB expose également des informations de schéma à l'aide de la méthode <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> de l'objet <xref:System.Data.OleDb.OleDbConnection>. En tant qu’arguments, **GetOleDbSchemaTable** prend un <xref:System.Data.OleDb.OleDbSchemaGuid> qui identifie les informations de schéma à retourner et un tableau de restrictions sur ces colonnes retournées. **GetOleDbSchemaTable** retourne un <xref:System.Data.DataTable> rempli avec les informations de schéma demandé.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Collections GetSchema et Schema](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 Décrit la **GetSchema** méthode et comment il peut être utilisé pour extraire et restreindre les informations de schéma à partir d’une base de données.  
  
 Restrictions de schéma  
 Décrit les restrictions de schéma qui peuvent être utilisées avec **GetSchema**.  
  
 [Collections de schémas courantes](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 Décrit toutes les collections de schémas communes prises en charge par tous les fournisseurs .NET Framework managés.  
  
 [Collections de schémas SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 Décrit la collection de schémas prise en charge par le fournisseur .NET Framework pour SQL Server.  
  
 [Collections de schémas Oracle](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 Décrit la collection de schémas prise en charge par le fournisseur .NET Framework pour Oracle.  
  
 [Collections de schémas ODBC](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 Décrit les collections de schémas pour les pilotes ODBC.  
  
 [Collections de schémas OLE DB](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 Décrit les collections de schémas pour les fournisseurs OLE DB.  
  
## <a name="reference"></a>Référence  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 Décrit la **GetSchema** méthode de la <xref:System.Data.Common.DbConnection> classe.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 Décrit la **GetSchema** méthode de la <xref:System.Data.Odbc.OdbcConnection> classe.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 Décrit la **GetSchema** méthode de la <xref:System.Data.OleDb.OleDbConnection> classe.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 Décrit la **GetSchema** méthode de la <xref:System.Data.OracleClient.OracleConnection> classe.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 Décrit la **GetSchema** méthode de la <xref:System.Data.SqlClient.SqlConnection> classe.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 Décrit la **GetSchemaTable** méthode de la <xref:System.Data.Common.DbDataReader> classe.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 Décrit la **GetSchemaTable** méthode de la <xref:System.Data.Odbc.OdbcDataReader> classe.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 Décrit la **GetSchemaTable** méthode de la <xref:System.Data.OleDb.OleDbDataReader> classe.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 Décrit la **GetSchemaTable** méthode de la <xref:System.Data.OracleClient.OracleDataReader> classe.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 Décrit la **GetSchemaTable** méthode de la <xref:System.Data.SqlClient.SqlDataReader> classe.  
  
## <a name="see-also"></a>Voir aussi  
 [Extraction et modification de données dans ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Fournisseurs managés ADO.NET et centre de développement DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

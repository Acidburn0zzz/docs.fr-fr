---
title: Collections de schémas OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766931"
---
# <a name="ole-db-schema-collections"></a>Collections de schémas OLE DB
Cette section traite de la prise en charge des collections de schémas pour les fournisseurs OLE DB de Microsoft SQL Server, Oracle et Microsoft Jet.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Fournisseur Microsoft SQL Server OLE DB  
 Le pilote OLE DB Microsoft SQL Server prend en charge les collections de schémas spécifiques suivantes en plus des collections de schémas courantes :  
  
-   Tables  
  
-   Columns  
  
-   Procédures  
  
-   ProcedureParameters  
  
-   Catalogue  
  
-   Index  
  
### <a name="tables"></a>Tables  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|TABLE_TYPE|Chaîne|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Chaîne|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|COLUMN_NAME|Chaîne|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Chaîne|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Chaîne|  
|CHARACTER_SET_SCHEMA|Chaîne|  
|CHARACTER_SET_NAME|Chaîne|  
|COLLATION_CATALOG|Chaîne|  
|COLLATION_SCHEMA|Chaîne|  
|COLLATION_NAME|Chaîne|  
|DOMAIN_CATALOG|Chaîne|  
|DOMAIN_SCHEMA|Chaîne|  
|DOMAIN_NAME|Chaîne|  
|DESCRIPTION|Chaîne|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Boolean|  
  
### <a name="procedures"></a>Procédures  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Chaîne|  
|PROCEDURE_SCHEMA|Chaîne|  
|PROCEDURE_NAME|Chaîne|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Chaîne|  
|DESCRIPTION|Chaîne|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Chaîne|  
|PROCEDURE_SCHEMA|Chaîne|  
|PROCEDURE_NAME|Chaîne|  
|PARAMETER_NAME|Chaîne|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Boolean|  
|PARAMETER_DEFAULT|Chaîne|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|Chaîne|  
|TYPE_NAME|Chaîne|  
|LOCAL_TYPE_NAME|Chaîne|  
  
### <a name="catalog"></a>Catalogue  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|CATALOG_NAME|Chaîne|  
|DESCRIPTION|Chaîne|  
  
### <a name="indexes"></a>Index  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|INDEX_CATALOG|Chaîne|  
|INDEX_SCHEMA|Chaîne|  
|INDEX_NAME|Chaîne|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Chaîne|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Chaîne|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Fournisseur Microsoft Oracle OLE DB  
 Le pilote Microsoft Oracle OLE DB prend en charge les collections de schémas spécifiques suivantes en plus des collections de schémas courantes :  
  
-   Tables  
  
-   Columns  
  
-   Procédures  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Vues  
  
-   Index  
  
### <a name="tables"></a>Tables  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|TABLE_TYPE|Chaîne|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Chaîne|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|COLUMN_NAME|Chaîne|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Chaîne|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Chaîne|  
|CHARACTER_SET_SCHEMA|Chaîne|  
|CHARACTER_SET_NAME|Chaîne|  
|COLLATION_CATALOG|Chaîne|  
|COLLATION_SCHEMA|Chaîne|  
|COLLATION_NAME|Chaîne|  
|DOMAIN_CATALOG|Chaîne|  
|DOMAIN_SCHEMA|Chaîne|  
|DOMAIN_NAME|Chaîne|  
|DESCRIPTION|Chaîne|  
  
### <a name="procedures"></a>Procédures  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Chaîne|  
|PROCEDURE_SCHEMA|Chaîne|  
|PROCEDURE_NAME|Chaîne|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Chaîne|  
|DESCRIPTION|Chaîne|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Chaîne|  
|PROCEDURE_SCHEMA|Chaîne|  
|PROCEDURE_NAME|Chaîne|  
|COLUMN_NAME|Chaîne|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|Chaîne|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>Vues  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|VIEW_DEFINITION|Chaîne|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|Chaîne|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Index  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|INDEX_CATALOG|Chaîne|  
|INDEX_SCHEMA|Chaîne|  
|INDEX_NAME|Chaîne|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Chaîne|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Chaîne|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Fournisseur Microsoft Jet OLE DB  
 Le pilote Microsoft Jet OLE DB prend en charge les collections de schémas spécifiques suivantes en plus des collections de schémas courantes :  
  
-   Tables  
  
-   Columns  
  
-   Procédures  
  
-   Vues  
  
-   Index  
  
### <a name="tables"></a>Tables  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|TABLE_TYPE|Chaîne|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Chaîne|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|COLUMN_NAME|Chaîne|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Chaîne|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Chaîne|  
|CHARACTER_SET_SCHEMA|Chaîne|  
|CHARACTER_SET_NAME|Chaîne|  
|COLLATION_CATALOG|Chaîne|  
|COLLATION_SCHEMA|Chaîne|  
|COLLATION_NAME|Chaîne|  
|DOMAIN_CATALOG|Chaîne|  
|DOMAIN_SCHEMA|Chaîne|  
|DOMAIN_NAME|Chaîne|  
|DESCRIPTION|Chaîne|  
  
### <a name="procedures"></a>Procédures  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Chaîne|  
|PROCEDURE_SCHEMA|Chaîne|  
|PROCEDURE_NAME|Chaîne|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Chaîne|  
|DESCRIPTION|Chaîne|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>Vues  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|VIEW_DEFINITION|Chaîne|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|Chaîne|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Index  
  
|Nom de colonne|Type de données|  
|----------------|--------------|  
|TABLE_CATALOG|Chaîne|  
|TABLE_SCHEMA|Chaîne|  
|TABLE_NAME|Chaîne|  
|INDEX_CATALOG|Chaîne|  
|INDEX_SCHEMA|Chaîne|  
|INDEX_NAME|Chaîne|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Chaîne|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Chaîne|  
|INTEGRATED|Booléen|  
  
## <a name="see-also"></a>Voir aussi  
 [Fournisseurs managés ADO.NET et centre de développement DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

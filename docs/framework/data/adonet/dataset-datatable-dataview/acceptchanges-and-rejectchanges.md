---
title: AcceptChanges et RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: 65e47bafda3e3e47241405c9c8b8e3b4b0055601
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges et RejectChanges
Après avoir vérifié l’exactitude des modifications apportées aux données dans un <xref:System.Data.DataTable>, vous pouvez accepter les modifications apportées à l’aide de la <xref:System.Data.DataRow.AcceptChanges%2A> méthode de la <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, ou <xref:System.Data.DataSet>, qui définit le **actuel** ligne valeurs de la **d’origine** valeurs et fait passer le **RowState** propriété **Unchanged**. Acceptation ou rejet des modifications supprime toutes les **RowError** informations et définit les **HasErrors** propriété **false**. L'acceptation ou le rejet des modifications peut également affecter la mise à jour des données dans la source de données. Pour plus d’informations, consultez [mise à jour des Sources de données avec DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Si les contraintes de clé étrangères existent sur le **DataTable**, modifications acceptées ou rejetées à l’aide de **AcceptChanges** et **RejectChanges** sont propagées aux lignes enfants de la  **DataRow** conformément à la **ForeignKeyConstraint.AcceptRejectRule**. Pour plus d’informations, consultez [contraintes DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 L'exemple suivant vérifie les lignes ayant des erreurs, résout, le cas échéant, les erreurs et rejette les lignes dans lesquelles les erreurs ne peuvent pas être résolues. Notez que, pour les erreurs résolues, le **RowError** valeur est réinitialisée à une chaîne vide, provoquant la **HasErrors** propriété à définir **false**. Lorsque toutes les lignes avec des erreurs ont été résolues ou rejetées, **AcceptChanges** est appelée pour accepter toutes les modifications pour l’intégralité de **DataTable**.  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Manipulation des données dans un DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Fournisseurs managés ADO.NET et centre de développement DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)

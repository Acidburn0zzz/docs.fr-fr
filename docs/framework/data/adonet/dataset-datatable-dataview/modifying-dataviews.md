---
title: Modification des DataViews
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3b1e0cbfc6118ad9ca670f5d91183b78b2c99d89
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44268534"
---
# <a name="modifying-dataviews"></a>Modification des DataViews
Vous pouvez utiliser l'objet <xref:System.Data.DataView> pour ajouter, supprimer ou modifier des lignes de données dans la table sous-jacente. La possibilité d’utiliser le **DataView** pour modifier des données dans la table sous-jacente est contrôlé en définissant une des trois propriétés de type booléen la **DataView**. Ces propriétés sont <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> et <xref:System.Data.DataView.AllowDelete%2A>. Ils sont définis sur **true** par défaut.  
  
 Si **AllowNew** est **true**, vous pouvez utiliser la <xref:System.Data.DataView.AddNew%2A> méthode de la **DataView** pour créer un nouveau <xref:System.Data.DataRowView>. Notez qu’une nouvelle ligne n’est pas été ajoutée au sous-jacent <xref:System.Data.DataTable> jusqu'à ce que le <xref:System.Data.DataRowView.EndEdit%2A> méthode de la **DataRowView** est appelée. Si le <xref:System.Data.DataRowView.CancelEdit%2A> méthode de la **DataRowView** est appelée, la nouvelle ligne est ignorée. Notez également que vous pouvez modifier qu’un seul **DataRowView** à la fois. Si vous appelez le **AddNew** ou **BeginEdit** méthode de la **DataRowView** alors qu’une ligne en attente existe, **EndEdit** est implicitement appelée sur le ligne en attente. Lorsque **EndEdit** est appelée, les modifications sont appliquées à sous-jacent **DataTable** et pourront ensuite être validées ou refusées à l’aide de la **AcceptChanges** ou  **RejectChanges** méthodes de la **DataTable**, **DataSet**, ou **DataRow** objet. Si **AllowNew** est **false**, une exception est levée si vous appelez le **AddNew** méthode de la **DataRowView**.  
  
 Si **AllowEdit** est **true**, vous pouvez modifier le contenu d’un **DataRow** via la **DataRowView**. Vous pouvez confirmer les modifications apportées à la ligne sous-jacente en utilisant **DataRowView.EndEdit** ou rejeter les modifications apportées à l’aide de **DataRowView.CancelEdit**. Notez que vous ne pouvez modifier qu'une seule ligne à la fois. Si vous appelez le **AddNew** ou **BeginEdit** méthodes de la **DataRowView** alors qu’une ligne en attente existe, **EndEdit** est implicitement appelée sur la ligne en attente. Lorsque **EndEdit** est appelée, les modifications proposées sont placées dans le **actuel** version de ligne de sous-jacent **DataRow** et pourront ensuite être validées ou refusées à l’aide de la  **AcceptChanges** ou **RejectChanges** méthodes de la **DataTable**, **DataSet**, ou **DataRow** objet. Si **AllowEdit** est **false**, une exception est levée si vous tentez de modifier une valeur dans le **DataView**.  
  
 Quand un existant **DataRowView** est en cours de modification, les événements de sous-jacent **DataTable** seront toujours déclenchés avec les modifications proposées. Notez que si vous appelez **EndEdit** ou **CancelEdit** sur sous-jacent **DataRow**, en attente seront appliquées ou annulées indépendamment de si des modifications  **EndEdit** ou **CancelEdit** est appelée sur le **DataRowView**.  
  
 Si **AllowDelete** est **true**, vous pouvez supprimer des lignes à partir de la **DataView** à l’aide de la **supprimer** méthode de la **DataView**  ou **DataRowView** objet et les lignes sont supprimées sous-jacent **DataTable**. Vous pouvez ultérieurement valider ou refuser les suppressions à l’aide de **AcceptChanges** ou **RejectChanges** respectivement. Si **AllowDelete** est **false**, une exception est levée si vous appelez le **supprimer** méthode de la **DataView** ou  **DataRowView**.  
  
 L’exemple de code suivant désactive à l’aide de la **DataView** pour supprimer les lignes et ajoute une nouvelle ligne à la table sous-jacente à l’aide la **DataView**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Fournisseurs managés ADO.NET et centre de développement DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)

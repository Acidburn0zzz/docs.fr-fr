---
title: Accès concurrentiel optimiste
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
ms.openlocfilehash: f2fc69867ae1659a342161b00dfd91852441fa5b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126215"
---
# <a name="optimistic-concurrency"></a>Accès concurrentiel optimiste
Dans un environnement multi-utilisateur, il existe deux modèles pour la mise à jour de données dans une base de données : l'accès simultané optimiste et l'accès simultané pessimiste. L'objet <xref:System.Data.DataSet> est conçu pour privilégier l'utilisation de l'accès simultané optimiste pour les activités longues, comme lors de la communication à distance de données ou de l'interaction avec ces dernières.  
  
 L'accès simultané pessimiste implique le verrouillage de lignes à la source de données pour empêcher que d'autres utilisateurs modifient des données d'une manière affectant l'utilisateur actuel. Dans un modèle pessimiste, lorsqu'un utilisateur effectue une action entraînant l'application d'un verrou, les autres utilisateurs ne peuvent pas effectuer d'actions qui créeraient un conflit avec le verrou tant que le propriétaire de ce dernier ne l'a pas libéré. Ce modèle est principalement utilisé dans les environnements où les conflits relatifs aux données sont fréquents, de sorte que le coût de la protection des données par verrous est inférieur à celui de la restauration des transactions en cas de conflits d’accès simultané.  
  
 Par conséquent, dans un modèle d'accès simultané pessimiste, un utilisateur qui met à jour une ligne crée un verrou. Jusqu'à ce que cet utilisateur ait terminé sa mise à jour et libéré le verrou, personne d'autre ne peut modifier cette ligne. C'est pourquoi il est préférable d'implémenter l'accès simultané pessimiste lorsque les temps de verrouillage sont courts, comme c'est le cas pour le traitement d'enregistrements par programme. L'accès simultané pessimiste ne constitue pas la solution la plus adaptée lorsque des utilisateurs interagissent avec les données, ce qui entraîne le verrouillage d'enregistrements pendant des laps de temps relativement longs.  
  
> [!NOTE]
>  Si vous devez mettre à jour plusieurs lignes en une même opération, la création d’une transaction constitue une option plus adaptée que l’utilisation du verrouillage pessimiste.  
  
 Au contraire, les utilisateurs qui ont recours à un accès simultané optimiste ne verrouillent pas une ligne lorsqu'ils la lisent. Lorsqu'un utilisateur souhaite mettre à jour une ligne, l'application doit déterminer si un autre utilisateur a modifié cette ligne depuis sa dernière lecture. L'accès simultané optimiste est généralement utilisé dans les environnements où les conflits relatifs aux données sont rares. L'accès simultané optimiste améliore les performances, dans la mesure où aucun verrouillage des enregistrements n'est requis et où le verrouillage d'enregistrements nécessite des ressources serveur supplémentaires. Il faut également savoir que la gestion des verrous d'enregistrements requiert une connexion permanente au serveur de base de données. Parce que ce n'est pas le cas dans un modèle d'accès simultané optimiste, les connexions au serveur sont disponibles pour traiter plus rapidement un nombre important de clients.  
  
 Dans un modèle d'accès simultané optimiste, une violation est réputée avoir eu lieu si, après réception par un utilisateur d'une valeur provenant de la base de données, un autre utilisateur modifie cette valeur avant que le premier n'ait tenté de le faire. La manière dont le serveur résout une violation de l'accès simultané est bien illustrée par l'exemple suivant.  
  
 Les tableaux ci-après suivent un exemple d'accès simultané optimiste.  
  
 À 13h00, l'utilisateur 1 lit une ligne de la base de données contenant les valeurs suivantes :  
  
 **CustID LastName FirstName**  
  
 101 Bob Smith  
  
|Nom de la colonne|Valeur d'origine|Valeur actuelle|Valeur dans la base de données|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Bob|Bob|  
  
 À 13h01, l'utilisateur 2 lit la même ligne.  
  
 À 13 h 03, l’utilisateur 2 modifie **FirstName** de « Bob » par « Robert » et met à jour de la base de données.  
  
|Nom de la colonne|Valeur d'origine|Valeur actuelle|Valeur dans la base de données|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Robert|Bob|  
  
 La mise à jour réussit car les valeurs de la base de données au moment de la mise à jour correspondent aux valeurs d'origine dont dispose l'utilisateur 2.  
  
 À 13h05, l'utilisateur 1 modifie la valeur de prénom pour remplacer « Bob » par « James » et tente de mettre à jour la base de données.  
  
|Nom de la colonne|Valeur d'origine|Valeur actuelle|Valeur dans la base de données|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|James|Robert|  
  
 À ce stade, l'utilisateur 1 est confronté à une violation d'accès simultané optimiste, car la valeur de la base de données (« Robert ») ne correspond plus à la valeur d'origine qu'attendait l'utilisateur 1 (« Bob »). La violation d'accès concurrentiel vous indique simplement que la mise à jour a échoué. Il convient maintenant de décider si les modifications apportées par l'utilisateur 2 devront être remplacées par celles de l'utilisateur 1 ou si ces dernières devront être annulées.  
  
## <a name="testing-for-optimistic-concurrency-violations"></a>Recherche des violations d'accès simultané optimiste  
 Il existe plusieurs techniques qui permettent de déceler la présence d'une violation d'accès simultané optimiste. L'une d'entre elles consiste à inclure une colonne horodateur dans la table. Les bases de données proposent généralement une fonctionnalité d'horodatage qui peut être utilisée pour connaître la date et l'heure de la dernière mise à jour d'un enregistrement. En utilisant cette technique, une colonne horodateur est incluse dans la définition de la table. Chaque fois que l'enregistrement est mis à jour, l'horodatage est également mis à jour en fonction de la date et de l'heure actuelles. Dans un test visant à déceler la présence de violations d'accès simultané optimiste, la colonne horodateur est retournée avec toute requête liée au contenu de la table. Lors d'une tentative de mise à jour, la valeur d'horodatage figurant dans la base de données est comparée à la valeur d'origine contenue dans la ligne modifiée. Si les valeurs correspondent, la modification est apportée et la colonne horodateur est mise à jour en fonction de la date et de l'heure actuelles afin de refléter la modification. Si elles ne correspondent pas, une violation d'accès simultané optimiste s'est produite.  
  
 Une autre technique de recherche des violations d'accès simultané optimiste consiste à vérifier que toutes les valeurs de colonne d'origine d'une ligne correspondent toujours à celles qui figurent dans la base de données. Examinons, par exemple, la requête suivante :  
  
```  
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 Pour tester une violation d’accès concurrentiel optimiste lors de la mise à jour une ligne dans **Table1**, émettez l’instruction UPDATE suivante :  
  
```  
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 Tant que les valeurs d'origine correspondent à celles qui figurent dans la base de données, la mise à jour est effectuée. Si une valeur a été modifiée, la mise à jour ne modifiera pas la ligne car la clause WHERE ne trouvera pas de correspondance.  
  
 Notez qu'il est recommandé de toujours retourner une valeur de clé primaire unique dans votre requête. Sinon, l'instruction UPDATE précédente risque de mettre à jour plusieurs lignes, ce qui n'est pas nécessairement dans vos intentions.  
  
 Si une colonne de votre source de données accepte les valeurs null, vous devrez peut-être étendre votre clause WHERE pour vérifier s'il existe une référence null dans votre table locale et sa correspondance dans votre source de données. Par exemple, l'instruction UPDATE suivante vérifie qu'une référence null dans la ligne locale correspond toujours à une référence null dans la source de données, ou si la valeur dans la ligne locale correspond toujours à celle de la source de données.  
  
```  
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 Vous pouvez aussi choisir d'appliquer des critères moins restrictifs lorsque vous utilisez un modèle d'accès simultané optimiste. Par exemple, utiliser uniquement les colonnes de clé primaire dans la clause WHERE aboutit au remplacement des données, que les autres colonnes aient ou non subi une mise à jour depuis la dernière requête. Vous pouvez aussi appliquer une clause WHERE à certaines colonnes uniquement, ce qui aura pour effet de remplacer les données, sauf si des champs spécifiques ont été mis à jour depuis la dernière requête les concernant.  
  
### <a name="the-dataadapterrowupdated-event"></a>Événement DataAdapter.RowUpdated  
 Le **RowUpdated** événements de la <xref:System.Data.Common.DataAdapter> objet peut être utilisé conjointement avec les techniques précédemment décrites, afin de fournir une notification à votre application de violations d’accès concurrentiel optimiste. **RowUpdated** intervient après chaque tentative pour mettre à jour un **Modified** ligne à partir d’un **DataSet**. Cela vous permet d'ajouter un code de gestion spécial, qui traitera les exceptions le cas échéant, ajoutera des informations d'erreur personnalisées, ajoutera une logique pour les nouvelles tentatives, etc. Le <xref:System.Data.Common.RowUpdatedEventArgs> objet retourne un **RecordsAffected** propriété contenant le nombre de lignes affectées par une commande de mise à jour particulière pour une ligne modifiée dans une table. En définissant la commande de mise à jour pour tester l’accès concurrentiel optimiste, la **RecordsAffected** propriété, par conséquent, renvoie la valeur 0 lorsqu’une violation d’accès concurrentiel optimiste s’est produite, car aucun enregistrement ont été mis à jour. Dans ce cas, une exception est levée. Le **RowUpdated** événement vous permet de gérer cet événement et d’éviter l’exception en définissant une **RowUpdatedEventArgs.Status** valeur, telle que  **UpdateStatus.SkipCurrentRow**. Pour plus d’informations sur la **RowUpdated** événement, consultez [gestion des événements DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
 Si vous le souhaitez, vous pouvez définir **DataAdapter.ContinueUpdateOnError** à **true**, avant d’appeler **mise à jour**et répondre aux informations d’erreur stockées dans le **RowError** ligne de propriété d’un particulier lorsque le **mise à jour** est terminée. Pour plus d’informations, consultez [informations d’erreur de ligne](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md).  
  
## <a name="optimistic-concurrency-example"></a>Exemple d'accès simultané optimiste  
 Voici un exemple simple qui définit les **UpdateCommand** d’un **DataAdapter** pour tester l’accès concurrentiel optimiste et utilise ensuite le **RowUpdated** événement à tester pour violations d’accès concurrentiel optimiste. Une violation d’accès concurrentiel optimiste, l’application définit le **RowError** de la ligne de la mise à jour a été émis pour afin de refléter une violation d’accès concurrentiel optimiste.  
  
 Notez que les valeurs de paramètre passées à la clause WHERE de la commande de mise à jour sont mappées à la **d’origine** valeurs de leurs colonnes respectives.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then   
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName", connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)   
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a>Voir aussi

- [Extraction et modification de données dans ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Mise à jour des sources de données avec les DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [Informations sur l'erreur de ligne](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)
- [Transactions et accès simultané](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [Fournisseurs managés ADO.NET et centre de développement DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)

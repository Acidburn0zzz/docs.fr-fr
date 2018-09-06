---
title: "Procédure pas à pas : affichage de données d'une base de données SQL Server dans un contrôle DataGrid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 1421d076ff202ec87a9d861ab2c7d1c1cdcdc1b7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43798724"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Procédure pas à pas : affichage de données d'une base de données SQL Server dans un contrôle DataGrid
Dans cette procédure pas à pas, vous récupérer des données à partir d’une base de données SQL Server et afficher ces données dans un <xref:System.Windows.Controls.DataGrid> contrôle. ADO.NET Entity Framework vous permet de créer les classes d’entité qui représentent les données et utilisent LINQ pour écrire une requête qui Récupère les données spécifiées à partir d’une classe d’entité.  
  
## <a name="prerequisites"></a>Prérequis  
 Pour exécuter cette procédure pas à pas, vous devez disposer des composants suivants :  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
-   Accès à une instance en cours d’exécution de SQL Server ou SQL Server Express qui a la base de données AdventureWorks attachée. Vous pouvez télécharger la base de données AdventureWorks à partir de la [GitHub](https://github.com/Microsoft/sql-server-samples/releases).  
  
### <a name="to-create-entity-classes"></a>Pour créer des classes d’entité  
  
1.  Créez un nouveau projet d’Application WPF en Visual Basic ou c# et nommez-le `DataGridSQLExample`.  
  
2.  Dans l’Explorateur de solutions, cliquez sur votre projet, pointez sur **ajouter**, puis sélectionnez **un nouvel élément**.  
  
     La boîte de dialogue Ajouter un nouvel élément s’affiche.  
  
3.  Dans le volet Modèles installés, sélectionnez **données** et dans la liste des modèles, sélectionnez **ADO.NET Entity Data Mode**l.  
  
     ![Sélectionnez ADO.NET Entity Data Model](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step1.png "DataGrid_SQL_EF_Step1")  
  
4.  Nommez le fichier `AdventureWorksModel.edmx` puis cliquez sur **ajouter**.  
  
     L'Assistant Entity Data Model s'affiche.  
  
5.  Dans l’écran Choisir le contenu du modèle, sélectionnez **générer à partir de la base de données** puis cliquez sur **suivant**.  
  
     ![Sélectionnez générer à partir de l’option de base de données](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step2.png "DataGrid_SQL_EF_Step2")  
  
6.  Dans l’écran Choisir votre connexion de données, fournissez la connexion à votre base de données AdventureWorksLT2008. Pour plus d’informations, consultez [boîte de dialogue Choisir votre connexion de données](https://go.microsoft.com/fwlink/?LinkId=160190).  
  
     ![Fournir la connexion à la base de données](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step3.png "DataGrid_SQL_EF_Step3")  
  
7.  Assurez-vous que le nom est `AdventureWorksLT2008Entities` et que le **enregistrer des paramètres de connexion entity dans App.Config en tant que** case à cocher est sélectionnée, puis cliquez sur **suivant**.  
  
8.  Dans l’écran Choisir vos objets de base de données, développez le nœud Tables, puis sélectionnez le **produit** et **ProductCategory** tables.  
  
     Vous pouvez générer des classes d’entités pour toutes les tables ; Toutefois, dans cet exemple vous uniquement récupérer des données à partir de ces deux tables.  
  
     ![Sélectionner Product et ProductCategory à partir des tables](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")  
  
9. Cliquez sur **Terminer**.  
  
     Les entités Product et ProductCategory sont affichées dans le Concepteur d’entités.  
  
     ![Modèles d’entité Product et ProductCategory](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")  
  
### <a name="to-retrieve-and-present-the-data"></a>Pour récupérer et de présenter les données  
  
1.  Ouvrez le fichier MainWindow.xaml.  
  
2.  Définir le <xref:System.Windows.FrameworkElement.Width%2A> propriété sur le <xref:System.Windows.Window> à 450.  
  
3.  Dans l’éditeur XAML, ajoutez le code suivant <xref:System.Windows.Controls.DataGrid> balise entre les `<Grid>` et `</Grid>` balises pour ajouter un <xref:System.Windows.Controls.DataGrid> nommé `dataGrid1`.  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]  
  
     ![Fenêtre avec DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")  
  
4.  Sélectionnez le contrôle <xref:System.Windows.Window>.  
  
5.  À l’aide de la fenêtre Propriétés ou l’éditeur XAML, créez un gestionnaire d’événements pour le <xref:System.Windows.Window> nommé `Window_Loaded` pour le <xref:System.Windows.FrameworkElement.Loaded> événement. Pour plus d’informations, consultez [Comment : créer un gestionnaire d’événements Simple](https://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).  
  
     L’exemple suivant montre le XAML pour MainWindow.xaml.  
  
    > [!NOTE]
    >  Si vous utilisez Visual Basic, dans la première ligne de MainWindow.xaml, remplacez `x:Class="DataGridSQLExample.MainWindow"` avec `x:Class="MainWindow"`.  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]  
  
6.  Ouvrez le fichier code-behind (MainWindow.xaml.vb ou MainWindow.xaml.cs) pour le <xref:System.Windows.Window>.  
  
7.  Ajoutez le code suivant pour récupérer uniquement les valeurs spécifiques des tables jointes et définir le <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propriété de la <xref:System.Windows.Controls.DataGrid> aux résultats de la requête.  
  
     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]  
  
8.  Exécutez l'exemple.  
  
     Vous devez voir un <xref:System.Windows.Controls.DataGrid> qui affiche des données.  
  
     ![DataGrid avec des données à partir de la base de données SQL](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")  
  
## <a name="next-steps"></a>Étapes suivantes  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Controls.DataGrid>  
 [Comment : comment pour démarrer avec Entity Framework dans les Applications WPF ?](https://go.microsoft.com/fwlink/?LinkId=159868)

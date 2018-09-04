---
title: Exemple LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 83dc8433459f64860baaca2e8309fbc85e2bb3a2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515366"
---
# <a name="linq-to-sql-sample"></a>Exemple LINQ to SQL
Cet exemple montre comment créer une activité pour utiliser des entités de requêtes LINQ to SQL de tables dans des bases de données SQL Server.  
  
> [!IMPORTANT]
>  Les exemples WCF peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  Si ce répertoire n'existe pas, cliquez sur le lien de téléchargement de l'exemple situé en haut de cette page. Notez que ce lien télécharge et installe tous les [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, et [!INCLUDE[infocard](../../../../includes/infocard-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a>Détails de l'activité pour FindInSqlTable  
 Cette activité permet aux utilisateurs d'interroger des entités de tables dans une base de données à l'aide de LINQ to SQL. Les utilisateurs de l'activité peuvent également fournir un prédicat LINQ sous la forme d'une expression lambda pour filtrer les résultats. Si aucun prédicat n'est fourni, la totalité de la table est retournée. Le tableau suivant décrit en détail les propriétés et valeurs de retour pour l'activité.  
  
|Propriété ou valeur de retour|Description|  
|------------------------------|-----------------|  
|Propriété `Collection`|Propriété requise qui spécifie la collection source.|  
|Propriété `Predicate`|Propriété requise qui spécifie le filtre pour la collection sous la forme d'une expression lambda.|  
|Valeur de retour|Collection filtrée.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>Exemple de code qui utilise l'activité personnalisée  
 L'exemple de code suivant utilise l'activité personnalisée `FindInSqlTable` pour rechercher toutes les lignes d'une table SQL Server nommée `Employee` où la colonne `Role` est égale à `SDE`.  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a>Pour utiliser cet exemple  
  
1.  Ouvrez une invite de commandes.  
  
2.  Accédez au dossier qui contient cet exemple.  
  
3.  Exécutez le fichier de commandes Setup.cmd.  
  
    > [!NOTE]
    >  Le script Setup.cmd tente d'installer l'exemple de base de données sur votre ordinateur local SQL Server Express. Si vous voulez l'installer dans une autre instance SQL Server, modifiez Setup.cmd.  
  
     Le script Setup.cmd effectue les actions suivantes :  
  
    -   Crée une base de données appelée LinqToSqlSample.  
  
    -   Crée une table Roles.  
  
    -   Crée une table Employees.  
  
    -   Insère 3 enregistrements dans la table Roles.  
  
    -   Insère 12 enregistrements dans la table Employees.  
  
4.  À l'aide de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ouvrez le fichier solution LinqToSQL.sln.  
  
5.  Pour générer la solution, appuyez sur Ctrl+Maj+B.  
  
6.  Pour exécuter la solution, appuyez sur F5.  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a>Pour désinstaller l'exemple de base de données LinqToSql  
  
1.  Ouvrez une invite de commandes.  
  
2.  Accédez au dossier qui contient cet exemple.  
  
3.  Exécutez le fichier de commandes Cleanup.cmd.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a>Voir aussi  
 [LINQ to SQL](https://go.microsoft.com/fwlink/?LinkId=150376)  
 [Mise en route (LINQ to SQL)](https://go.microsoft.com/fwlink/?LinkId=150377)

---
title: "Procédure pas à pas : accès à une base de données SQL Database à l'aide des fournisseurs de type et des entités (F#)"
description: "Découvrez comment accéder aux données typées pour une base de données SQL en fonction de l’ADO.NET Entity Data Model dans F # 3.0."
keywords: visual f#, f#, programmation fonctionnelle
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 153050f27ade0152741bdc2d77ab85eefa8418e9
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a><span data-ttu-id="54e6c-104">Procédure pas à pas : accès à une base de données SQL Database à l'aide des fournisseurs de type et des entités</span><span class="sxs-lookup"><span data-stu-id="54e6c-104">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>

> [!NOTE]
<span data-ttu-id="54e6c-105">Ce guide a été écrit pour F # 3.0 et sera mise à jour.</span><span class="sxs-lookup"><span data-stu-id="54e6c-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="54e6c-106">Pour obtenir la liste la plus récente des fournisseurs de type multiplateformes, consultez [FSharp.Data](https://fsharp.github.io/FSharp.Data/).</span><span class="sxs-lookup"><span data-stu-id="54e6c-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="54e6c-107">Les liens de référence d’API vous permettront de MSDN.</span><span class="sxs-lookup"><span data-stu-id="54e6c-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="54e6c-108">Les informations de référence sur les API docs.microsoft.com ne sont pas terminées.</span><span class="sxs-lookup"><span data-stu-id="54e6c-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="54e6c-109">Cette procédure pas à pas pour F# 3.0 indique comment accéder à des données typées pour une base de données SQL sur ADO.NET Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="54e6c-109">This walkthrough for F# 3.0 shows you how to access typed data for a SQL database based on the ADO.NET Entity Data Model.</span></span> <span data-ttu-id="54e6c-110">Cette procédure pas à pas indique comment installer le fournisseur de type F# `SqlEntityConnection` à utiliser avec une base de données SQL, comment écrire des requêtes sur les données, comment appeler des procédures stockées sur la base de données, et comment utiliser certains types et méthodes ADO.NET Entity Framework pour mettre à jour la base de données.</span><span class="sxs-lookup"><span data-stu-id="54e6c-110">This walkthrough shows you how to set up the F# `SqlEntityConnection` type provider for use with a SQL database, how to write queries against the data, how to call stored procedures on the database, as well as how to use some of the ADO.NET Entity Framework types and methods to update the database.</span></span>

<span data-ttu-id="54e6c-111">Les tâches suivantes, décrites dans cette procédure pas à pas, doivent être exécutées dans cet ordre pour la réussite de cette dernière :</span><span class="sxs-lookup"><span data-stu-id="54e6c-111">This walkthrough illustrates the following tasks, which you should perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="54e6c-112">Créer la base de données School</span><span class="sxs-lookup"><span data-stu-id="54e6c-112">Create the School database</span></span>
<br />

- <span data-ttu-id="54e6c-113">Créer et configurer un projet F#</span><span class="sxs-lookup"><span data-stu-id="54e6c-113">Create and configure an F# project</span></span>
<br />

- <span data-ttu-id="54e6c-114">Configurer le fournisseur de type et de se connecter à l’Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="54e6c-114">Configure the type provider and connect to the Entity Data Model</span></span>
<br />

- <span data-ttu-id="54e6c-115">La base de données</span><span class="sxs-lookup"><span data-stu-id="54e6c-115">Query the database</span></span>
<br />

- <span data-ttu-id="54e6c-116">Mise à jour de la base de données</span><span class="sxs-lookup"><span data-stu-id="54e6c-116">Updating the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="54e6c-117">Prérequis</span><span class="sxs-lookup"><span data-stu-id="54e6c-117">Prerequisites</span></span>
<span data-ttu-id="54e6c-118">Vous devez avoir accès à un serveur qui exécute SQL Server sur lequel vous pouvez créer une base de données pour effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="54e6c-118">You must have access to a server that's running SQL Server where you can create a database to complete these steps.</span></span>

## <a name="create-the-school-database"></a><span data-ttu-id="54e6c-119">Créer la base de données School</span><span class="sxs-lookup"><span data-stu-id="54e6c-119">Create the School database</span></span>
<span data-ttu-id="54e6c-120">Vous pouvez créer la base de données School sur un serveur qui exécute SQL Server et auquel vous avez un accès administratif, ou vous pouvez utiliser LocalDB.</span><span class="sxs-lookup"><span data-stu-id="54e6c-120">You can create the School database on any server that's running SQL Server to which you have administrative access, or you can use LocalDB.</span></span>


#### <a name="to-create-the-school-database"></a><span data-ttu-id="54e6c-121">Pour créer la base de données School</span><span class="sxs-lookup"><span data-stu-id="54e6c-121">To create the School database</span></span>

1. <span data-ttu-id="54e6c-122">Dans **l’Explorateur de serveurs**, ouvrez le menu contextuel pour le **des connexions de données** nœud, puis choisissez **ajouter une connexion**.</span><span class="sxs-lookup"><span data-stu-id="54e6c-122">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and then choose **Add Connection**.</span></span>
<br />  <span data-ttu-id="54e6c-123">Le **ajouter une connexion** boîte de dialogue s’affiche.</span><span class="sxs-lookup"><span data-stu-id="54e6c-123">The **Add Connection** dialog box appears.</span></span>
<br />

2. <span data-ttu-id="54e6c-124">Dans le **nom du serveur** zone, spécifiez le nom d’une instance de SQL Server à laquelle vous avez un accès administratif ou spécifiez (LocalDB \ V11.0) si vous n’avez pas accès à un serveur.</span><span class="sxs-lookup"><span data-stu-id="54e6c-124">In the **Server name** box, specify the name of an instance of SQL Server to which you have administrative access, or specify (localdb\v11.0) if you don't have access to a server.</span></span>
<br />  <span data-ttu-id="54e6c-125">SQL Server Express LocalDB fournit un serveur de base de données léger pour le développement et les tests sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="54e6c-125">SQL Server Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="54e6c-126">Pour plus d’informations sur la base de données locale, consultez [procédure pas à pas : création d’un fichier de base de données Local dans Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span><span class="sxs-lookup"><span data-stu-id="54e6c-126">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>
<br />  <span data-ttu-id="54e6c-127">Un nœud est créé dans **l’Explorateur de serveurs** sous **des connexions de données**.</span><span class="sxs-lookup"><span data-stu-id="54e6c-127">A new node is created in **Server Explorer** under **Data Connections**.</span></span>
<br />

3. <span data-ttu-id="54e6c-128">Ouvrez le menu contextuel pour le nouveau nœud de connexion, puis choisissez **nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="54e6c-128">Open the shortcut menu for the new connection node, and then choose **New Query**.</span></span>
<br />

4. <span data-ttu-id="54e6c-129">Ouvrez [création de la base de données School](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) dans le site Web de Microsoft, puis copiez et collez le script de base de données qui crée la base de données School dans la fenêtre d’éditeur.</span><span class="sxs-lookup"><span data-stu-id="54e6c-129">Open [Creating the School Sample Database](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) on the Microsoft website, and then copy and paste the database script that creates the School database into the editor window.</span></span>
<br />


## <span data-ttu-id="54e6c-130"><a name="BKMK_CreateConfigFSProj"> </a></span><span class="sxs-lookup"><span data-stu-id="54e6c-130"><a name="BKMK_CreateConfigFSProj"> </a></span></span>

## <a name="create-and-configure-an-f-project"></a><span data-ttu-id="54e6c-131">Créer et configurer un projet F#</span><span class="sxs-lookup"><span data-stu-id="54e6c-131">Create and configure an F# project</span></span>
<span data-ttu-id="54e6c-132">Dans cette étape, vous créez un projet et le configurez pour utiliser un fournisseur de type.</span><span class="sxs-lookup"><span data-stu-id="54e6c-132">In this step, you create a project and set it up to use a type provider.</span></span>


#### <a name="to-create-and-configure-an-f-project"></a><span data-ttu-id="54e6c-133">Pour créer et configurer un projet F#</span><span class="sxs-lookup"><span data-stu-id="54e6c-133">To create and configure an F# project</span></span>

1. <span data-ttu-id="54e6c-134">Fermez le projet précédent, créez un autre projet et nommez-le **SchoolEDM**.</span><span class="sxs-lookup"><span data-stu-id="54e6c-134">Close the previous project, create another project, and name it **SchoolEDM**.</span></span>
<br />

2. <span data-ttu-id="54e6c-135">Dans **l’Explorateur de solutions**, ouvrez le menu contextuel pour **références**, puis choisissez **ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="54e6c-135">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="54e6c-136">Choisissez le **Framework** nœud, puis, dans le **Framework** , choisissez **System.Data**, **System.Data.Entity**et **System.Data.Linq**.</span><span class="sxs-lookup"><span data-stu-id="54e6c-136">Choose the **Framework** node, and then, in the **Framework** list, choose **System.Data**, **System.Data.Entity**,  and **System.Data.Linq**.</span></span>
<br />

4. <span data-ttu-id="54e6c-137">Choisissez le **Extensions** nœud, ajouter une référence à la [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, puis choisissez le **OK** bouton pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="54e6c-137">Choose the **Extensions** node, add a reference to the [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, and then choose the **OK** button to dismiss the dialog box.</span></span>
<br />

5. <span data-ttu-id="54e6c-138">Ajoutez le code suivant pour définir un module interne et ouvrir les espaces de noms appropriés.</span><span class="sxs-lookup"><span data-stu-id="54e6c-138">Add the following code to define an internal module and open appropriate namespaces.</span></span> <span data-ttu-id="54e6c-139">Le fournisseur de type peut injecter des types uniquement dans un espace de noms privé ou interne.</span><span class="sxs-lookup"><span data-stu-id="54e6c-139">The type provider can inject types only into a private or internal namespace.</span></span>
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. <span data-ttu-id="54e6c-140">Pour exécuter le code dans cette procédure pas à pas de façon interactive en tant que script au lieu d’en tant qu’un programme compilé, ouvrez le menu contextuel du nœud de projet, choisissez **ajouter un nouvel élément**, ajoutez un fichier de script F #, puis ajoutez le code dans chaque étape du script.</span><span class="sxs-lookup"><span data-stu-id="54e6c-140">To run the code in this walkthrough interactively as a script instead of as a compiled program, open the shortcut menu for the project node, choose **Add New Item**, add an F# script file, and then add the code in each step to the script.</span></span> <span data-ttu-id="54e6c-141">Pour charger les références d'assembly, ajoutez les lignes suivantes.</span><span class="sxs-lookup"><span data-stu-id="54e6c-141">To load the assembly references, add the following lines.</span></span>
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. <span data-ttu-id="54e6c-142">Mettez en surbrillance chaque bloc de code au fur et à mesure que vous l'ajoutez, puis appuyez sur Alt+Entrée pour l'exécuter dans F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="54e6c-142">Highlight each block of code as you add it, and choose the Alt + Enter keys to run it in F# Interactive.</span></span>
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="54e6c-143">Configurer le fournisseur de type et se connecter à l’Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="54e6c-143">Configure the type provider, and connect to the Entity Data Model</span></span>
<span data-ttu-id="54e6c-144">Dans cette étape, vous configurez un fournisseur de type avec une connexion de données et obtenez un contexte de données qui vous permet d’utiliser des données.</span><span class="sxs-lookup"><span data-stu-id="54e6c-144">In this step, you set up a type provider with a data connection and obtain a data context that allows you to work with data.</span></span>


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="54e6c-145">Pour configurer le fournisseur de type et se connecter à l'Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="54e6c-145">To configure the type provider, and connect to the Entity Data Model</span></span>

1. <span data-ttu-id="54e6c-146">Entrez le code suivant pour configurer le fournisseur de type `SqlEntityConnection` qui génère des types F# basés sur l'Entity Data Model que vous avez créés précédemment.</span><span class="sxs-lookup"><span data-stu-id="54e6c-146">Enter the following code to configure the `SqlEntityConnection` type provider that generates F# types based on the Entity Data Model that you created previously.</span></span> <span data-ttu-id="54e6c-147">Au lieu de la chaîne de connexion complète EDMX, utilisez uniquement la chaîne de connexion SQL.</span><span class="sxs-lookup"><span data-stu-id="54e6c-147">Instead of the full EDMX connection string, use only the SQL connection string.</span></span>
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  <span data-ttu-id="54e6c-148">Cette action configure un fournisseur de type avec la connexion de base de données que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="54e6c-148">This action sets up a type provider with the database connection that you created earlier.</span></span> <span data-ttu-id="54e6c-149">La propriété `MultipleActiveResultSets` est nécessaire lorsque vous utilisez ADO.NET Entity Framework, car cette propriété permet à plusieurs commandes de s'exécuter de façon asynchrone sur la base de données dans une connexion, ce qui peut se produire fréquemment dans le code ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="54e6c-149">The property `MultipleActiveResultSets` is needed when you use the ADO.NET Entity Framework because this property allows multiple commands to execute asynchronously on the database in one connection, which can occur frequently in ADO.NET Entity Framework code.</span></span> <span data-ttu-id="54e6c-150">Pour plus d’informations, consultez [MARS (Multiple Active Result Sets)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span><span class="sxs-lookup"><span data-stu-id="54e6c-150">For more information, see [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span></span>
<br />

2. <span data-ttu-id="54e6c-151">Obtenez le contexte de données, qui est un objet qui contient les tables de base de données en tant que propriétés et les procédures et fonctions stockées de base de données en tant que méthodes.</span><span class="sxs-lookup"><span data-stu-id="54e6c-151">Get the data context, which is an object that contains the database tables as properties and the database stored procedures and functions as methods.</span></span>
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a><span data-ttu-id="54e6c-152">Interroger la base de données</span><span class="sxs-lookup"><span data-stu-id="54e6c-152">Querying the database</span></span>
<span data-ttu-id="54e6c-153">Dans cette étape, vous utilisez des expressions de requête F# pour exécuter diverses requêtes sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="54e6c-153">In this step, you use F# query expressions to execute various queries on the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="54e6c-154">Pour interroger les données</span><span class="sxs-lookup"><span data-stu-id="54e6c-154">To query the data</span></span>

- <span data-ttu-id="54e6c-155">Entrez le code suivant pour interroger les données de l'Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="54e6c-155">Enter the following code to query the data from the entity data model.</span></span> <span data-ttu-id="54e6c-156">Notez l'effet de Pluralize = true, qui modifie la table de base de données Course par Courses et Person par People.</span><span class="sxs-lookup"><span data-stu-id="54e6c-156">Note the effect of Pluralize = true, which changes the database table Course to Courses and Person to People.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a><span data-ttu-id="54e6c-157">Mise à jour de la base de données</span><span class="sxs-lookup"><span data-stu-id="54e6c-157">Updating the database</span></span>
<span data-ttu-id="54e6c-158">Pour mettre à jour la base de données, vous utilisez les classes et les méthodes Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="54e6c-158">To update the database, you use the Entity Framework classes and methods.</span></span> <span data-ttu-id="54e6c-159">Vous pouvez utiliser deux types de contexte de données avec le fournisseur de type SQLEntityConnection.</span><span class="sxs-lookup"><span data-stu-id="54e6c-159">You can use two types of data context with the SQLEntityConnection type provider.</span></span> <span data-ttu-id="54e6c-160">En premier lieu, `ServiceTypes.SimpleDataContextTypes.EntityContainer` est le contexte de données simplifié, qui inclut uniquement les propriétés fournies qui représentent des tables et des colonnes de base de données.</span><span class="sxs-lookup"><span data-stu-id="54e6c-160">First, `ServiceTypes.SimpleDataContextTypes.EntityContainer` is the simplified data context, which includes only the provided properties that represent database tables and columns.</span></span> <span data-ttu-id="54e6c-161">Ensuite, le contexte de données complet est une instance de la classe Entity Framework `System.Data.Objects.ObjectContext`, qui contient la méthode `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` pour ajouter des lignes à la base de données.</span><span class="sxs-lookup"><span data-stu-id="54e6c-161">Second, the full data context is an instance of the Entity Framework class `System.Data.Objects.ObjectContext`, which contains the method `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` to add rows to the database.</span></span> <span data-ttu-id="54e6c-162">L’Entity Framework reconnaît des tables et des relations entre elles, ce qui garantit la cohérence de base de données.</span><span class="sxs-lookup"><span data-stu-id="54e6c-162">The Entity Framework recognizes the tables and the relationships between them, so it enforces database consistency.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="54e6c-163">Pour mettre à jour la base de données</span><span class="sxs-lookup"><span data-stu-id="54e6c-163">To update the database</span></span>

1. <span data-ttu-id="54e6c-164">Ajoutez le code suivant à votre programme.</span><span class="sxs-lookup"><span data-stu-id="54e6c-164">Add the following code to your program.</span></span> <span data-ttu-id="54e6c-165">Dans cet exemple, vous ajoutez deux objets ayant une relation entre eux, et vous ajoutez un formateur et une attribution de lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="54e6c-165">In this example, you add two objects with a relationship between them, and you add an instructor and an office assignment.</span></span> <span data-ttu-id="54e6c-166">Le tableau `OfficeAssignments` contient la colonne `InstructorID`, qui référence la colonne `PersonID` dans le tableau `Person`.</span><span class="sxs-lookup"><span data-stu-id="54e6c-166">The table `OfficeAssignments` contains the `InstructorID` column, which references the `PersonID` column in the `Person` table.</span></span>
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

<span data-ttu-id="54e6c-167">Rien n'est modifié dans la base de données jusqu'à ce que vous appeliez `System.Data.Objects.ObjectContext.SaveChanges`.</span><span class="sxs-lookup"><span data-stu-id="54e6c-167">Nothing is changed in the database until you call `System.Data.Objects.ObjectContext.SaveChanges`.</span></span>
<br />

2. <span data-ttu-id="54e6c-168">À présent, restaurez la base de données afin qu'elle retrouve son précédent état en supprimant les objets que vous avez ajoutés.</span><span class="sxs-lookup"><span data-stu-id="54e6c-168">Now restore the database to its earlier state by deleting the objects that you added.</span></span>
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
<span data-ttu-id="54e6c-169">Lorsque vous utilisez une expression de requête, gardez en mémoire que la requête est sujette à l'évaluation tardive.</span><span class="sxs-lookup"><span data-stu-id="54e6c-169">When you use a query expression, you must remember that the query is subject to lazy evaluation.</span></span> <span data-ttu-id="54e6c-170">Par conséquent, la base de données est encore ouverte pour lecture pendant les évaluations chaînées, comme dans les blocs d'expression lambda après chaque expression de requête.</span><span class="sxs-lookup"><span data-stu-id="54e6c-170">Therefore, the database is still open for reading during any chained evaluations, such as in the lambda expression blocks after each query expression.</span></span> <span data-ttu-id="54e6c-171">Toute opération de base de données qui utilise explicitement ou implicitement une transaction doit se produire après que les opérations de lecture soient terminées.</span><span class="sxs-lookup"><span data-stu-id="54e6c-171">Any database operation that explicitly or implicitly uses a transaction must occur after the read operations have completed.</span></span>


## <a name="next-steps"></a><span data-ttu-id="54e6c-172">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="54e6c-172">Next Steps</span></span>
<span data-ttu-id="54e6c-173">Explorer d’autres options de requête en examinant les opérateurs de requête disponibles dans [les Expressions de requête](../../language-reference/query-expressions.md)et aussi passer en revue les [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) à comprendre quelles sont les fonctionnalités à votre disposition quand vous utilisez ce fournisseur de type.</span><span class="sxs-lookup"><span data-stu-id="54e6c-173">Explore other query options by reviewing the query operators available in [Query Expressions](../../language-reference/query-expressions.md), and also review the [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) to understand what functionality is available to you when you use this type provider.</span></span>


## <a name="see-also"></a><span data-ttu-id="54e6c-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54e6c-174">See Also</span></span>
[<span data-ttu-id="54e6c-175">Fournisseurs de type</span><span class="sxs-lookup"><span data-stu-id="54e6c-175">Type Providers</span></span>](index.md)  
[<span data-ttu-id="54e6c-176">Fournisseur de Type de SqlEntityConnection</span><span class="sxs-lookup"><span data-stu-id="54e6c-176">SqlEntityConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[<span data-ttu-id="54e6c-177">Procédure pas à pas : Génération de Types F # à partir d’un fichier de schéma EDMX</span><span class="sxs-lookup"><span data-stu-id="54e6c-177">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>](generating-fsharp-types-from-edmx.md)  
[<span data-ttu-id="54e6c-178">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="54e6c-178">ADO.NET Entity Framework</span></span>](https://msdn.microsoft.com/library/bb399572)  
[<span data-ttu-id="54e6c-179">vue d’ensemble du fichier .edmx</span><span class="sxs-lookup"><span data-stu-id="54e6c-179">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[<span data-ttu-id="54e6c-180">EDM Generator &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="54e6c-180">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)  

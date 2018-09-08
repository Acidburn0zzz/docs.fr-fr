---
title: Restrictions de schéma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198606"
---
# <a name="schema-restrictions"></a><span data-ttu-id="4f8d8-102">Restrictions de schéma</span><span class="sxs-lookup"><span data-stu-id="4f8d8-102">Schema Restrictions</span></span>
<span data-ttu-id="4f8d8-103">Le deuxième paramètre facultatif de la **GetSchema** méthode est retournée les restrictions qui sont utilisées pour limiter la quantité d’informations de schéma, et il est transmis à la **GetSchema** sous forme de tableau de chaînes (méthode) .</span><span class="sxs-lookup"><span data-stu-id="4f8d8-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="4f8d8-104">La position dans le tableau détermine les valeurs que vous pouvez passer et équivaut au numéro de restriction.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="4f8d8-105">Par exemple, le tableau suivant décrit les restrictions prises en charge par la collection de schémas « Tables » utilisant le fournisseur de données .NET Framework pour SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="4f8d8-106">Des restrictions supplémentaires pour les collections de schémas SQL Server figurent à la fin de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="4f8d8-107">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-107">Restriction Name</span></span>|<span data-ttu-id="4f8d8-108">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-108">Parameter Name</span></span>|<span data-ttu-id="4f8d8-109">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-109">Restriction Default</span></span>|<span data-ttu-id="4f8d8-110">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-111">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-111">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-112">TABLE_CATALOG</span></span>|<span data-ttu-id="4f8d8-113">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-113">1</span></span>|  
|<span data-ttu-id="4f8d8-114">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-114">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="4f8d8-116">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-116">2</span></span>|  
|<span data-ttu-id="4f8d8-117">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-117">Table</span></span>|@Name|<span data-ttu-id="4f8d8-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-118">TABLE_NAME</span></span>|<span data-ttu-id="4f8d8-119">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-119">3</span></span>|  
|<span data-ttu-id="4f8d8-120">TableType</span><span class="sxs-lookup"><span data-stu-id="4f8d8-120">TableType</span></span>|@TableType|<span data-ttu-id="4f8d8-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4f8d8-121">TABLE_TYPE</span></span>|<span data-ttu-id="4f8d8-122">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="4f8d8-123">Spécification des valeurs de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="4f8d8-124">Pour utiliser l’une des restrictions de la collection de schémas « Tables », créez simplement un tableau de chaînes contenant quatre éléments, puis placez une valeur dans l’élément correspondant au numéro de restriction.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="4f8d8-125">Par exemple, pour restreindre les tables retournées par la **GetSchema** méthode exclusivement aux tables dans le schéma « Ventes », définissez le second élément du tableau sur « Sales » avant de le transmettre à la **GetSchema** (méthode).</span><span class="sxs-lookup"><span data-stu-id="4f8d8-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f8d8-126">Les collections de restrictions pour `SqlClient` et `OracleClient` comportent une colonne `ParameterName` supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="4f8d8-127">La colonne par défaut de la restriction est encore là pour la compatibilité ascendante, mais est désormais ignorée.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="4f8d8-128">Il convient d'utiliser des requêtes paramétrées plutôt qu'un remplacement de chaîne afin de minimiser le risque d'attaque par injection SQL lors de la spécification de valeurs de restriction.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f8d8-129">Le nombre d'éléments du tableau doit être inférieur ou égal au nombre de restrictions prises en charge pour la collection de schémas spécifiée, sans quoi une exception <xref:System.ArgumentException> est levée.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="4f8d8-130">Il peut y avoir moins de restrictions que le nombre maximal de restrictions.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="4f8d8-131">Les restrictions manquantes sont supposées avoir la valeur null (aucune restriction).</span><span class="sxs-lookup"><span data-stu-id="4f8d8-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="4f8d8-132">Vous pouvez interroger un fournisseur .NET Framework managé afin de déterminer la liste des restrictions prises en charge en appelant le **GetSchema** méthode portant le nom de la collection de schémas de restrictions, « restrictions ».</span><span class="sxs-lookup"><span data-stu-id="4f8d8-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="4f8d8-133">Cette opération retourne un <xref:System.Data.DataTable> contenant une liste des noms de collections, des noms de restriction, des valeurs de restriction par défaut et des numéros de restriction.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="4f8d8-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="4f8d8-134">Example</span></span>  
 <span data-ttu-id="4f8d8-135">Les exemples suivants montrent comment utiliser le <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> méthode du fournisseur de données .NET Framework pour SQL Server <xref:System.Data.SqlClient.SqlConnection> classe à récupérer les informations de schéma sur toutes les tables contenues dans le **AdventureWorks**exemple de base de données, et pour restreindre les informations retournées exclusivement aux tables dans le schéma « Sales » :</span><span class="sxs-lookup"><span data-stu-id="4f8d8-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="4f8d8-136">Restrictions de schéma SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f8d8-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="4f8d8-137">Les tableaux suivants énumèrent les restrictions pour les collections de schémas SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="4f8d8-138">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4f8d8-138">Users</span></span>  
  
|<span data-ttu-id="4f8d8-139">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-139">Restriction Name</span></span>|<span data-ttu-id="4f8d8-140">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-140">Parameter Name</span></span>|<span data-ttu-id="4f8d8-141">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-141">Restriction Default</span></span>|<span data-ttu-id="4f8d8-142">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-143">User_Name</span></span>|@Name|<span data-ttu-id="4f8d8-144">name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-144">name</span></span>|<span data-ttu-id="4f8d8-145">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="4f8d8-146">Bases de données</span><span class="sxs-lookup"><span data-stu-id="4f8d8-146">Databases</span></span>  
  
|<span data-ttu-id="4f8d8-147">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-147">Restriction Name</span></span>|<span data-ttu-id="4f8d8-148">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-148">Parameter Name</span></span>|<span data-ttu-id="4f8d8-149">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-149">Restriction Default</span></span>|<span data-ttu-id="4f8d8-150">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-151">Name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-151">Name</span></span>|@Name|<span data-ttu-id="4f8d8-152">Name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-152">Name</span></span>|<span data-ttu-id="4f8d8-153">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="4f8d8-154">Tables</span><span class="sxs-lookup"><span data-stu-id="4f8d8-154">Tables</span></span>  
  
|<span data-ttu-id="4f8d8-155">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-155">Restriction Name</span></span>|<span data-ttu-id="4f8d8-156">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-156">Parameter Name</span></span>|<span data-ttu-id="4f8d8-157">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-157">Restriction Default</span></span>|<span data-ttu-id="4f8d8-158">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-159">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-159">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-160">TABLE_CATALOG</span></span>|<span data-ttu-id="4f8d8-161">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-161">1</span></span>|  
|<span data-ttu-id="4f8d8-162">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-162">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="4f8d8-164">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-164">2</span></span>|  
|<span data-ttu-id="4f8d8-165">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-165">Table</span></span>|@Name|<span data-ttu-id="4f8d8-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-166">TABLE_NAME</span></span>|<span data-ttu-id="4f8d8-167">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-167">3</span></span>|  
|<span data-ttu-id="4f8d8-168">TableType</span><span class="sxs-lookup"><span data-stu-id="4f8d8-168">TableType</span></span>|@TableType|<span data-ttu-id="4f8d8-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4f8d8-169">TABLE_TYPE</span></span>|<span data-ttu-id="4f8d8-170">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="4f8d8-171">Columns</span><span class="sxs-lookup"><span data-stu-id="4f8d8-171">Columns</span></span>  
  
|<span data-ttu-id="4f8d8-172">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-172">Restriction Name</span></span>|<span data-ttu-id="4f8d8-173">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-173">Parameter Name</span></span>|<span data-ttu-id="4f8d8-174">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-174">Restriction Default</span></span>|<span data-ttu-id="4f8d8-175">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-176">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-176">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-177">TABLE_CATALOG</span></span>|<span data-ttu-id="4f8d8-178">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-178">1</span></span>|  
|<span data-ttu-id="4f8d8-179">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-179">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="4f8d8-181">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-181">2</span></span>|  
|<span data-ttu-id="4f8d8-182">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-182">Table</span></span>|@Table|<span data-ttu-id="4f8d8-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-183">TABLE_NAME</span></span>|<span data-ttu-id="4f8d8-184">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-184">3</span></span>|  
|<span data-ttu-id="4f8d8-185">Colonne</span><span class="sxs-lookup"><span data-stu-id="4f8d8-185">Column</span></span>|@Column|<span data-ttu-id="4f8d8-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-186">COLUMN_NAME</span></span>|<span data-ttu-id="4f8d8-187">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="4f8d8-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="4f8d8-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="4f8d8-189">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-189">Restriction Name</span></span>|<span data-ttu-id="4f8d8-190">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-190">Parameter Name</span></span>|<span data-ttu-id="4f8d8-191">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-191">Restriction Default</span></span>|<span data-ttu-id="4f8d8-192">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-193">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-193">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-194">TABLE_CATALOG</span></span>|<span data-ttu-id="4f8d8-195">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-195">1</span></span>|  
|<span data-ttu-id="4f8d8-196">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-196">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="4f8d8-198">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-198">2</span></span>|  
|<span data-ttu-id="4f8d8-199">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-199">Table</span></span>|@Table|<span data-ttu-id="4f8d8-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-200">TABLE_NAME</span></span>|<span data-ttu-id="4f8d8-201">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-201">3</span></span>|  
|<span data-ttu-id="4f8d8-202">Colonne</span><span class="sxs-lookup"><span data-stu-id="4f8d8-202">Column</span></span>|@Column|<span data-ttu-id="4f8d8-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-203">COLUMN_NAME</span></span>|<span data-ttu-id="4f8d8-204">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="4f8d8-205">Vues</span><span class="sxs-lookup"><span data-stu-id="4f8d8-205">Views</span></span>  
  
|<span data-ttu-id="4f8d8-206">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-206">Restriction Name</span></span>|<span data-ttu-id="4f8d8-207">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-207">Parameter Name</span></span>|<span data-ttu-id="4f8d8-208">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-208">Restriction Default</span></span>|<span data-ttu-id="4f8d8-209">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-210">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-210">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-211">TABLE_CATALOG</span></span>|<span data-ttu-id="4f8d8-212">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-212">1</span></span>|  
|<span data-ttu-id="4f8d8-213">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-213">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="4f8d8-215">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-215">2</span></span>|  
|<span data-ttu-id="4f8d8-216">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-216">Table</span></span>|@Table|<span data-ttu-id="4f8d8-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-217">TABLE_NAME</span></span>|<span data-ttu-id="4f8d8-218">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="4f8d8-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="4f8d8-219">ViewColumns</span></span>  
  
|<span data-ttu-id="4f8d8-220">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-220">Restriction Name</span></span>|<span data-ttu-id="4f8d8-221">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-221">Parameter Name</span></span>|<span data-ttu-id="4f8d8-222">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-222">Restriction Default</span></span>|<span data-ttu-id="4f8d8-223">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-224">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-224">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-225">VIEW_CATALOG</span></span>|<span data-ttu-id="4f8d8-226">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-226">1</span></span>|  
|<span data-ttu-id="4f8d8-227">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-227">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="4f8d8-229">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-229">2</span></span>|  
|<span data-ttu-id="4f8d8-230">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-230">Table</span></span>|@Table|<span data-ttu-id="4f8d8-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-231">VIEW_NAME</span></span>|<span data-ttu-id="4f8d8-232">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-232">3</span></span>|  
|<span data-ttu-id="4f8d8-233">Colonne</span><span class="sxs-lookup"><span data-stu-id="4f8d8-233">Column</span></span>|@Column|<span data-ttu-id="4f8d8-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-234">COLUMN_NAME</span></span>|<span data-ttu-id="4f8d8-235">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="4f8d8-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="4f8d8-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="4f8d8-237">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-237">Restriction Name</span></span>|<span data-ttu-id="4f8d8-238">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-238">Parameter Name</span></span>|<span data-ttu-id="4f8d8-239">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-239">Restriction Default</span></span>|<span data-ttu-id="4f8d8-240">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-241">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-241">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="4f8d8-243">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-243">1</span></span>|  
|<span data-ttu-id="4f8d8-244">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-244">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="4f8d8-246">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-246">2</span></span>|  
|<span data-ttu-id="4f8d8-247">Name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-247">Name</span></span>|@Name|<span data-ttu-id="4f8d8-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="4f8d8-249">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-249">3</span></span>|  
|<span data-ttu-id="4f8d8-250">Paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-250">Parameter</span></span>|@Parameter|<span data-ttu-id="4f8d8-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-251">PARAMETER_NAME</span></span>|<span data-ttu-id="4f8d8-252">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="4f8d8-253">Procédures</span><span class="sxs-lookup"><span data-stu-id="4f8d8-253">Procedures</span></span>  
  
|<span data-ttu-id="4f8d8-254">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-254">Restriction Name</span></span>|<span data-ttu-id="4f8d8-255">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-255">Parameter Name</span></span>|<span data-ttu-id="4f8d8-256">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-256">Restriction Default</span></span>|<span data-ttu-id="4f8d8-257">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-258">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-258">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="4f8d8-260">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-260">1</span></span>|  
|<span data-ttu-id="4f8d8-261">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-261">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="4f8d8-263">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-263">2</span></span>|  
|<span data-ttu-id="4f8d8-264">Name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-264">Name</span></span>|@Name|<span data-ttu-id="4f8d8-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="4f8d8-266">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-266">3</span></span>|  
|<span data-ttu-id="4f8d8-267">Type</span><span class="sxs-lookup"><span data-stu-id="4f8d8-267">Type</span></span>|@Type|<span data-ttu-id="4f8d8-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4f8d8-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="4f8d8-269">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="4f8d8-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="4f8d8-270">IndexColumns</span></span>  
  
|<span data-ttu-id="4f8d8-271">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-271">Restriction Name</span></span>|<span data-ttu-id="4f8d8-272">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-272">Parameter Name</span></span>|<span data-ttu-id="4f8d8-273">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-273">Restriction Default</span></span>|<span data-ttu-id="4f8d8-274">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-275">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-275">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="4f8d8-276">db_name()</span></span>|<span data-ttu-id="4f8d8-277">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-277">1</span></span>|  
|<span data-ttu-id="4f8d8-278">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-278">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="4f8d8-279">user_name()</span></span>|<span data-ttu-id="4f8d8-280">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-280">2</span></span>|  
|<span data-ttu-id="4f8d8-281">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-281">Table</span></span>|@Table|<span data-ttu-id="4f8d8-282">o.name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-282">o.name</span></span>|<span data-ttu-id="4f8d8-283">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-283">3</span></span>|  
|<span data-ttu-id="4f8d8-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="4f8d8-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="4f8d8-285">x.name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-285">x.name</span></span>|<span data-ttu-id="4f8d8-286">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-286">4</span></span>|  
|<span data-ttu-id="4f8d8-287">Colonne</span><span class="sxs-lookup"><span data-stu-id="4f8d8-287">Column</span></span>|@Column|<span data-ttu-id="4f8d8-288">c.name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-288">c.name</span></span>|<span data-ttu-id="4f8d8-289">5</span><span class="sxs-lookup"><span data-stu-id="4f8d8-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="4f8d8-290">Index</span><span class="sxs-lookup"><span data-stu-id="4f8d8-290">Indexes</span></span>  
  
|<span data-ttu-id="4f8d8-291">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-291">Restriction Name</span></span>|<span data-ttu-id="4f8d8-292">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-292">Parameter Name</span></span>|<span data-ttu-id="4f8d8-293">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-293">Restriction Default</span></span>|<span data-ttu-id="4f8d8-294">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-295">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-295">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="4f8d8-296">db_name()</span></span>|<span data-ttu-id="4f8d8-297">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-297">1</span></span>|  
|<span data-ttu-id="4f8d8-298">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-298">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="4f8d8-299">user_name()</span></span>|<span data-ttu-id="4f8d8-300">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-300">2</span></span>|  
|<span data-ttu-id="4f8d8-301">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-301">Table</span></span>|@Table|<span data-ttu-id="4f8d8-302">o.name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-302">o.name</span></span>|<span data-ttu-id="4f8d8-303">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="4f8d8-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="4f8d8-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="4f8d8-305">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-305">Restriction Name</span></span>|<span data-ttu-id="4f8d8-306">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-306">Parameter Name</span></span>|<span data-ttu-id="4f8d8-307">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-307">Restriction Default</span></span>|<span data-ttu-id="4f8d8-308">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="4f8d8-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-310">assemblies.name</span></span>|<span data-ttu-id="4f8d8-311">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-311">1</span></span>|  
|<span data-ttu-id="4f8d8-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-312">udt_name</span></span>|@UDTName|<span data-ttu-id="4f8d8-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="4f8d8-313">types.assembly_class</span></span>|<span data-ttu-id="4f8d8-314">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="4f8d8-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="4f8d8-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="4f8d8-316">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-316">Restriction Name</span></span>|<span data-ttu-id="4f8d8-317">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-317">Parameter Name</span></span>|<span data-ttu-id="4f8d8-318">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-318">Restriction Default</span></span>|<span data-ttu-id="4f8d8-319">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-320">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-320">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="4f8d8-322">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-322">1</span></span>|  
|<span data-ttu-id="4f8d8-323">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-323">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="4f8d8-325">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-325">2</span></span>|  
|<span data-ttu-id="4f8d8-326">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-326">Table</span></span>|@Table|<span data-ttu-id="4f8d8-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-327">TABLE_NAME</span></span>|<span data-ttu-id="4f8d8-328">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-328">3</span></span>|  
|<span data-ttu-id="4f8d8-329">Name</span><span class="sxs-lookup"><span data-stu-id="4f8d8-329">Name</span></span>|@Name|<span data-ttu-id="4f8d8-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="4f8d8-331">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="4f8d8-332">Restrictions de schéma SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="4f8d8-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="4f8d8-333">Les tableaux suivants répertorient les restrictions pour les collections de schémas SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="4f8d8-334">Ces restrictions s'appliquent à partir de la version 3.5 SP1 de .NET Framework et SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="4f8d8-335">Elles ne sont pas prises en charge dans les versions précédentes de .NET Framework et SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f8d8-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="4f8d8-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="4f8d8-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="4f8d8-337">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-337">Restriction Name</span></span>|<span data-ttu-id="4f8d8-338">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-338">Parameter Name</span></span>|<span data-ttu-id="4f8d8-339">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-339">Restriction Default</span></span>|<span data-ttu-id="4f8d8-340">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-341">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-341">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-342">TABLE_CATALOG</span></span>|<span data-ttu-id="4f8d8-343">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-343">1</span></span>|  
|<span data-ttu-id="4f8d8-344">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-344">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="4f8d8-346">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-346">2</span></span>|  
|<span data-ttu-id="4f8d8-347">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-347">Table</span></span>|@Table|<span data-ttu-id="4f8d8-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-348">TABLE_NAME</span></span>|<span data-ttu-id="4f8d8-349">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="4f8d8-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="4f8d8-350">AllColumns</span></span>  
  
|<span data-ttu-id="4f8d8-351">Nom de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-351">Restriction Name</span></span>|<span data-ttu-id="4f8d8-352">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="4f8d8-352">Parameter Name</span></span>|<span data-ttu-id="4f8d8-353">Valeur par défaut de la restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-353">Restriction Default</span></span>|<span data-ttu-id="4f8d8-354">Numéro de restriction</span><span class="sxs-lookup"><span data-stu-id="4f8d8-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="4f8d8-355">Catalogue</span><span class="sxs-lookup"><span data-stu-id="4f8d8-355">Catalog</span></span>|@Catalog|<span data-ttu-id="4f8d8-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4f8d8-356">TABLE_CATALOG</span></span>|<span data-ttu-id="4f8d8-357">1</span><span class="sxs-lookup"><span data-stu-id="4f8d8-357">1</span></span>|  
|<span data-ttu-id="4f8d8-358">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="4f8d8-358">Owner</span></span>|@Owner|<span data-ttu-id="4f8d8-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="4f8d8-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="4f8d8-360">2</span><span class="sxs-lookup"><span data-stu-id="4f8d8-360">2</span></span>|  
|<span data-ttu-id="4f8d8-361">Table</span><span class="sxs-lookup"><span data-stu-id="4f8d8-361">Table</span></span>|@Table|<span data-ttu-id="4f8d8-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-362">TABLE_NAME</span></span>|<span data-ttu-id="4f8d8-363">3</span><span class="sxs-lookup"><span data-stu-id="4f8d8-363">3</span></span>|  
|<span data-ttu-id="4f8d8-364">Colonne</span><span class="sxs-lookup"><span data-stu-id="4f8d8-364">Column</span></span>|@Column|<span data-ttu-id="4f8d8-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="4f8d8-365">COLUMN_NAME</span></span>|<span data-ttu-id="4f8d8-366">4</span><span class="sxs-lookup"><span data-stu-id="4f8d8-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f8d8-367">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f8d8-367">See Also</span></span>  
 [<span data-ttu-id="4f8d8-368">Fournisseurs managés ADO.NET et centre de développement DataSet</span><span class="sxs-lookup"><span data-stu-id="4f8d8-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

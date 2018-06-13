---
title: Guide pratique pour réorganiser les champs d’un fichier délimité (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 4b7485ff80ef02b7d12980d8ede29cf926027f93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326704"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a><span data-ttu-id="2bbf5-102">Guide pratique pour réorganiser les champs d’un fichier délimité (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2bbf5-102">How to: Reorder the Fields of a Delimited File (LINQ) (C#)</span></span>
<span data-ttu-id="2bbf5-103">Un fichier de valeurs séparées par des virgules (CSV) est un fichier texte qui est souvent utilisé pour stocker des données de feuille de calcul ou autres données tabulaires qui sont représentées sous forme de lignes et de colonnes.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="2bbf5-104">En utilisant la méthode <xref:System.String.Split%2A> pour séparer les champs, il est très facile d’interroger et de manipuler des fichiers CSV à l’aide de LINQ.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="2bbf5-105">En fait, la même technique peut servir à réorganiser les sections de n’importe quelle ligne de texte structurée et ne se limite donc pas aux fichiers CSV.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="2bbf5-106">Dans l’exemple suivant, supposons que les trois colonnes représentent le nom, le prénom et l’ID de l’étudiant.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="2bbf5-107">Les champs sont classés par ordre alphabétique, selon le nom des étudiants.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="2bbf5-108">La requête produit une séquence dans laquelle la colonne ID apparaît en premier, suivie d’une deuxième colonne qui comprend à la fois le prénom et le nom de l’étudiant.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="2bbf5-109">Les lignes sont réorganisées d’après le champ ID.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="2bbf5-110">Les résultats sont enregistrés dans un nouveau fichier et les données d’origine ne sont pas modifiées.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="2bbf5-111">Pour créer le fichier de données</span><span class="sxs-lookup"><span data-stu-id="2bbf5-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="2bbf5-112">Copiez les lignes suivantes dans un fichier texte nommé spreadsheet1.csv.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="2bbf5-113">Enregistrez le fichier dans votre dossier de projet.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-113">Save the file in your project folder.</span></span>  
  
    ```  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a><span data-ttu-id="2bbf5-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="2bbf5-114">Example</span></span>  
  
```csharp  
class CSVFiles  
{  
    static void Main(string[] args)  
    {  
        // Create the IEnumerable data source  
        string[] lines = System.IO.File.ReadAllLines(@"../../../spreadsheet1.csv");  
  
        // Create the query. Put field 2 first, then  
        // reverse and combine fields 0 and 1 from the old field  
        IEnumerable<string> query =  
            from line in lines  
            let x = line.Split(',')  
            orderby x[2]  
            select x[2] + ", " + (x[1] + " " + x[0]);  
  
        // Execute the query and write out the new file. Note that WriteAllLines  
        // takes a string[], so ToArray is called on the query.  
        System.IO.File.WriteAllLines(@"../../../spreadsheet2.csv", query.ToArray());  
  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output to spreadsheet2.csv:  
111, Svetlana Omelchenko  
112, Claire O'Donnell  
113, Sven Mortensen  
114, Cesar Garcia  
115, Debra Garcia  
116, Fadi Fakhouri  
117, Hanying Feng  
118, Hugo Garcia  
119, Lance Tucker  
120, Terry Adams  
121, Eugene Zabokritski  
122, Michael Tucker  
 */  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2bbf5-115">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="2bbf5-115">Compiling the Code</span></span>  
 <span data-ttu-id="2bbf5-116">Créez un projet qui cible le .NET Framework version 3.5 ou version ultérieure, avec une référence à System.Core.dll et des directives `using` pour les espaces de noms System.Linq et System.IO.</span><span class="sxs-lookup"><span data-stu-id="2bbf5-116">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbf5-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2bbf5-117">See Also</span></span>  
 [<span data-ttu-id="2bbf5-118">LINQ et chaînes (C#)</span><span class="sxs-lookup"><span data-stu-id="2bbf5-118">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="2bbf5-119">LINQ et répertoires de fichiers (C#)</span><span class="sxs-lookup"><span data-stu-id="2bbf5-119">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)  
 [<span data-ttu-id="2bbf5-120">Guide pratique : générer du code XML à partir de fichiers CSV</span><span class="sxs-lookup"><span data-stu-id="2bbf5-120">How to: Generate XML from CSV Files</span></span>](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)

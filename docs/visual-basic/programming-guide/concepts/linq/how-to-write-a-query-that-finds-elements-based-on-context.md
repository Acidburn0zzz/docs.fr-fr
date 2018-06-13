---
title: 'Comment : écrire une requête qui recherche des éléments selon le contexte (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
ms.openlocfilehash: a16f591fc08e8822059bae2ee07d96af575059bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645679"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a><span data-ttu-id="22c1a-102">Comment : écrire une requête qui recherche des éléments selon le contexte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22c1a-102">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>
<span data-ttu-id="22c1a-103">Parfois, vous devez écrire une requête qui sélectionne des éléments en fonction de leur contexte.</span><span class="sxs-lookup"><span data-stu-id="22c1a-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="22c1a-104">Vous souhaiterez peut-être filtrer en fonction des éléments frères qui précèdent ou qui suivent.</span><span class="sxs-lookup"><span data-stu-id="22c1a-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="22c1a-105">Vous souhaiterez peut-être filtrer en fonction des éléments enfants ou ancêtres.</span><span class="sxs-lookup"><span data-stu-id="22c1a-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="22c1a-106">Vous pouvez pour cela écrire une requête et utiliser ses résultats dans la clause `where`.</span><span class="sxs-lookup"><span data-stu-id="22c1a-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="22c1a-107">Si vous devez tout d'abord tester par rapport à la valeur Null, puis tester la valeur, il est plus pratique de créer la requête dans une clause `let`, puis d'utiliser les résultats dans la clause `where`.</span><span class="sxs-lookup"><span data-stu-id="22c1a-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22c1a-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="22c1a-108">Example</span></span>  
 <span data-ttu-id="22c1a-109">L'exemple suivant sélectionne tous les éléments `p` qui sont suivis immédiatement d'un élément `ul`.</span><span class="sxs-lookup"><span data-stu-id="22c1a-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```vb  
Dim doc As XElement = _  
    <Root>  
        <p id='1'/>  
        <ul>abc</ul>  
        <Child>  
            <p id='2'/>  
            <notul/>  
            <p id='3'/>  
            <ul>def</ul>  
            <p id='4'/>  
        </Child>  
        <Child>  
            <p id='5'/>  
            <notul/>  
            <p id='6'/>  
            <ul>abc</ul>  
            <p id='7'/>  
        </Child>  
    </Root>  
  
Dim items As IEnumerable(Of XElement) = _  
    From e In doc...<p> _  
    Let z = e.ElementsAfterSelf().FirstOrDefault() _  
    Where z IsNot Nothing AndAlso z.Name.LocalName = "ul" _  
    Select e  
  
For Each e As XElement In items  
    Console.WriteLine("id = {0}", e.@<id>)  
Next  
```  
  
 <span data-ttu-id="22c1a-110">Ce code génère la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="22c1a-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="22c1a-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="22c1a-111">Example</span></span>  
 <span data-ttu-id="22c1a-112">L'exemple suivant illustre la même requête pour du code XML qui est dans un espace de noms.</span><span class="sxs-lookup"><span data-stu-id="22c1a-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="22c1a-113">Pour plus d’informations, consultez [utilisation des espaces de noms XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="22c1a-113">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim doc As XElement = _  
            <Root>  
                <p id='1'/>  
                <ul>abc</ul>  
                <Child>  
                    <p id='2'/>  
                    <notul/>  
                    <p id='3'/>  
                    <ul>def</ul>  
                    <p id='4'/>  
                </Child>  
                <Child>  
                    <p id='5'/>  
                    <notul/>  
                    <p id='6'/>  
                    <ul>abc</ul>  
                    <p id='7'/>  
                </Child>  
            </Root>  
  
        Dim items As IEnumerable(Of XElement) = _  
            From e In doc...<p> _  
            Let z = e.ElementsAfterSelf().FirstOrDefault() _  
            Where z IsNot Nothing AndAlso z.Name = GetXmlNamespace().GetName("ul") _  
            Select e  
  
        For Each e As XElement In items  
            Console.WriteLine("id = {0}", e.@<id>)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="22c1a-114">Ce code génère la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="22c1a-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="22c1a-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22c1a-115">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Parse%2A>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
 <xref:System.Linq.Enumerable.FirstOrDefault%2A>  
 [<span data-ttu-id="22c1a-116">Requêtes de base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22c1a-116">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

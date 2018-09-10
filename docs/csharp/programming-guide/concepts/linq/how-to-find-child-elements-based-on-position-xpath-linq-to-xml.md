---
title: Guide pratique pour rechercher des éléments enfants en fonction de leur position (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: e35bb269-ec86-4c96-8321-12491a0eb2c3
ms.openlocfilehash: 5d62418fe6d89c8dc5c7ddb4975404f1a7e0aa2d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517091"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-c"></a><span data-ttu-id="03ead-102">Guide pratique pour rechercher des éléments enfants en fonction de leur position (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="03ead-102">How to: Find Child Elements Based on Position (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="03ead-103">Parfois, vous souhaitez rechercher des éléments en fonction de leur position.</span><span class="sxs-lookup"><span data-stu-id="03ead-103">Sometimes you want to find elements based on their position.</span></span> <span data-ttu-id="03ead-104">Vous pourriez souhaiter rechercher le deuxième élément, ou les troisième, quatrième et cinquième éléments.</span><span class="sxs-lookup"><span data-stu-id="03ead-104">You might want to find the second element, or you might want to find the third through the fifth element.</span></span>  
  
 <span data-ttu-id="03ead-105">L'expression XPath est la suivante :</span><span class="sxs-lookup"><span data-stu-id="03ead-105">The XPath expression is:</span></span>  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 <span data-ttu-id="03ead-106">Il existe deux approches pour l'écriture de cette requête [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] d'une manière différée.</span><span class="sxs-lookup"><span data-stu-id="03ead-106">There are two approaches to writing this [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query in a lazy way.</span></span> <span data-ttu-id="03ead-107">Vous pouvez utiliser les opérateurs <xref:System.Linq.Enumerable.Skip%2A> et <xref:System.Linq.Enumerable.Take%2A>, ou vous pouvez utiliser la surcharge <xref:System.Linq.Enumerable.Where%2A> qui prend un index.</span><span class="sxs-lookup"><span data-stu-id="03ead-107">You can use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> operators, or you can use the <xref:System.Linq.Enumerable.Where%2A> overload that takes an index.</span></span> <span data-ttu-id="03ead-108">Lorsque vous utilisez la surcharge <xref:System.Linq.Enumerable.Where%2A>, vous utilisez une expression lambda qui prend deux arguments.</span><span class="sxs-lookup"><span data-stu-id="03ead-108">When you use the <xref:System.Linq.Enumerable.Where%2A> overload, you use a lambda expression that takes two arguments.</span></span> <span data-ttu-id="03ead-109">L'exemple suivant illustre les deux méthodes de sélection basée sur la position.</span><span class="sxs-lookup"><span data-stu-id="03ead-109">The following example shows both methods of selecting based on position.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03ead-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="03ead-110">Example</span></span>  
 <span data-ttu-id="03ead-111">Cet exemple recherche les deuxième, troisième et quatrième éléments `Test`.</span><span class="sxs-lookup"><span data-stu-id="03ead-111">This example finds the second through the fourth `Test` element.</span></span> <span data-ttu-id="03ead-112">Le résultat est une collection d’éléments.</span><span class="sxs-lookup"><span data-stu-id="03ead-112">The result is a collection of elements.</span></span>  
  
 <span data-ttu-id="03ead-113">Cet exemple utilise le document XML suivant : [Exemple de fichier XML : Configuration test (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="03ead-113">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement testCfg = XElement.Load("TestConfig.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    testCfg  
    .Elements("Test")  
    .Skip(1)  
    .Take(3);  
  
// LINQ to XML query  
IEnumerable<XElement> list2 =  
    testCfg  
    .Elements("Test")  
    .Where((el, idx) => idx >= 1 && idx <= 3);  
  
// XPath expression  
IEnumerable<XElement> list3 =  
  testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]");  
  
if (list1.Count() == list2.Count() &&  
    list1.Count() == list3.Count() &&  
    list1.Intersect(list2).Count() == list1.Count() &&  
    list1.Intersect(list3).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="03ead-114">Cet exemple génère la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="03ead-114">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03ead-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03ead-115">See Also</span></span>

- [<span data-ttu-id="03ead-116">LINQ to XML pour les utilisateurs XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="03ead-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

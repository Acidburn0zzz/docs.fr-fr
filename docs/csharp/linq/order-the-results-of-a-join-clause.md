---
title: Classer les résultats d'une clause join (LINQ en C#)
description: Découvrez comment classer les résultats d'une clause join LINQ en C#.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: 13cd6cb202cf67def17310db6d98e368ce837646
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516984"
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="568d4-103">Classer les résultats d’une clause join</span><span class="sxs-lookup"><span data-stu-id="568d4-103">Order the results of a join clause</span></span>

<span data-ttu-id="568d4-104">Cet exemple montre comment classer les résultats d’une opération de jointure.</span><span class="sxs-lookup"><span data-stu-id="568d4-104">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="568d4-105">Notez que le classement est effectué après la jointure.</span><span class="sxs-lookup"><span data-stu-id="568d4-105">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="568d4-106">Vous pouvez utiliser une clause `orderby` avec une ou plusieurs séquences sources avant la jointure, mais cette pratique est généralement déconseillée.</span><span class="sxs-lookup"><span data-stu-id="568d4-106">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="568d4-107">Certains fournisseurs LINQ ne conservent pas ce classement après la jointure.</span><span class="sxs-lookup"><span data-stu-id="568d4-107">Some LINQ providers might not preserve that ordering after the join.</span></span>

## <a name="example"></a><span data-ttu-id="568d4-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="568d4-108">Example</span></span>

<span data-ttu-id="568d4-109">Cette requête crée une jointure groupée, puis trie les groupes en fonction de l’élément de catégorie, qui est encore dans la portée.</span><span class="sxs-lookup"><span data-stu-id="568d4-109">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="568d4-110">À l’intérieur de l’initialiseur de type anonyme, une sous-requête classe tous les éléments correspondants de la séquence de produits.</span><span class="sxs-lookup"><span data-stu-id="568d4-110">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a><span data-ttu-id="568d4-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="568d4-111">See also</span></span>

- [<span data-ttu-id="568d4-112">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="568d4-112">Language Integrated Query (LINQ)</span></span>](index.md)  
- [<span data-ttu-id="568d4-113">orderby, clause</span><span class="sxs-lookup"><span data-stu-id="568d4-113">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
- [<span data-ttu-id="568d4-114">join, clause</span><span class="sxs-lookup"><span data-stu-id="568d4-114">join clause</span></span>](../language-reference/keywords/join-clause.md)  
---
title: Effectuer des jointures externes gauches
description: Guide pratique pour effectuer des jointures externes gauches.
ms.date: 12/1/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: aacab1ac6f4ab2c10b393cf0b2c578a13d9b9306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284275"
---
# <a name="perform-left-outer-joins"></a>Effectuer des jointures externes gauches
Une jointure externe gauche est une jointure dans laquelle chaque élément de la première collection est retourné, qu’elle ait ou non des éléments corrélés dans la deuxième collection. Vous pouvez utiliser LINQ pour effectuer une jointure externe gauche en appelant la méthode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> sur les résultats d’une jointure groupée.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser la méthode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> sur les résultats d’une jointure groupée pour effectuer une jointure externe gauche.  
  
 Pour créer une jointure externe gauche entre deux collections, la première étape consiste à effectuer une jointure interne à l’aide d’une jointure groupée. (Pour savoir comment faire, consultez [Effectuer des jointures internes](perform-inner-joins.md).) Dans cet exemple, la liste des objets `Person` est jointe par une jointure interne à la liste des objets `Pet` sur la base d’un objet `Person` qui correspond à `Pet.Owner`.  
  
 La deuxième étape consiste à inclure tous les éléments de la première collection (celle de gauche) dans le jeu de résultats, y compris les éléments sans correspondance dans la collection de droite. Pour cela, appelez <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> sur chaque séquence d’éléments correspondants de la jointure groupée. Dans cet exemple, la méthode <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> est appelée sur chaque séquence d’objets `Pet` correspondants. La méthode retourne une collection qui contient uniquement une valeur par défaut si la séquence des objets `Pet` correspondants à un objet `Person` est vide, ce qui garantit que chaque objet `Person` est représenté dans la collection de résultats.  
  
> [!NOTE]
>  La valeur par défaut pour un type référence est `null`. L’exemple recherche donc une référence null avant d’accéder à chaque élément de chaque collection `Pet`.  
  
 [!code-csharp[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]  
 
## <a name="see-also"></a>Voir aussi  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [Effectuer des jointures internes](perform-inner-joins.md)  
 [Effectuer des jointures groupées](perform-grouped-joins.md)  
 [Types anonymes](../programming-guide/classes-and-structs/anonymous-types.md)  
 

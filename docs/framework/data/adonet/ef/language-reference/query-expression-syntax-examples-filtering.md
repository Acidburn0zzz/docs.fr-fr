---
title: 'Exemples de syntaxe d’expression de requête : Filtrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c27cb89c-1c1d-4988-9f38-950eda3cb275
ms.openlocfilehash: eb1680ba8ca2fab5511dc20c94ad997ef04974fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134548"
---
# <a name="query-expression-syntax-examples-filtering"></a>Exemples de syntaxe d’expression de requête : Filtrage
Les exemples de cette rubrique montrent comment utiliser le `Where` et `Where…Contains` méthodes permettant d’interroger la [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) à l’aide de la syntaxe d’expression de requête. Notez que, dans lequel...`Contains` ne peut pas être utilisé dans le cadre d’un [requête compilée](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).  
  
 Le modèle de vente AdventureWorks Sales Model utilisé dans ces exemples est construit à partir des tables Contact, Address, Product, SalesOrderHeader et SalesOrderDetail de l'exemple de base de données AdventureWorks.  
  
 Les exemples de cette rubrique utilisent les éléments suivants `using` / `Imports` instructions :  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a>Où  
  
### <a name="example"></a>Exemple  
 L'exemple suivant retourne toutes les commandes en ligne.  
  
 [!code-csharp[DP L2E Examples#Where1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1)]
 [!code-vb[DP L2E Examples#Where1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1)]  
  
### <a name="example"></a>Exemple  
 L'exemple suivant retourne les commandes où la quantité commandée est supérieure à 2 et inférieure à 6.  
  
 [!code-csharp[DP L2E Examples#Where2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2)]
 [!code-vb[DP L2E Examples#Where2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2)]  
  
### <a name="example"></a>Exemple  
 L'exemple suivant retourne tous les produits de couleur rouge.  
  
 [!code-csharp[DP L2E Examples#Where3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3)]
 [!code-vb[DP L2E Examples#Where3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3)]  
  
### <a name="example"></a>Exemple  
 L'exemple ci-dessous utilise la méthode `Where` pour rechercher des commandes qui ont été passées après le 1er décembre 2003, puis utilise la propriété de navigation `order.SalesOrderDetail` pour obtenir les détails de chaque commande.  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="wherecontains"></a>Where…Contains  
  
### <a name="example"></a>Exemple  
 L'exemple ci-dessous utilise un tableau dans le cadre d'une clause `Where…Contains` pour rechercher tous les produits qui ont un `ProductModelID` qui correspond à une valeur dans le tableau.  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#1)]
 [!code-vb[DP L2E ArraysAndListsInQueries#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#1)]  
  
> [!NOTE]
>  Dans le cadre du prédicat dans une clause `Where…Contains`, vous pouvez utiliser un <xref:System.Array>, un <xref:System.Collections.Generic.List%601> ou une collection de type quelconque qui implémente l’interface <xref:System.Collections.Generic.IEnumerable%601>. Vous pouvez également déclarer et initialiser une collection dans une requête LINQ to Entities. Pour plus d'informations, consultez l'exemple suivant.  
  
### <a name="example"></a>Exemple  
 L'exemple ci-dessous déclare et initialise des tableaux dans une clause `Where…Contains` pour rechercher tous les produits qui ont un `ProductModelID` ou un `Size` correspondant aux valeurs dans les tableaux.  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#2)]
 [!code-vb[DP L2E ArraysAndListsInQueries#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Voir aussi

- [Requêtes dans LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)

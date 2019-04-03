---
title: Opérations d’agrégation (C#)
ms.date: 07/20/2015
ms.assetid: 6fc035e5-7639-48b8-bc7f-b093dd31b039
ms.openlocfilehash: 151332964b4efd495acff5d8763dfab5f380ee6c
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675625"
---
# <a name="aggregation-operations-c"></a>Opérations d’agrégation (C#)
Une opération d’agrégation calcule une valeur unique à partir d’une collection de valeurs. Par exemple, une opération d'agrégation peut être le calcul de la température quotidienne moyenne à partir des valeurs de température quotidiennes relevées sur un mois.  
  
 L’illustration suivante montre les résultats de deux opérations d’agrégation différentes sur une séquence de nombres. La première opération additionne les nombres. La deuxième opération retourne la valeur maximale dans la séquence.  
  
 ![Illustration qui montre des opérations d’agrégation LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 Les méthodes d’opérateurs de requête standard qui effectuent des opérations d’agrégation sont répertoriées dans la section suivante.  
  
## <a name="methods"></a>Méthodes  
  
|Nom de la méthode|Description|Syntaxe d'expression de requête C#|Informations complémentaires|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Aggregate|Effectue une opération d’agrégation personnalisée sur les valeurs d’une collection.|Non applicable.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Average|Calcule la valeur moyenne d’une collection de valeurs.|Non applicable.|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Nombre|Compte tous les éléments d’une collection, ou uniquement les éléments basés sur une fonction de prédicat.|Non applicable.|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Compte tous les éléments d’une grande collection, ou uniquement les éléments basés sur une fonction de prédicat.|Non applicable.|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Max|Détermine la valeur maximale dans une collection.|Non applicable.|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Min|Détermine la valeur minimale dans une collection.|Non applicable.|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Sum|Calcule la somme des valeurs d’une collection.|Non applicable.|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Linq>
- [Vue d’ensemble des opérateurs de requête standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Guide pratique pour calculer des valeurs de colonnes dans un fichier texte CSV (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Guide pratique pour rechercher les fichiers les plus volumineux dans une arborescence de répertoires (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)
- [Guide pratique pour rechercher le nombre total d’octets dans un ensemble de dossiers (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)

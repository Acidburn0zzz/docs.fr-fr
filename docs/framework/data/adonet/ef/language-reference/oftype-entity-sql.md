---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: c90950e11cbfca7a49b505c1654d08be504990e1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198135"
---
# <a name="oftype-entity-sql"></a>OFTYPE (Entity SQL)
Retourne une collection d'objets à partir d'une expression de requête d'un type spécifique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Toute expression de requête valide qui retourne une collection d'objets.  
  
 `test_type`  
 Type en fonction duquel tester chaque objet retourné par `expression` . Le type doit être qualifié par un espace de noms.  
  
## <a name="return-value"></a>Valeur de retour  
 Collection d'objets du type `test_type`ou d'un type de base ou dérivé de `test_type`. Si ONLY est spécifié, seules les instances de `test_type` ou une collection vide seront retournées.  
  
## <a name="remarks"></a>Notes  
 Une expression `OFTYPE` spécifie une expression de type émise pour effectuer un test de type sur chaque élément d'une collection.  L'expression `OFTYPE` produit une nouvelle collection du type spécifié ne contenant que les éléments qui étaient équivalents à ce type ou à l'un de ses sous-types.  
  
 Une expression `OFTYPE` est l'abréviation de l'expression de requête suivante :  
  
```  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 Un Manager étant un sous-type d'Employee, l'expression suivante produit à partir d'une collection d'employés (employee) une collection composée uniquement de responsables (manager) :  
  
```  
OfType(employees, NamespaceName.Manager)  
```  
  
 Il est également possible d'effectuer un upcast sur une collection à l'aide du filtre de type :  
  
```  
OfType(executives, NamespaceName.Manager)  
```  
  
 Puisque tous les cadres (executives) sont des responsables, la collection obtenue contient toujours tous les cadres d'origine, même si elle est désormais typée en tant que collection de responsables.  
  
 Le tableau suivant montre le comportement de l'opérateur `OFTYPE` sur certains modèles. Toutes les exceptions sont levées du côté client avant que le fournisseur ne soit appelé :  
  
|Modèle|Comportement|  
|-------------|--------------|  
|OFTYPE(Collection(EntityType), EntityType)|Collection(EntityType)|  
|OFTYPE(Collection(ComplexType), ComplexType)|Exception|  
|OFTYPE(Collection(RowType), RowType)|Exception|  
  
## <a name="example"></a>Exemple  
 La requête [!INCLUDE[esql](../../../../../../includes/esql-md.md)] suivante utilise l'opérateur OFTYPE pour retourner une collection d'objets OnsiteCourse à partir d'une collection d'objets Course. La requête est basée sur le [modèle School](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#OFTYPE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#oftype)]  
  
## <a name="see-also"></a>Voir aussi  
 [Référence Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

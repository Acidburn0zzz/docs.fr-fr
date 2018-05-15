---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: c374261ad3702294f5720edb7881e21ba79d85bc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="2f238-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2f238-102">NAVIGATE (Entity SQL)</span></span>
<span data-ttu-id="2f238-103">Parcourt la relation établie entre des entités.</span><span class="sxs-lookup"><span data-stu-id="2f238-103">Navigates over the relationship established between entities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f238-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2f238-104">Syntax</span></span>  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f238-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="2f238-105">Arguments</span></span>  
 `instance-expresssion`  
 <span data-ttu-id="2f238-106">Instance d'une entité.</span><span class="sxs-lookup"><span data-stu-id="2f238-106">An instance of an entity.</span></span>  
  
 `relationship-type`  
 <span data-ttu-id="2f238-107">Nom du type de relation, à partir du fichier CSDL (Conceptual Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="2f238-107">The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="2f238-108">Le `relationship-type` est qualifié en tant que \<espace de noms >.\< nom de type de relation >.</span><span class="sxs-lookup"><span data-stu-id="2f238-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>  
  
 `to`  
 <span data-ttu-id="2f238-109">Fin de la relation.</span><span class="sxs-lookup"><span data-stu-id="2f238-109">The end of the relationship.</span></span>  
  
 `from`  
 <span data-ttu-id="2f238-110">Début de la relation.</span><span class="sxs-lookup"><span data-stu-id="2f238-110">The beginning of the relationship.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f238-111">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="2f238-111">Return Value</span></span>  
 <span data-ttu-id="2f238-112">Si la cardinalité de la terminaison To est 1, la valeur retournée est `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="2f238-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="2f238-113">Si la cardinalité de la terminaison To est n, la valeur retournée est `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="2f238-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f238-114">Notes</span><span class="sxs-lookup"><span data-stu-id="2f238-114">Remarks</span></span>  
 <span data-ttu-id="2f238-115">Les relations sont des constructions de première classe dans le modèle EDM ( [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="2f238-115">Relationships are first-class constructs in the [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span></span> <span data-ttu-id="2f238-116">Elles peuvent être établies entre plusieurs types d'entités et les utilisateurs peuvent les parcourir d'une terminaison (entité) à l'autre.</span><span class="sxs-lookup"><span data-stu-id="2f238-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="2f238-117">`from` et `to` sont facultatifs à la condition qu'il n'existe aucune ambiguïté au niveau de la résolution des noms dans la relation.</span><span class="sxs-lookup"><span data-stu-id="2f238-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>  
  
 <span data-ttu-id="2f238-118">NAVIGATE est valide dans l'espace O et C.</span><span class="sxs-lookup"><span data-stu-id="2f238-118">NAVIGATE is valid in O and C space.</span></span>  
  
 <span data-ttu-id="2f238-119">Une construction de navigation se présente généralement sous la forme suivante :</span><span class="sxs-lookup"><span data-stu-id="2f238-119">The general form of a navigation construct is the following:</span></span>  
  
 <span data-ttu-id="2f238-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="2f238-120">navigate(`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>  
  
 <span data-ttu-id="2f238-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2f238-121">For example:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="2f238-122">Où OrderCustomer est le `relationship`, et Client et Order sont les terminaisons `to-end` (customer) et `from-end` (order) de la relation.</span><span class="sxs-lookup"><span data-stu-id="2f238-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="2f238-123">Si OrderCustomer était une relation n : 1, le type de résultat de l’expression de navigation est Ref\<client >.</span><span class="sxs-lookup"><span data-stu-id="2f238-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>  
  
 <span data-ttu-id="2f238-124">Voici la même expression sous une forme plus simple :</span><span class="sxs-lookup"><span data-stu-id="2f238-124">The simpler form of this expression is the following:</span></span>  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 <span data-ttu-id="2f238-125">De même, dans une requête de la forme suivante, l’expression de navigation produirait le résultat Collection < Ref\<commande >>.</span><span class="sxs-lookup"><span data-stu-id="2f238-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 <span data-ttu-id="2f238-126">L'expression d'instance doit être un type entity/ref.</span><span class="sxs-lookup"><span data-stu-id="2f238-126">The instance-expression must be an entity/ref type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f238-127">Exemple</span><span class="sxs-lookup"><span data-stu-id="2f238-127">Example</span></span>  
 <span data-ttu-id="2f238-128">La requête Entity SQL suivante utilise l'opérateur NAVIGATE pour parcourir la relation établie entre les types d'entités Address et SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="2f238-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="2f238-129">Cette requête est basée sur le modèle de vente AdventureWorks Sales Model.</span><span class="sxs-lookup"><span data-stu-id="2f238-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2f238-130">Pour compiler et exécuter cette requête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2f238-130">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2f238-131">Suivez la procédure de [Comment : exécuter une requête qui retourne des résultats StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2f238-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="2f238-132">Transmettez à la méthode `ExecuteStructuralTypeQuery` la requête suivante en tant qu'argument :</span><span class="sxs-lookup"><span data-stu-id="2f238-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a><span data-ttu-id="2f238-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f238-133">See Also</span></span>  
 [<span data-ttu-id="2f238-134">Référence Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2f238-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="2f238-135">Comment : parcourir les relations avec l’opérateur Navigate</span><span class="sxs-lookup"><span data-stu-id="2f238-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)

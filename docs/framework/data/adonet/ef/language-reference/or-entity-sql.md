---
title: '|| (OR) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b44934aa0db73f872f0ab27a4c36c5c615855de1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/17/2018
---
# <a name="-or-entity-sql"></a><span data-ttu-id="a5313-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a5313-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="a5313-103">Combine deux expressions `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a5313-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5313-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a5313-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5313-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="a5313-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="a5313-106">Toute expression valide qui retourne une valeur `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a5313-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5313-107">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="a5313-107">Return Value</span></span>  
 <span data-ttu-id="a5313-108">`true` si l'une des conditions a la valeur `true`; sinon, `false`.</span><span class="sxs-lookup"><span data-stu-id="a5313-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5313-109">Notes</span><span class="sxs-lookup"><span data-stu-id="a5313-109">Remarks</span></span>  
 <span data-ttu-id="a5313-110">OR est un opérateur logique [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5313-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="a5313-111">Il est utilisé pour combiner deux conditions.</span><span class="sxs-lookup"><span data-stu-id="a5313-111">It is used to combine two conditions.</span></span> <span data-ttu-id="a5313-112">Lorsque vous utilisez plusieurs opérateurs logiques dans une instruction, les opérateurs OR sont évalués après les opérateurs AND.</span><span class="sxs-lookup"><span data-stu-id="a5313-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="a5313-113">L'utilisation de parenthèses permet toutefois de modifier l'ordre de traitement.</span><span class="sxs-lookup"><span data-stu-id="a5313-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="a5313-114">Les doubles barres verticales (&#124; &#124;) ont la même fonctionnalité que l’opérateur OR.</span><span class="sxs-lookup"><span data-stu-id="a5313-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="a5313-115">Le tableau ci-dessous indique les valeurs d'entrée et les types de retour possibles.</span><span class="sxs-lookup"><span data-stu-id="a5313-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="a5313-116">true</span><span class="sxs-lookup"><span data-stu-id="a5313-116">TRUE</span></span>|<span data-ttu-id="a5313-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="a5313-117">TRUE</span></span>|<span data-ttu-id="a5313-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="a5313-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="a5313-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="a5313-119">TRUE</span></span>|<span data-ttu-id="a5313-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="a5313-120">FALSE</span></span>|<span data-ttu-id="a5313-121">NULL</span><span class="sxs-lookup"><span data-stu-id="a5313-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="a5313-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="a5313-122">TRUE</span></span>|<span data-ttu-id="a5313-123">NULL</span><span class="sxs-lookup"><span data-stu-id="a5313-123">NULL</span></span>|<span data-ttu-id="a5313-124">NULL</span><span class="sxs-lookup"><span data-stu-id="a5313-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a5313-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="a5313-125">Example</span></span>  
 <span data-ttu-id="a5313-126">La requête Entity SQL ci-dessous utilise l'opérateur OR pour combiner deux expressions `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a5313-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="a5313-127">Cette requête est basée sur le modèle de vente AdventureWorks Sales Model.</span><span class="sxs-lookup"><span data-stu-id="a5313-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a5313-128">Pour compiler et exécuter cette requête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a5313-128">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a5313-129">Suivez la procédure indiquée dans [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a5313-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="a5313-130">Transmettez à la méthode `ExecuteStructuralTypeQuery` la requête suivante en tant qu'argument :</span><span class="sxs-lookup"><span data-stu-id="a5313-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="a5313-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5313-131">See Also</span></span>  
 [<span data-ttu-id="a5313-132">Référence Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a5313-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

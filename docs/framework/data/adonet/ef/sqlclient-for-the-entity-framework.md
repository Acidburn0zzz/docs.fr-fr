---
title: SqlClient pour Entity Framework
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 2801ad445be073f2cd4725d04a0c731e8bfcdd1b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="100d2-102">SqlClient pour Entity Framework</span><span class="sxs-lookup"><span data-stu-id="100d2-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="100d2-103">Cette section décrit le fournisseur de données .NET Framework pour SQL Server (SqlClient) qui permet à Entity Framework de travailler sur Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="100d2-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="100d2-104">Attribut de schéma Provider</span><span class="sxs-lookup"><span data-stu-id="100d2-104">Provider Schema Attribute</span></span>  
 <span data-ttu-id="100d2-105">`Provider` est un attribut de l'élément `Schema` en langage SSDL (Store Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="100d2-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="100d2-106">Pour utiliser SqlClient, attribuez la chaîne « System.Data.SqlClient » à l'attribut `Provider` de l'élément `Schema`.</span><span class="sxs-lookup"><span data-stu-id="100d2-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="100d2-107">Attribut de schéma ProviderManifestToken</span><span class="sxs-lookup"><span data-stu-id="100d2-107">ProviderManifestToken Schema Attribute</span></span>  
 <span data-ttu-id="100d2-108">`ProviderManifestToken` est un attribut obligatoire de l'élément `Schema` en SSDL.</span><span class="sxs-lookup"><span data-stu-id="100d2-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="100d2-109">Ce jeton permet de charger le manifeste du fournisseur pour les scénarios hors connexion.</span><span class="sxs-lookup"><span data-stu-id="100d2-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="100d2-110">Pour plus d’informations sur `ProviderManifestToken` d’attribut, consultez [élément Schema (SSDL)](http://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222).</span><span class="sxs-lookup"><span data-stu-id="100d2-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](http://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222).</span></span>  
  
 <span data-ttu-id="100d2-111">SqlClient peut être utilisé comme un fournisseur de données pour les différentes versions de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="100d2-111">SqlClient can be used as a data provider for different versions of SQL Server.</span></span> <span data-ttu-id="100d2-112">Ces versions ont des fonctionnalités différentes.</span><span class="sxs-lookup"><span data-stu-id="100d2-112">These versions have different capabilities.</span></span> <span data-ttu-id="100d2-113">Par exemple, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] ne prend pas en charge les types `varchar(max)` et `nvarchar(max)` introduits par [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="100d2-113">For example, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] does not support `varchar(max)` and `nvarchar(max)` types that were introduced with [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="100d2-114">SqlClient produit et accepte les jetons du manifeste du fournisseur suivants pour les différentes versions de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="100d2-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="100d2-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="100d2-115">SQL Server 2000</span></span>|<span data-ttu-id="100d2-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="100d2-116">SQL Server 2005</span></span>|<span data-ttu-id="100d2-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="100d2-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="100d2-118">2 000</span><span class="sxs-lookup"><span data-stu-id="100d2-118">2000</span></span>|<span data-ttu-id="100d2-119">2005</span><span class="sxs-lookup"><span data-stu-id="100d2-119">2005</span></span>|<span data-ttu-id="100d2-120">2008</span><span class="sxs-lookup"><span data-stu-id="100d2-120">2008</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="100d2-121">En commençant par [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, le [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527) ne prennent pas en charge SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="100d2-121">Starting with [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, the [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="100d2-122">Nom de l'espace de noms du fournisseur</span><span class="sxs-lookup"><span data-stu-id="100d2-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="100d2-123">Tous les fournisseurs doivent spécifier un espace de noms.</span><span class="sxs-lookup"><span data-stu-id="100d2-123">All providers must specify a namespace.</span></span> <span data-ttu-id="100d2-124">Cette propriété indique à Entity Framework le préfixe attribué par le fournisseur à des constructions spécifiques, telles que des types et des fonctions.</span><span class="sxs-lookup"><span data-stu-id="100d2-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="100d2-125">L'espace de noms des manifestes du fournisseur SqlClient est `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="100d2-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="100d2-126">Pour plus d’informations sur les espaces de noms, consultez [espaces de noms](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="100d2-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="100d2-127">Types</span><span class="sxs-lookup"><span data-stu-id="100d2-127">Types</span></span>  
 <span data-ttu-id="100d2-128">Le fournisseur SqlClient pour Entity Framework fournit des informations de mappage entre les types de modèles conceptuels et les types SQL Server.</span><span class="sxs-lookup"><span data-stu-id="100d2-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="100d2-129">Pour plus d’informations, consultez [SqlClient pour Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span><span class="sxs-lookup"><span data-stu-id="100d2-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="100d2-130">Fonctions</span><span class="sxs-lookup"><span data-stu-id="100d2-130">Functions</span></span>  
 <span data-ttu-id="100d2-131">Le fournisseur SqlClient pour Entity Framework définit la liste des fonctions prises en charge par le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="100d2-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="100d2-132">Pour obtenir la liste des fonctions prises en charge, consultez [fonctions SqlClient pour Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="100d2-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="100d2-133">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="100d2-133">In This Section</span></span>  
 [<span data-ttu-id="100d2-134">Fonctions SqlClient pour Entity Framework</span><span class="sxs-lookup"><span data-stu-id="100d2-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="100d2-135">SqlClient pour Entity FrameworkTypes</span><span class="sxs-lookup"><span data-stu-id="100d2-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="100d2-136">Problèmes connus dans SqlClient pour Entity Framework</span><span class="sxs-lookup"><span data-stu-id="100d2-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="100d2-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="100d2-137">See Also</span></span>  
 [<span data-ttu-id="100d2-138">Langage Entity SQL</span><span class="sxs-lookup"><span data-stu-id="100d2-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="100d2-139">Informations de référence sur le langage</span><span class="sxs-lookup"><span data-stu-id="100d2-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [<span data-ttu-id="100d2-140">Problèmes connus dans le fournisseur SqlClient pour Entity Framework</span><span class="sxs-lookup"><span data-stu-id="100d2-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)

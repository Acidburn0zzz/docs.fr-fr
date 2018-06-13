---
title: '&lt;legacyCorruptedStateExceptionsPolicy&gt; élément'
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6228aaf4c7da70337d9d1a99adcb78f71a0039b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744614"
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a><span data-ttu-id="d5f42-102">&lt;legacyCorruptedStateExceptionsPolicy&gt; élément</span><span class="sxs-lookup"><span data-stu-id="d5f42-102">&lt;legacyCorruptedStateExceptionsPolicy&gt; Element</span></span>
<span data-ttu-id="d5f42-103">Spécifie si le common language runtime permet au code managé d’intercepter les violations d’accès et d’autres exceptions d’état endommagé.</span><span class="sxs-lookup"><span data-stu-id="d5f42-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="d5f42-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d5f42-104">\<configuration></span></span>  
<span data-ttu-id="d5f42-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d5f42-105">\<runtime></span></span>  
<span data-ttu-id="d5f42-106">\<legacyCorruptedStateExceptionsPolicy ></span><span class="sxs-lookup"><span data-stu-id="d5f42-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f42-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d5f42-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5f42-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="d5f42-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d5f42-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="d5f42-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5f42-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="d5f42-110">Attributes</span></span>  
  
|<span data-ttu-id="d5f42-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="d5f42-111">Attribute</span></span>|<span data-ttu-id="d5f42-112">Description</span><span class="sxs-lookup"><span data-stu-id="d5f42-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d5f42-113">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="d5f42-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d5f42-114">Spécifie que l’application interceptera endommager les échecs d’état d’exception telles que des violations d’accès.</span><span class="sxs-lookup"><span data-stu-id="d5f42-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d5f42-115">Attribut enabled</span><span class="sxs-lookup"><span data-stu-id="d5f42-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d5f42-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="d5f42-116">Value</span></span>|<span data-ttu-id="d5f42-117">Description</span><span class="sxs-lookup"><span data-stu-id="d5f42-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d5f42-118">L’application n’intercepte pas endommager les échecs d’état d’exception telles que des violations d’accès.</span><span class="sxs-lookup"><span data-stu-id="d5f42-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="d5f42-119">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="d5f42-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d5f42-120">L’application interceptera endommager les échecs d’état d’exception telles que des violations d’accès.</span><span class="sxs-lookup"><span data-stu-id="d5f42-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5f42-121">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="d5f42-121">Child Elements</span></span>  
 <span data-ttu-id="d5f42-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="d5f42-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5f42-123">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="d5f42-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d5f42-124">Élément</span><span class="sxs-lookup"><span data-stu-id="d5f42-124">Element</span></span>|<span data-ttu-id="d5f42-125">Description</span><span class="sxs-lookup"><span data-stu-id="d5f42-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d5f42-126">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5f42-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d5f42-127">Contient des informations sur les liaisons d’assembly et l’opération garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d5f42-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5f42-128">Notes</span><span class="sxs-lookup"><span data-stu-id="d5f42-128">Remarks</span></span>  
 <span data-ttu-id="d5f42-129">Dans le .NET Framework version 3.5 et versions antérieure, le common language runtime autorise le code managé intercepter les exceptions levées par les États de processus endommagés.</span><span class="sxs-lookup"><span data-stu-id="d5f42-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="d5f42-130">Une violation d’accès est un exemple de ce type d’exception.</span><span class="sxs-lookup"><span data-stu-id="d5f42-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="d5f42-131">En commençant par le [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]managé code n’intercepte plus ces types d’exceptions dans `catch` blocs.</span><span class="sxs-lookup"><span data-stu-id="d5f42-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="d5f42-132">Toutefois, vous pouvez remplacer cette modification et mettre à jour de la gestion des exceptions d’état endommagé de deux manières :</span><span class="sxs-lookup"><span data-stu-id="d5f42-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
-   <span data-ttu-id="d5f42-133">Définir le `<legacyCorruptedStateExceptionsPolicy>` l’élément `enabled` attribut `true`.</span><span class="sxs-lookup"><span data-stu-id="d5f42-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="d5f42-134">Ce paramètre de configuration est appliquée au niveau du processus et affecte toutes les méthodes.</span><span class="sxs-lookup"><span data-stu-id="d5f42-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="d5f42-135">- ou -</span><span class="sxs-lookup"><span data-stu-id="d5f42-135">-or-</span></span>  
  
-   <span data-ttu-id="d5f42-136">Appliquer le <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> d’attribut à la méthode qui contient les exceptions `catch` bloc.</span><span class="sxs-lookup"><span data-stu-id="d5f42-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="d5f42-137">Cet élément de configuration est uniquement disponible dans le [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="d5f42-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5f42-138">Exemple</span><span class="sxs-lookup"><span data-stu-id="d5f42-138">Example</span></span>  
 <span data-ttu-id="d5f42-139">L’exemple suivant montre comment spécifier que l’application doit rétablir le comportement avant le [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]et d’intercepter l’altération de tous les échecs d’exception état.</span><span class="sxs-lookup"><span data-stu-id="d5f42-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5f42-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5f42-140">See Also</span></span>  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [<span data-ttu-id="d5f42-141">Schéma des paramètres d’exécution</span><span class="sxs-lookup"><span data-stu-id="d5f42-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d5f42-142">Schéma des fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="d5f42-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

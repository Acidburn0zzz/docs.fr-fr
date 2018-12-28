---
title: '&lt;gcConcurrent&gt; élément'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fa802ab9d1025bd130a6265b50050284aae0150
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612385"
---
# <a name="ltgcconcurrentgt-element"></a><span data-ttu-id="9bcb1-102">&lt;gcConcurrent&gt; élément</span><span class="sxs-lookup"><span data-stu-id="9bcb1-102">&lt;gcConcurrent&gt; Element</span></span>
<span data-ttu-id="9bcb1-103">Spécifie si le common language runtime exécute l’opération garbage collection sur un thread distinct.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>  
  
 <span data-ttu-id="9bcb1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9bcb1-104">\<configuration></span></span>  
<span data-ttu-id="9bcb1-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="9bcb1-105">\<runtime></span></span>  
<span data-ttu-id="9bcb1-106">\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="9bcb1-106">\<gcConcurrent></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bcb1-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9bcb1-107">Syntax</span></span>  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bcb1-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="9bcb1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9bcb1-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bcb1-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="9bcb1-110">Attributes</span></span>  
  
|<span data-ttu-id="9bcb1-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="9bcb1-111">Attribute</span></span>|<span data-ttu-id="9bcb1-112">Description</span><span class="sxs-lookup"><span data-stu-id="9bcb1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9bcb1-113">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9bcb1-114">Spécifie si le runtime exécute l'opération garbage collection simultanément.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9bcb1-115">Attribut enabled</span><span class="sxs-lookup"><span data-stu-id="9bcb1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9bcb1-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="9bcb1-116">Value</span></span>|<span data-ttu-id="9bcb1-117">Description</span><span class="sxs-lookup"><span data-stu-id="9bcb1-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9bcb1-118">N’exécute pas l’opération garbage collection simultanément.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-118">Does not run garbage collection concurrently.</span></span>|  
|`true`|<span data-ttu-id="9bcb1-119">Exécute l’opération garbage collection simultanément.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="9bcb1-120">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9bcb1-121">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="9bcb1-121">Child Elements</span></span>  
 <span data-ttu-id="9bcb1-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9bcb1-123">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="9bcb1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9bcb1-124">Élément</span><span class="sxs-lookup"><span data-stu-id="9bcb1-124">Element</span></span>|<span data-ttu-id="9bcb1-125">Description</span><span class="sxs-lookup"><span data-stu-id="9bcb1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9bcb1-126">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9bcb1-127">Contient des informations sur les liaisons d’assembly et l’opération garbage collection.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bcb1-128">Notes</span><span class="sxs-lookup"><span data-stu-id="9bcb1-128">Remarks</span></span>  
 <span data-ttu-id="9bcb1-129">Dans les versions antérieures à .NET Framework 4, le garbage collection de station de travail prenait en charge le garbage collection simultané, qui exécutait l’opération garbage collection en arrière-plan sur un thread distinct.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="9bcb1-130">Dans .NET Framework 4, le garbage collection simultané a été remplacé par le garbage collection d'arrière-plan pour effectuer l'opération de la même manière.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="9bcb1-131">Depuis .NET Framework 4.5, le garbage collection d'arrière-plan est disponible dans le garbage collection de serveur.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="9bcb1-132">L'élément `<gcConcurrent>` contrôle si le runtime exécute le garbage collection simultané ou d'arrière-plan, s'il est disponible, ou s'il exécute le garbage collection de premier plan.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it is available, or whether it performs garbage collection in the foreground.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="9bcb1-133">Depuis .NET Framework 4, le garbage collection simultané est remplacé par le garbage collection d’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-133">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="9bcb1-134">Les termes du contrat *simultanées* et *arrière-plan* sont utilisés indifféremment dans la documentation .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-134">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="9bcb1-135">Pour désactiver le garbage collection d’arrière-plan, utilisez l’élément `<gcConcurrent>` comme indiqué dans cet article.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-135">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>  
  
 <span data-ttu-id="9bcb1-136">Par défaut, le runtime utilise le garbage collection simultané ou d'arrière-plan, dont la latence est optimisée.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-136">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="9bcb1-137">Si votre application implique une grande interaction avec l'utilisateur, laissez le garbage collection simultané activé pour minimiser le temps d'interruption de l'application pendant l'exécution de l'opération garbage collection.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-137">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="9bcb1-138">Si vous définissez l'attribut `enabled` de l'élément `<gcConcurrent>` avec la valeur `false`, le runtime utilise le garbage collection non simultané, dont le débit est optimisé.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-138">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="9bcb1-139">Le fichier de configuration suivant désactive le garbage collection d'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-139">The following configuration file disables background garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="9bcb1-140">Le paramètre `<gcConcurrentSetting>` qui figure dans le fichier de configuration de l'ordinateur définit la valeur par défaut de toutes les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-140">If there is a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="9bcb1-141">Ce paramètre se substitue au paramètre du fichier de configuration de l'application.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-141">The machine configuration file setting overrides the application configuration file setting.</span></span>  
  
 <span data-ttu-id="9bcb1-142">Pour plus d’informations sur simultané et garbage collection d’arrière-plan, consultez la section « garbage collection simultané » dans le [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) rubrique.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-142">For more information on concurrent and background garbage collection, see the "Concurrent garbage collection" section in the [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bcb1-143">Exemple</span><span class="sxs-lookup"><span data-stu-id="9bcb1-143">Example</span></span>  
 <span data-ttu-id="9bcb1-144">L’exemple suivant active le garbage collection simultané.</span><span class="sxs-lookup"><span data-stu-id="9bcb1-144">The following example enables concurrent garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bcb1-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9bcb1-145">See Also</span></span>  
- [<span data-ttu-id="9bcb1-146">Schéma des paramètres d’exécution</span><span class="sxs-lookup"><span data-stu-id="9bcb1-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="9bcb1-147">Schéma des fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="9bcb1-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="9bcb1-148">Principes de base du Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9bcb1-148">Fundamentals of Garbage Collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md)

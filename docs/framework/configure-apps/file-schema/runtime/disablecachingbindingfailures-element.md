---
title: '&lt;disableCachingBindingFailures&gt; élément'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78ca269dacc33fb441310ad00ba2548826f5403e
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610513"
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a><span data-ttu-id="285a4-102">&lt;disableCachingBindingFailures&gt; élément</span><span class="sxs-lookup"><span data-stu-id="285a4-102">&lt;disableCachingBindingFailures&gt; Element</span></span>
<span data-ttu-id="285a4-103">Spécifie s’il faut désactiver la mise en cache des échecs se produisent, car l’assembly est introuvable par la détection de liaison.</span><span class="sxs-lookup"><span data-stu-id="285a4-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="285a4-104">\<configuration > élément</span><span class="sxs-lookup"><span data-stu-id="285a4-104">\<configuration> Element</span></span>  
<span data-ttu-id="285a4-105">\<runtime > élément</span><span class="sxs-lookup"><span data-stu-id="285a4-105">\<runtime> Element</span></span>  
<span data-ttu-id="285a4-106">\<disableCachingBindingFailures ></span><span class="sxs-lookup"><span data-stu-id="285a4-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="285a4-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="285a4-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="285a4-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="285a4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="285a4-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="285a4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="285a4-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="285a4-110">Attributes</span></span>  
  
|<span data-ttu-id="285a4-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="285a4-111">Attribute</span></span>|<span data-ttu-id="285a4-112">Description</span><span class="sxs-lookup"><span data-stu-id="285a4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="285a4-113">enabled</span><span class="sxs-lookup"><span data-stu-id="285a4-113">enabled</span></span>|<span data-ttu-id="285a4-114">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="285a4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="285a4-115">Spécifie s’il faut désactiver la mise en cache des échecs se produisent, car l’assembly est introuvable par la détection de liaison.</span><span class="sxs-lookup"><span data-stu-id="285a4-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="285a4-116">Attribut enabled</span><span class="sxs-lookup"><span data-stu-id="285a4-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="285a4-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="285a4-117">Value</span></span>|<span data-ttu-id="285a4-118">Description</span><span class="sxs-lookup"><span data-stu-id="285a4-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="285a4-119">0</span><span class="sxs-lookup"><span data-stu-id="285a4-119">0</span></span>|<span data-ttu-id="285a4-120">Ne désactivez pas la mise en cache des échecs se produisent, car l’assembly est introuvable par la détection de liaison.</span><span class="sxs-lookup"><span data-stu-id="285a4-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="285a4-121">Il s’agit du comportement de liaison par défaut en commençant par le .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="285a4-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="285a4-122">1</span><span class="sxs-lookup"><span data-stu-id="285a4-122">1</span></span>|<span data-ttu-id="285a4-123">Désactiver la mise en cache des échecs se produisent, car l’assembly est introuvable par la détection de liaison.</span><span class="sxs-lookup"><span data-stu-id="285a4-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="285a4-124">Ce paramètre rétablit le comportement de liaison du .NET Framework version 1.1.</span><span class="sxs-lookup"><span data-stu-id="285a4-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="285a4-125">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="285a4-125">Child Elements</span></span>  
 <span data-ttu-id="285a4-126">Aucun.</span><span class="sxs-lookup"><span data-stu-id="285a4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="285a4-127">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="285a4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="285a4-128">Élément</span><span class="sxs-lookup"><span data-stu-id="285a4-128">Element</span></span>|<span data-ttu-id="285a4-129">Description</span><span class="sxs-lookup"><span data-stu-id="285a4-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="285a4-130">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="285a4-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="285a4-131">Contient des informations sur les liaisons d’assembly et l’opération garbage collection.</span><span class="sxs-lookup"><span data-stu-id="285a4-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="285a4-132">Notes</span><span class="sxs-lookup"><span data-stu-id="285a4-132">Remarks</span></span>  
 <span data-ttu-id="285a4-133">À compter de .NET Framework version 2.0, le comportement par défaut pour le chargement des assemblys est mettre en cache tous les liaison et les échecs de chargement.</span><span class="sxs-lookup"><span data-stu-id="285a4-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="285a4-134">Autrement dit, si une tentative de chargement d’un assembly échoue, les demandes suivantes pour charger le même assembly échouent immédiatement, sans faire de tentative pour localiser l’assembly.</span><span class="sxs-lookup"><span data-stu-id="285a4-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="285a4-135">Cet élément désactive ce comportement par défaut pour les échecs de liaison qui se produisent, car l’assembly est introuvable dans le chemin de recherche.</span><span class="sxs-lookup"><span data-stu-id="285a4-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="285a4-136">Ces défaillances lèvent <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="285a4-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="285a4-137">Une liaison et les échecs de chargement ne sont pas affectées par cet élément et sont toujours mis en cache.</span><span class="sxs-lookup"><span data-stu-id="285a4-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="285a4-138">Ces échecs se produisent, car l’assembly a été trouvé, mais ne peut pas être chargé.</span><span class="sxs-lookup"><span data-stu-id="285a4-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="285a4-139">Elles lèvent <xref:System.BadImageFormatException> ou <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="285a4-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="285a4-140">La liste suivante comprend quelques exemples de ces défaillances.</span><span class="sxs-lookup"><span data-stu-id="285a4-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="285a4-141">Si vous tentez de charger un fichier n’est pas un assembly valide, les tentatives suivantes pour charger l’assembly échoue même si le fichier incorrect est remplacé par l’assembly approprié.</span><span class="sxs-lookup"><span data-stu-id="285a4-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="285a4-142">Si vous essayez de charger un assembly qui est verrouillé par le système de fichiers, les tentatives suivantes pour charger l’assembly échoue même après que l’assembly est libéré par le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="285a4-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="285a4-143">Si une ou plusieurs versions de l’assembly que vous tentez de charger est dans le chemin de recherche, mais la version spécifique que vous demandez n’est pas entre eux, les tentatives suivantes pour charger cette version échoue même si la version correcte est déplacée dans le chemin de recherche.</span><span class="sxs-lookup"><span data-stu-id="285a4-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="285a4-144">Exemple</span><span class="sxs-lookup"><span data-stu-id="285a4-144">Example</span></span>  
 <span data-ttu-id="285a4-145">L’exemple suivant montre comment désactiver la mise en cache des échecs de liaison d’assembly qui se produisent, car l’assembly est introuvable par la détection.</span><span class="sxs-lookup"><span data-stu-id="285a4-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="285a4-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="285a4-146">See Also</span></span>  
- [<span data-ttu-id="285a4-147">Schéma des paramètres d’exécution</span><span class="sxs-lookup"><span data-stu-id="285a4-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="285a4-148">Schéma des fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="285a4-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="285a4-149">Méthode de localisation des assemblys par le runtime</span><span class="sxs-lookup"><span data-stu-id="285a4-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)

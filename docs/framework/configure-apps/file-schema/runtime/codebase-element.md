---
title: '&lt;codeBase&gt; élément'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d7563d3a0ba545bfd8d1b80981fcce607d230873
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399240"
---
# <a name="ltcodebasegt-element"></a><span data-ttu-id="0dd34-102">&lt;codeBase&gt; élément</span><span class="sxs-lookup"><span data-stu-id="0dd34-102">&lt;codeBase&gt; Element</span></span>
<span data-ttu-id="0dd34-103">Spécifie où le common language runtime peut trouver un assembly.</span><span class="sxs-lookup"><span data-stu-id="0dd34-103">Specifies where the common language runtime can find an assembly.</span></span>  
  
 <span data-ttu-id="0dd34-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0dd34-104">\<configuration></span></span>  
<span data-ttu-id="0dd34-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="0dd34-105">\<runtime></span></span>  
<span data-ttu-id="0dd34-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="0dd34-106">\<assemblyBinding></span></span>  
<span data-ttu-id="0dd34-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="0dd34-107">\<dependentAssembly></span></span>  
<span data-ttu-id="0dd34-108">\<codeBase ></span><span class="sxs-lookup"><span data-stu-id="0dd34-108">\<codeBase></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd34-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0dd34-109">Syntax</span></span>  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0dd34-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="0dd34-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0dd34-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="0dd34-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0dd34-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="0dd34-112">Attributes</span></span>  
  
|<span data-ttu-id="0dd34-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0dd34-113">Attribute</span></span>|<span data-ttu-id="0dd34-114">Description</span><span class="sxs-lookup"><span data-stu-id="0dd34-114">Description</span></span>|  
|---------------|-----------------|  
|`href`|<span data-ttu-id="0dd34-115">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="0dd34-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="0dd34-116">Spécifie l’URL où le runtime peut trouver la version spécifiée de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="0dd34-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|  
|`version`|<span data-ttu-id="0dd34-117">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="0dd34-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="0dd34-118">Spécifie la version de l’assembly d’à que la base de code s’applique.</span><span class="sxs-lookup"><span data-stu-id="0dd34-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="0dd34-119">Le format du numéro de version est *major.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="0dd34-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|  
  
## <a name="version-attribute"></a><span data-ttu-id="0dd34-120">Attribut de version</span><span class="sxs-lookup"><span data-stu-id="0dd34-120">version Attribute</span></span>  
  
|<span data-ttu-id="0dd34-121">Value</span><span class="sxs-lookup"><span data-stu-id="0dd34-121">Value</span></span>|<span data-ttu-id="0dd34-122">Description</span><span class="sxs-lookup"><span data-stu-id="0dd34-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0dd34-123">Les valeurs valides pour chaque partie du numéro de version sont compris entre 0 et 65535.</span><span class="sxs-lookup"><span data-stu-id="0dd34-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="0dd34-124">Non applicable.</span><span class="sxs-lookup"><span data-stu-id="0dd34-124">Not applicable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0dd34-125">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="0dd34-125">Child Elements</span></span>  
 <span data-ttu-id="0dd34-126">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0dd34-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0dd34-127">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="0dd34-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0dd34-128">Élément</span><span class="sxs-lookup"><span data-stu-id="0dd34-128">Element</span></span>|<span data-ttu-id="0dd34-129">Description</span><span class="sxs-lookup"><span data-stu-id="0dd34-129">Description</span></span>|  
|-------------|-----------------|  
|`buildproviders`|<span data-ttu-id="0dd34-130">Définit une collection de fournisseurs de générations utilisés pour compiler des fichiers de ressources personnalisés.</span><span class="sxs-lookup"><span data-stu-id="0dd34-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="0dd34-131">Le nombre de fournisseurs de générations n'est pas défini.</span><span class="sxs-lookup"><span data-stu-id="0dd34-131">You can have any number of build providers.</span></span>|  
|`compilation`|<span data-ttu-id="0dd34-132">Configure tous les paramètres de compilation ASP.NET utilise.</span><span class="sxs-lookup"><span data-stu-id="0dd34-132">Configures all the compilation settings that ASP.NET uses.</span></span>|  
|`configuration`|<span data-ttu-id="0dd34-133">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0dd34-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.web`|<span data-ttu-id="0dd34-134">Spécifie l'élément racine de la section de configuration ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0dd34-134">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0dd34-135">Notes</span><span class="sxs-lookup"><span data-stu-id="0dd34-135">Remarks</span></span>  
 <span data-ttu-id="0dd34-136">Le runtime doit utiliser le  **\<codeBase >** définissant dans un fichier de configuration machine ou d’un fichier de stratégie d’éditeur, le fichier doit également rediriger la version d’assembly.</span><span class="sxs-lookup"><span data-stu-id="0dd34-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="0dd34-137">Fichiers de configuration d’application peuvent avoir un paramètre de base de code sans avoir à demander la version d’assembly.</span><span class="sxs-lookup"><span data-stu-id="0dd34-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="0dd34-138">Après avoir déterminé la version de l’assembly à utiliser, le runtime applique le paramètre de base de code à partir du fichier qui détermine la version.</span><span class="sxs-lookup"><span data-stu-id="0dd34-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="0dd34-139">Si aucune base de code n’est indiqué, le runtime tente de détecter l’assembly à l’accoutumée.</span><span class="sxs-lookup"><span data-stu-id="0dd34-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>  
  
 <span data-ttu-id="0dd34-140">Si l’assembly a un nom fort, le paramètre de base de code peut être n’importe où sur l’intranet local ou Internet.</span><span class="sxs-lookup"><span data-stu-id="0dd34-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="0dd34-141">Si l’assembly est un assembly privé, le paramètre de base de code doit être un chemin d’accès relatif au répertoire de l’application.</span><span class="sxs-lookup"><span data-stu-id="0dd34-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>  
  
 <span data-ttu-id="0dd34-142">Pour les assemblys sans nom fort, la version est ignorée et le chargeur utilise la première apparition de \<codebase > à l’intérieur \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="0dd34-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="0dd34-143">S’il existe une entrée dans le fichier de configuration d’application qui redirige la liaison à un autre assembly, la redirection est prioritaire même si la version d’assembly ne correspond pas à la demande de liaison.</span><span class="sxs-lookup"><span data-stu-id="0dd34-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesnt match the binding request.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0dd34-144">Exemple</span><span class="sxs-lookup"><span data-stu-id="0dd34-144">Example</span></span>  
 <span data-ttu-id="0dd34-145">L’exemple suivant montre comment spécifier où le runtime peut trouver un assembly.</span><span class="sxs-lookup"><span data-stu-id="0dd34-145">The following example shows how to specify where the runtime can find an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0dd34-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0dd34-146">See Also</span></span>  
 [<span data-ttu-id="0dd34-147">Schéma des paramètres d’exécution</span><span class="sxs-lookup"><span data-stu-id="0dd34-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="0dd34-148">Schéma des fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="0dd34-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="0dd34-149">Spécification de l'emplacement d'un assembly</span><span class="sxs-lookup"><span data-stu-id="0dd34-149">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="0dd34-150">Méthode de localisation des assemblys par le runtime</span><span class="sxs-lookup"><span data-stu-id="0dd34-150">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)

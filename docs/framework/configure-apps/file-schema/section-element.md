---
title: '&lt;section&gt; élément'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 17b44ca93efc26f4732f5fe2926f894257d8f984
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="section-element"></a><span data-ttu-id="0d580-102">\<section > élément</span><span class="sxs-lookup"><span data-stu-id="0d580-102">\<section> element</span></span>

<span data-ttu-id="0d580-103">Contient une déclaration de section de configuration.</span><span class="sxs-lookup"><span data-stu-id="0d580-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="0d580-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0d580-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0d580-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0d580-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="0d580-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section >**</span><span class="sxs-lookup"><span data-stu-id="0d580-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="0d580-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0d580-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0d580-108">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0d580-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="0d580-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="0d580-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="0d580-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section >**</span><span class="sxs-lookup"><span data-stu-id="0d580-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0d580-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0d580-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="0d580-112">Attributs requis</span><span class="sxs-lookup"><span data-stu-id="0d580-112">Required attributes</span></span>

|           | <span data-ttu-id="0d580-113">Description</span><span class="sxs-lookup"><span data-stu-id="0d580-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0d580-114">**name**</span><span class="sxs-lookup"><span data-stu-id="0d580-114">**name**</span></span>  | <span data-ttu-id="0d580-115">Spécifie le nom de la section de configuration.</span><span class="sxs-lookup"><span data-stu-id="0d580-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="0d580-116">**type**</span><span class="sxs-lookup"><span data-stu-id="0d580-116">**type**</span></span>  | <span data-ttu-id="0d580-117">Spécifie le nom de la classe de gestionnaire de section de configuration qui lit la section du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="0d580-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="0d580-118">La valeur de type a la syntaxe « fully-qualified-section-handler-class-name, nom d’assembly simple ».</span><span class="sxs-lookup"><span data-stu-id="0d580-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="0d580-119">Le nom simple d’assembly est le nom de fichier racine sans le *.dll* extension de fichier.</span><span class="sxs-lookup"><span data-stu-id="0d580-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="0d580-120">Attributs facultatifs</span><span class="sxs-lookup"><span data-stu-id="0d580-120">Optional attributes</span></span>

<span data-ttu-id="0d580-121">Les attributs suivants sont appliquent uniquement aux applications ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0d580-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="0d580-122">Le système de configuration ignore ces attributs pour les autres types d’applications.</span><span class="sxs-lookup"><span data-stu-id="0d580-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="0d580-123">Description</span><span class="sxs-lookup"><span data-stu-id="0d580-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="0d580-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="0d580-124">**allowDefinition**</span></span> | <span data-ttu-id="0d580-125">Spécifie la section peut être utilisée dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="0d580-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="0d580-126">Utilisez l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d580-126">Use one of the following values:</span></span><br><br><span data-ttu-id="0d580-127">**Partout**</span><span class="sxs-lookup"><span data-stu-id="0d580-127">**Everywhere**</span></span><br><span data-ttu-id="0d580-128">Permet à la section peut être utilisée dans n’importe quel fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="0d580-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="0d580-129">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="0d580-129">This is the default.</span></span><br><span data-ttu-id="0d580-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="0d580-130">**MachineOnly**</span></span><br><span data-ttu-id="0d580-131">Autorise la section à être utilisé uniquement dans le fichier de configuration machine (*Machine.config*).</span><span class="sxs-lookup"><span data-stu-id="0d580-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="0d580-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="0d580-132">**MachineToApplication**</span></span><br><span data-ttu-id="0d580-133">Autorise la section à utiliser dans le fichier de configuration machine ou dans le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="0d580-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="0d580-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="0d580-134">**allowLocation**</span></span>   | <span data-ttu-id="0d580-135">Détermine si la section peut être utilisée dans le  **\<emplacement >** élément.</span><span class="sxs-lookup"><span data-stu-id="0d580-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="0d580-136">Utilisez l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d580-136">Use one of the following values:</span></span><br><br><span data-ttu-id="0d580-137">**true**</span><span class="sxs-lookup"><span data-stu-id="0d580-137">**true**</span></span><br><span data-ttu-id="0d580-138">La section au sein de la  **\<emplacement >** élément.</span><span class="sxs-lookup"><span data-stu-id="0d580-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="0d580-139">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="0d580-139">This is the default.</span></span><br><span data-ttu-id="0d580-140">**false**</span><span class="sxs-lookup"><span data-stu-id="0d580-140">**false**</span></span><br><span data-ttu-id="0d580-141">N’autorise pas la section au sein de la  **\<emplacement >** élément.</span><span class="sxs-lookup"><span data-stu-id="0d580-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="0d580-142">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="0d580-142">Parent elements</span></span>

|     | <span data-ttu-id="0d580-143">Description</span><span class="sxs-lookup"><span data-stu-id="0d580-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0d580-144">**\<configSections >** élément</span><span class="sxs-lookup"><span data-stu-id="0d580-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="0d580-145">Contient des déclarations d’espace de noms et de la section de configuration.</span><span class="sxs-lookup"><span data-stu-id="0d580-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="0d580-146">**\<sectionGroup >** élément</span><span class="sxs-lookup"><span data-stu-id="0d580-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="0d580-147">Définit un espace de noms de sections de configuration.</span><span class="sxs-lookup"><span data-stu-id="0d580-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="0d580-148">A  **\<section >** élément est un élément enfant d’un  **\<configSections >** ou  **\<sectionGroup >** mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="0d580-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="0d580-149">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="0d580-149">Child elements</span></span>

<span data-ttu-id="0d580-150">Aucun</span><span class="sxs-lookup"><span data-stu-id="0d580-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0d580-151">Notes</span><span class="sxs-lookup"><span data-stu-id="0d580-151">Remarks</span></span>

<span data-ttu-id="0d580-152">Déclaration essentiellement d’une section de configuration définit un nouvel élément pour le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="0d580-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="0d580-153">Le nouvel élément contient une configuration de gestionnaire de section de paramètres (autrement dit, une classe qui implémente le <xref:System.Configuration.IConfigurationSectionHandler> interface) lit.</span><span class="sxs-lookup"><span data-stu-id="0d580-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="0d580-154">Les attributs et les éléments enfants d’une section que vous définissez dépendent du Gestionnaire de section que vous permet de lire vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="0d580-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="0d580-155">Déclaration d’un gestionnaire de section de configuration dans le *Machine.config* fichier vous permet d’utiliser la section de configuration dans n’importe quel fichier de configuration d’application sur cet ordinateur, à moins que le **allowDefinition**attribut spécifie dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="0d580-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="0d580-156">Exemple</span><span class="sxs-lookup"><span data-stu-id="0d580-156">Example</span></span>

<span data-ttu-id="0d580-157">L’exemple suivant montre comment définir une section de configuration et de définir les paramètres de cette section :</span><span class="sxs-lookup"><span data-stu-id="0d580-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="0d580-158">fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="0d580-158">Configuration file</span></span>

<span data-ttu-id="0d580-159">Cet élément peut être utilisé dans le fichier de configuration d’application, fichier de configuration machine (*Machine.config*), et *Web.config* les fichiers qui ne sont pas au niveau du répertoire d’application.</span><span class="sxs-lookup"><span data-stu-id="0d580-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d580-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d580-160">See also</span></span>

[<span data-ttu-id="0d580-161">Schéma de fichier de configuration pour le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0d580-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)

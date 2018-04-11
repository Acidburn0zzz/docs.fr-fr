---
title: Élément personnalisé pour SingleTagSectionHandler
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ee722c7d5db9d58ab1a91f4b1299912981510af
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/10/2018
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="6b922-102">Élément personnalisé pour SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="6b922-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="6b922-103">Définit les paramètres dans une section de configuration personnalisée qui est définie par un</span><span class="sxs-lookup"><span data-stu-id="6b922-103">Defines settings in a custom configuration section that is defined by a</span></span> <section> <span data-ttu-id="6b922-104">élément et utilise la <xref:System.Configuration.SingleTagSectionHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="6b922-104">element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="6b922-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6b922-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6b922-106">&nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="6b922-106">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="6b922-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6b922-107">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="6b922-108">Attributs</span><span class="sxs-lookup"><span data-stu-id="6b922-108">Attributes</span></span>

<span data-ttu-id="6b922-109">Attributs et valeurs d’attribut sont définies par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6b922-109">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="6b922-110">Élément parent</span><span class="sxs-lookup"><span data-stu-id="6b922-110">Parent element</span></span>

|     | <span data-ttu-id="6b922-111">Description</span><span class="sxs-lookup"><span data-stu-id="6b922-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6b922-112">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="6b922-112">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="6b922-113">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b922-113">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6b922-114">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="6b922-114">Child elements</span></span>

<span data-ttu-id="6b922-115">Aucun</span><span class="sxs-lookup"><span data-stu-id="6b922-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="6b922-116">Notes</span><span class="sxs-lookup"><span data-stu-id="6b922-116">Remarks</span></span>

<span data-ttu-id="6b922-117">Le  **\<sectionName >** est un élément personnalisé défini par un [  **\<section >** ](~/docs/framework/configure-apps/file-schema/section-element.md) de balise dans le [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) élément.</span><span class="sxs-lookup"><span data-stu-id="6b922-117">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="6b922-118">Le système de configuration retourne un <xref:System.Collections.IDictionary> lorsque vous appelez l’objet <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6b922-118">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="6b922-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="6b922-119">Example</span></span>

<span data-ttu-id="6b922-120">L’exemple suivant déclare un élément personnalisé appelé  **\<sampleSection >** qui contient les paramètres lus par le <xref:System.Configuration.SingleTagSectionHandler> classe :</span><span class="sxs-lookup"><span data-stu-id="6b922-120">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6b922-121">fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="6b922-121">Configuration file</span></span>

<span data-ttu-id="6b922-122">Cet élément peut être utilisé dans le fichier de configuration d’application, fichier de configuration machine (*Machine.config*), et *Web.config* les fichiers qui ne sont pas au niveau du répertoire d’application.</span><span class="sxs-lookup"><span data-stu-id="6b922-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b922-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b922-123">See also</span></span>

[<span data-ttu-id="6b922-124">Schéma de fichier de configuration pour le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6b922-124">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)

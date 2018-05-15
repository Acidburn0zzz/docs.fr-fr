---
title: '&lt;supprimer&gt; élément de NameValueSectionHandler et DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 61f1c98d3f12b5aa1d25595ca28328602683b073
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="a02c7-102">\<Supprimer >, élément pour NameValueSectionHandler et DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="a02c7-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="a02c7-103">Supprime un paramètre défini précédemment.</span><span class="sxs-lookup"><span data-stu-id="a02c7-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="a02c7-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a02c7-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="a02c7-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="a02c7-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="a02c7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Supprimer >**</span><span class="sxs-lookup"><span data-stu-id="a02c7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a02c7-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a02c7-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="a02c7-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="a02c7-108">Attribute</span></span>

|           | <span data-ttu-id="a02c7-109">Description</span><span class="sxs-lookup"><span data-stu-id="a02c7-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="a02c7-110">**key**</span><span class="sxs-lookup"><span data-stu-id="a02c7-110">**key**</span></span>   | <span data-ttu-id="a02c7-111">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="a02c7-111">Required attribute.</span></span><br><br><span data-ttu-id="a02c7-112">Spécifie le nom du paramètre à supprimer.</span><span class="sxs-lookup"><span data-stu-id="a02c7-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="a02c7-113">Élément parent</span><span class="sxs-lookup"><span data-stu-id="a02c7-113">Parent element</span></span>

| <span data-ttu-id="a02c7-114">Élément</span><span class="sxs-lookup"><span data-stu-id="a02c7-114">Element</span></span> | <span data-ttu-id="a02c7-115">Description</span><span class="sxs-lookup"><span data-stu-id="a02c7-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="a02c7-116">**\<sectionName >** élément</span><span class="sxs-lookup"><span data-stu-id="a02c7-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="a02c7-117">Définit les paramètres pour les sections de configuration personnalisées qui utilisent le <xref:System.Configuration.NameValueSectionHandler> et <xref:System.Configuration.DictionarySectionHandler> classes.</span><span class="sxs-lookup"><span data-stu-id="a02c7-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a02c7-118">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="a02c7-118">Child elements</span></span>

<span data-ttu-id="a02c7-119">Aucun</span><span class="sxs-lookup"><span data-stu-id="a02c7-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="a02c7-120">Notes</span><span class="sxs-lookup"><span data-stu-id="a02c7-120">Remarks</span></span>

<span data-ttu-id="a02c7-121">Vous pouvez utiliser la  **\<Supprimer >** élément à supprimer les paramètres de votre application qui ont été définis à un niveau supérieur dans la hiérarchie des fichiers de configuration.</span><span class="sxs-lookup"><span data-stu-id="a02c7-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="a02c7-122">Exemple</span><span class="sxs-lookup"><span data-stu-id="a02c7-122">Example</span></span>

<span data-ttu-id="a02c7-123">L’exemple suivant montre comment utiliser le  **\<Supprimer >** élément dans un fichier de configuration pour supprimer les paramètres définis précédemment dans le fichier de configuration machine.</span><span class="sxs-lookup"><span data-stu-id="a02c7-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="a02c7-124">Le code suivant du fichier de configuration machine déclare la section  **\<MaSection >** et ajoute deux paramètres, `key1` et `key2`, à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="a02c7-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="a02c7-125">Le code du fichier de configuration application suivant supprime la `key2` définition à partir de  **\<MaSection >**:</span><span class="sxs-lookup"><span data-stu-id="a02c7-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="a02c7-126">fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="a02c7-126">Configuration file</span></span>

<span data-ttu-id="a02c7-127">Cet élément peut être utilisé dans le fichier de configuration d’application, fichier de configuration machine (*Machine.config*), et *Web.config* les fichiers qui ne sont pas au niveau du répertoire d’application.</span><span class="sxs-lookup"><span data-stu-id="a02c7-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a02c7-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a02c7-128">See also</span></span>

[<span data-ttu-id="a02c7-129">Schéma de fichier de configuration pour le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a02c7-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)

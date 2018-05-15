---
title: '&lt;linkedConfiguration&gt; élément'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 71769efa1233fc8a693219dc02ae56ea39c164e7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="33633-102">\<linkedConfiguration > élément</span><span class="sxs-lookup"><span data-stu-id="33633-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="33633-103">Spécifie un fichier de configuration à inclure.</span><span class="sxs-lookup"><span data-stu-id="33633-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="33633-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="33633-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="33633-105">&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="33633-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="33633-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="33633-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="33633-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="33633-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="33633-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="33633-108">Attribute</span></span>

|           | <span data-ttu-id="33633-109">Description</span><span class="sxs-lookup"><span data-stu-id="33633-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="33633-110">**href**</span><span class="sxs-lookup"><span data-stu-id="33633-110">**href**</span></span>  | <span data-ttu-id="33633-111">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="33633-111">Required attribute.</span></span><br><br><span data-ttu-id="33633-112">L’URL du fichier de configuration à inclure.</span><span class="sxs-lookup"><span data-stu-id="33633-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="33633-113">Le seul format pris en charge pour le **href** attribut est `file://`.</span><span class="sxs-lookup"><span data-stu-id="33633-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="33633-114">Fichiers locaux et les fichiers UNC sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="33633-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="33633-115">Élément parent</span><span class="sxs-lookup"><span data-stu-id="33633-115">Parent element</span></span>

|     | <span data-ttu-id="33633-116">Description</span><span class="sxs-lookup"><span data-stu-id="33633-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="33633-117">**\<assemblyBinding >** élément</span><span class="sxs-lookup"><span data-stu-id="33633-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="33633-118">Spécifie la stratégie de liaison de l’assembly au niveau de la configuration.</span><span class="sxs-lookup"><span data-stu-id="33633-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="33633-119">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="33633-119">Child elements</span></span>

<span data-ttu-id="33633-120">Aucun</span><span class="sxs-lookup"><span data-stu-id="33633-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="33633-121">Notes</span><span class="sxs-lookup"><span data-stu-id="33633-121">Remarks</span></span>

<span data-ttu-id="33633-122">Le  **\<linkedConfiguration >** élément simplifie la maintenance pour les assemblys de composant.</span><span class="sxs-lookup"><span data-stu-id="33633-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="33633-123">Si une ou plusieurs applications utilisent un assembly disposant d’un fichier de configuration qui réside dans un emplacement connu, les fichiers de configuration des applications qui utilisent l’assembly peuvent utiliser le  **\<linkedConfiguration >** élément à inclure le fichier de configuration d’assembly, au lieu d’y compris les informations de configuration directement.</span><span class="sxs-lookup"><span data-stu-id="33633-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="33633-124">Lorsque l’assembly de composant est prise en charge, la mise à jour le fichier de configuration commun fournit des informations de configuration mise à jour pour toutes les applications qui utilisent l’assembly.</span><span class="sxs-lookup"><span data-stu-id="33633-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="33633-125">Le  **\<linkedConfiguration >** élément n’est pas pris en charge pour les applications avec des manifestes côte à côte de Windows.</span><span class="sxs-lookup"><span data-stu-id="33633-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="33633-126">Les règles suivantes régissent l’utilisation des fichiers de configuration liés :</span><span class="sxs-lookup"><span data-stu-id="33633-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="33633-127">Les paramètres dans les fichiers de configuration inclus uniquement affectent la stratégie de liaison du chargeur et sont utilisés uniquement par le chargeur.</span><span class="sxs-lookup"><span data-stu-id="33633-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="33633-128">Les fichiers de configuration inclus peuvent avoir des paramètres autres que les stratégies de liaison, mais ces paramètres n’ont aucun effet.</span><span class="sxs-lookup"><span data-stu-id="33633-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="33633-129">Le seul format pris en charge pour le `href` attribut est `file://`.</span><span class="sxs-lookup"><span data-stu-id="33633-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="33633-130">Fichiers locaux et les fichiers UNC sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="33633-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="33633-131">Il n’existe aucune contrainte sur le nombre de configurations liées par fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="33633-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="33633-132">Tous les fichiers de configuration liés sont fusionnés pour former un fichier, semblable au comportement de la `#include` directive en C/C++.</span><span class="sxs-lookup"><span data-stu-id="33633-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="33633-133">Le  **\<linkedConfiguration >** élément est autorisé uniquement dans les fichiers de configuration d’application ; il est ignoré dans *Machine.config*.</span><span class="sxs-lookup"><span data-stu-id="33633-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="33633-134">Les références circulaires sont détectées et arrêtées.</span><span class="sxs-lookup"><span data-stu-id="33633-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="33633-135">Autrement dit, si le  **\<linkedConfiguration >** les éléments d’une série de fichiers de configuration forment une boucle, la boucle est détectée et arrêtée.</span><span class="sxs-lookup"><span data-stu-id="33633-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="33633-136">Exemple</span><span class="sxs-lookup"><span data-stu-id="33633-136">Example</span></span>

<span data-ttu-id="33633-137">L’exemple suivant montre comment inclure le fichier de configuration à partir du disque dur local :</span><span class="sxs-lookup"><span data-stu-id="33633-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="33633-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33633-138">See also</span></span>

<span data-ttu-id="33633-139">[**\<assemblyBinding >** élément](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="33633-139">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
[<span data-ttu-id="33633-140">Schéma de fichier de configuration pour le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="33633-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)

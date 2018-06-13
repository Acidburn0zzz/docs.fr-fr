---
title: '&lt;Assert&gt; élément'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ab1644d23e4d6d78b62e701902e5ec39e134b38b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745118"
---
# <a name="ltassertgt-element"></a><span data-ttu-id="4d85c-102">&lt;Assert&gt; élément</span><span class="sxs-lookup"><span data-stu-id="4d85c-102">&lt;assert&gt; Element</span></span>
<span data-ttu-id="4d85c-103">Indique si une boîte de message doit s’afficher quand vous appelez la méthode <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> ; spécifie également le nom du fichier dans lequel écrire les messages.</span><span class="sxs-lookup"><span data-stu-id="4d85c-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  
  
 <span data-ttu-id="4d85c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4d85c-104">\<configuration></span></span>  
<span data-ttu-id="4d85c-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="4d85c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4d85c-106">\<Assert ></span><span class="sxs-lookup"><span data-stu-id="4d85c-106">\<assert></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d85c-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4d85c-107">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d85c-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="4d85c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4d85c-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="4d85c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d85c-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="4d85c-110">Attributes</span></span>  
  
|<span data-ttu-id="4d85c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4d85c-111">Attribute</span></span>|<span data-ttu-id="4d85c-112">Description</span><span class="sxs-lookup"><span data-stu-id="4d85c-112">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="4d85c-113">Attribut facultatif.</span><span class="sxs-lookup"><span data-stu-id="4d85c-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4d85c-114">Spécifie si pour afficher un boîte de message lorsque le **Debug.Assert** prend la valeur de méthode **false**.</span><span class="sxs-lookup"><span data-stu-id="4d85c-114">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="4d85c-115">Attribut facultatif.</span><span class="sxs-lookup"><span data-stu-id="4d85c-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4d85c-116">Spécifie le nom du fichier à écrire le message se **Debug.Assert** prend la valeur de **false**.</span><span class="sxs-lookup"><span data-stu-id="4d85c-116">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="4d85c-117">Attribut d’AssertUiEnabled</span><span class="sxs-lookup"><span data-stu-id="4d85c-117">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="4d85c-118">Value</span><span class="sxs-lookup"><span data-stu-id="4d85c-118">Value</span></span>|<span data-ttu-id="4d85c-119">Description</span><span class="sxs-lookup"><span data-stu-id="4d85c-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="4d85c-120">Affiche la boîte de message.</span><span class="sxs-lookup"><span data-stu-id="4d85c-120">Displays the message box.</span></span> <span data-ttu-id="4d85c-121">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="4d85c-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="4d85c-122">Ne pas afficher la boîte de message.</span><span class="sxs-lookup"><span data-stu-id="4d85c-122">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d85c-123">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="4d85c-123">Child Elements</span></span>  
 <span data-ttu-id="4d85c-124">Aucun.</span><span class="sxs-lookup"><span data-stu-id="4d85c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d85c-125">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="4d85c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="4d85c-126">Élément</span><span class="sxs-lookup"><span data-stu-id="4d85c-126">Element</span></span>|<span data-ttu-id="4d85c-127">Description</span><span class="sxs-lookup"><span data-stu-id="4d85c-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4d85c-128">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d85c-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4d85c-129">Spécifie les écouteurs de trace qui collectent, stockent et acheminent les messages, ainsi que le niveau auquel un commutateur de trace est défini.</span><span class="sxs-lookup"><span data-stu-id="4d85c-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d85c-130">Notes</span><span class="sxs-lookup"><span data-stu-id="4d85c-130">Remarks</span></span>  
 <span data-ttu-id="4d85c-131">Les deux attributs dans le  **\<assert >** élément sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="4d85c-131">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="4d85c-132">Vous pouvez désactiver les boîtes de message sans spécifier de fichier pour écrire les messages, ou vous pouvez spécifier un fichier pour écrire des messages tout en laissant les messages activés.</span><span class="sxs-lookup"><span data-stu-id="4d85c-132">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d85c-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="4d85c-133">Example</span></span>  
 <span data-ttu-id="4d85c-134">L’exemple suivant montre comment désactiver l’affichage des messages lorsque vous appelez **Debug.Assert** et écrire les messages dans `c:\log.txt`.</span><span class="sxs-lookup"><span data-stu-id="4d85c-134">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d85c-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d85c-135">See Also</span></span>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="4d85c-136">Schéma des paramètres de trace et de débogage</span><span class="sxs-lookup"><span data-stu-id="4d85c-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)

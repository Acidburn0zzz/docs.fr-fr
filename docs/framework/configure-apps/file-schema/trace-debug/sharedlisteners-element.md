---
title: '&lt;sharedListeners&gt; élément'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b312ea8180c464fb9f955e7d7079cac930c8bf05
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070134"
---
# <a name="ltsharedlistenersgt-element"></a><span data-ttu-id="3322c-102">&lt;sharedListeners&gt; élément</span><span class="sxs-lookup"><span data-stu-id="3322c-102">&lt;sharedListeners&gt; Element</span></span>
<span data-ttu-id="3322c-103">Contient des écouteurs auxquels toute source ou tout élément de trace peuvent faire référence.</span><span class="sxs-lookup"><span data-stu-id="3322c-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="3322c-104">Ces écouteurs ne reçoivent pas les traces par défaut, et il n’est pas possible de récupérer au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="3322c-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="3322c-105">Écouteurs identifiés comme des écouteurs partagés peuvent être ajoutés à des sources ou des traces par nom.</span><span class="sxs-lookup"><span data-stu-id="3322c-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="3322c-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3322c-106">\<configuration></span></span>  
<span data-ttu-id="3322c-107">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="3322c-107">\<system.diagnostics></span></span>  
<span data-ttu-id="3322c-108">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="3322c-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3322c-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3322c-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3322c-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="3322c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3322c-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="3322c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3322c-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="3322c-112">Attributes</span></span>  
 <span data-ttu-id="3322c-113">Aucun.</span><span class="sxs-lookup"><span data-stu-id="3322c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3322c-114">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="3322c-114">Child Elements</span></span>  
  
|<span data-ttu-id="3322c-115">Élément</span><span class="sxs-lookup"><span data-stu-id="3322c-115">Element</span></span>|<span data-ttu-id="3322c-116">Description</span><span class="sxs-lookup"><span data-stu-id="3322c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3322c-117">\<add></span><span class="sxs-lookup"><span data-stu-id="3322c-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="3322c-118">Ajoute un écouteur à la collection `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="3322c-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3322c-119">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="3322c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3322c-120">Élément</span><span class="sxs-lookup"><span data-stu-id="3322c-120">Element</span></span>|<span data-ttu-id="3322c-121">Description</span><span class="sxs-lookup"><span data-stu-id="3322c-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="3322c-122">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3322c-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3322c-123">Spécifie l'élément racine de la section de configuration ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3322c-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3322c-124">Notes</span><span class="sxs-lookup"><span data-stu-id="3322c-124">Remarks</span></span>  
 <span data-ttu-id="3322c-125">Ajout d’un écouteur à la collection d’écouteurs partagés n’en fait pas un écouteur actif.</span><span class="sxs-lookup"><span data-stu-id="3322c-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="3322c-126">Il doit encore être ajouté à une source de trace ou d’une trace en l’ajoutant à la `Listeners` collection pour cet élément de la trace.</span><span class="sxs-lookup"><span data-stu-id="3322c-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="3322c-127">Les classes de l’écouteur dans le .NET Framework dérivent la <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="3322c-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="3322c-128">Cet élément peut être utilisé dans le fichier de configuration machine (Machine.config) et le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="3322c-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3322c-129">Exemple</span><span class="sxs-lookup"><span data-stu-id="3322c-129">Example</span></span>  
 <span data-ttu-id="3322c-130">L’exemple suivant montre comment utiliser le `<sharedListeners>` élément pour ajouter l’écouteur `console` à la `Listeners` collection à la fois pour le <xref:System.Diagnostics.TraceSource> et <xref:System.Diagnostics.Trace> classes.</span><span class="sxs-lookup"><span data-stu-id="3322c-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="3322c-131">L’écouteur de suivi de console écrit des informations de traçage dans la console par des appels à <xref:System.Diagnostics.TraceSource> ou <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="3322c-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a><span data-ttu-id="3322c-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3322c-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="3322c-133">Schéma des paramètres de trace et de débogage</span><span class="sxs-lookup"><span data-stu-id="3322c-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="3322c-134">Écouteurs de suivi</span><span class="sxs-lookup"><span data-stu-id="3322c-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)

---
title: '&lt;filtre&gt; élément pour &lt;ajouter&gt; pour &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 5172a2be163e178b9c7115825fa5dba4ff073a96
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47115137"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a><span data-ttu-id="2684c-102">&lt;filtre&gt; élément pour &lt;ajouter&gt; pour &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="2684c-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="2684c-103">Ajoute un filtre à un écouteur dans la collection `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="2684c-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="2684c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2684c-104">\<configuration></span></span>  
<span data-ttu-id="2684c-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="2684c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2684c-106">\<sharedListeners > élément</span><span class="sxs-lookup"><span data-stu-id="2684c-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="2684c-107">\<add></span><span class="sxs-lookup"><span data-stu-id="2684c-107">\<add></span></span>  
<span data-ttu-id="2684c-108">\<Filtre ></span><span class="sxs-lookup"><span data-stu-id="2684c-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2684c-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2684c-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2684c-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="2684c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2684c-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="2684c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2684c-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="2684c-112">Attributes</span></span>  
  
|<span data-ttu-id="2684c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2684c-113">Attribute</span></span>|<span data-ttu-id="2684c-114">Description</span><span class="sxs-lookup"><span data-stu-id="2684c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2684c-115">**type**</span><span class="sxs-lookup"><span data-stu-id="2684c-115">**type**</span></span>|<span data-ttu-id="2684c-116">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="2684c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="2684c-117">Spécifie le type du filtre.</span><span class="sxs-lookup"><span data-stu-id="2684c-117">Specifies the type of the filter.</span></span> <span data-ttu-id="2684c-118">Vous pouvez utiliser uniquement le nom complet du type (dans le format de la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propriété), ou vous pouvez utiliser le nom de type qualifié complet, y compris les informations d’assembly (dans le format de la <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> propriété).</span><span class="sxs-lookup"><span data-stu-id="2684c-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="2684c-119">Pour plus d’informations sur la création d’un nom de type qualifié complet, consultez [spécifiant des noms de types qualifiés complets](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="2684c-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="2684c-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="2684c-120">**initializeData**</span></span>|<span data-ttu-id="2684c-121">Attribut facultatif.</span><span class="sxs-lookup"><span data-stu-id="2684c-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2684c-122">La chaîne passée au constructeur pour la classe spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2684c-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2684c-123">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="2684c-123">Child Elements</span></span>  
 <span data-ttu-id="2684c-124">Aucun.</span><span class="sxs-lookup"><span data-stu-id="2684c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2684c-125">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="2684c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2684c-126">Élément</span><span class="sxs-lookup"><span data-stu-id="2684c-126">Element</span></span>|<span data-ttu-id="2684c-127">Description</span><span class="sxs-lookup"><span data-stu-id="2684c-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2684c-128">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2684c-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2684c-129">Spécifie les écouteurs de trace qui collectent, stockent et acheminent les messages, ainsi que le niveau auquel un commutateur de trace est défini.</span><span class="sxs-lookup"><span data-stu-id="2684c-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="2684c-130">Une collection d’écouteurs de n’importe quel élément trace ou une source peut faire référence.</span><span class="sxs-lookup"><span data-stu-id="2684c-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="2684c-131">Ajoute un écouteur à la **sharedListeners** collection.</span><span class="sxs-lookup"><span data-stu-id="2684c-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2684c-132">Notes</span><span class="sxs-lookup"><span data-stu-id="2684c-132">Remarks</span></span>  
 <span data-ttu-id="2684c-133">Si un écouteur est défini dans un `<add>` élément de la `<sharedListeners>` élément, le filtre de cet écouteur doit être défini dans un `<filter>` élément qui est un enfant de le `<add>` élément.</span><span class="sxs-lookup"><span data-stu-id="2684c-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="2684c-134">Cet élément peut être utilisé dans le fichier de configuration machine (Machine.config) et le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="2684c-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2684c-135">Exemple</span><span class="sxs-lookup"><span data-stu-id="2684c-135">Example</span></span>  
 <span data-ttu-id="2684c-136">L’exemple suivant montre comment utiliser le `<filter>` élément pour ajouter un filtre à l’écouteur de suivi `console` dans le `sharedListeners` collection.</span><span class="sxs-lookup"><span data-stu-id="2684c-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2684c-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2684c-137">See Also</span></span>  
 <xref:System.Diagnostics.TraceFilter>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="2684c-138">Schéma des paramètres de trace et de débogage</span><span class="sxs-lookup"><span data-stu-id="2684c-138">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)

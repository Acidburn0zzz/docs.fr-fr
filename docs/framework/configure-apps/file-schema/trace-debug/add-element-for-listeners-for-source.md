---
title: '&lt;ajouter&gt; élément pour &lt;écouteurs&gt; pour &lt;source&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: c0ab15f6eca8b20653530583016eb849273c4ce1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47072028"
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="49e41-102">&lt;ajouter&gt; élément pour &lt;écouteurs&gt; pour &lt;source&gt;</span><span class="sxs-lookup"><span data-stu-id="49e41-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="49e41-103">Ajoute un écouteur à la collection `Listeners` pour une source de trace.</span><span class="sxs-lookup"><span data-stu-id="49e41-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="49e41-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="49e41-104">\<configuration></span></span>  
<span data-ttu-id="49e41-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="49e41-105">\<system.diagnostics></span></span>  
<span data-ttu-id="49e41-106">\<sources ></span><span class="sxs-lookup"><span data-stu-id="49e41-106">\<sources></span></span>  
<span data-ttu-id="49e41-107">\<source ></span><span class="sxs-lookup"><span data-stu-id="49e41-107">\<source></span></span>  
<span data-ttu-id="49e41-108">\<écouteurs ></span><span class="sxs-lookup"><span data-stu-id="49e41-108">\<listeners></span></span>  
<span data-ttu-id="49e41-109">\<add></span><span class="sxs-lookup"><span data-stu-id="49e41-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e41-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="49e41-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49e41-111">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="49e41-111">Attributes and Elements</span></span>  
 <span data-ttu-id="49e41-112">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="49e41-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49e41-113">Attributs</span><span class="sxs-lookup"><span data-stu-id="49e41-113">Attributes</span></span>  
  
|<span data-ttu-id="49e41-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="49e41-114">Attribute</span></span>|<span data-ttu-id="49e41-115">Description</span><span class="sxs-lookup"><span data-stu-id="49e41-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="49e41-116">Attribut, requis, sauf si vous référencez un écouteur dans la `sharedListeners` regroupement, dans lequel cas vous suffit de faire référence par nom (voir la [exemple](#example)).</span><span class="sxs-lookup"><span data-stu-id="49e41-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="49e41-117">Spécifie le type de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="49e41-117">Specifies the type of the listener.</span></span> <span data-ttu-id="49e41-118">Vous devez utiliser une chaîne conforme aux exigences spécifiées dans [spécifiant des noms de types qualifiés complets](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="49e41-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="49e41-119">Attribut facultatif.</span><span class="sxs-lookup"><span data-stu-id="49e41-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="49e41-120">La chaîne passée au constructeur pour la classe spécifiée.</span><span class="sxs-lookup"><span data-stu-id="49e41-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="49e41-121">Un <xref:System.Configuration.ConfigurationException> est levée si la classe n’a pas de constructeur qui accepte une chaîne.</span><span class="sxs-lookup"><span data-stu-id="49e41-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="49e41-122">Attribut facultatif.</span><span class="sxs-lookup"><span data-stu-id="49e41-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="49e41-123">Spécifie le nom de l’écouteur.</span><span class="sxs-lookup"><span data-stu-id="49e41-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="49e41-124">Attribut facultatif.</span><span class="sxs-lookup"><span data-stu-id="49e41-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="49e41-125">Spécifie le <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valeur de propriété pour l’écouteur de suivi.</span><span class="sxs-lookup"><span data-stu-id="49e41-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="49e41-126">[attributs personnalisés]</span><span class="sxs-lookup"><span data-stu-id="49e41-126">[custom attributes]</span></span>|<span data-ttu-id="49e41-127">Attributs facultatifs.</span><span class="sxs-lookup"><span data-stu-id="49e41-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="49e41-128">Spécifie la valeur pour les attributs spécifiques à l’écouteur identifiés par la <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> méthode pour cet écouteur.</span><span class="sxs-lookup"><span data-stu-id="49e41-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="49e41-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> est un exemple d’attribut supplémentaire unique à la <xref:System.Diagnostics.DelimitedListTraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="49e41-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49e41-130">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="49e41-130">Child Elements</span></span>  
  
|<span data-ttu-id="49e41-131">Élément</span><span class="sxs-lookup"><span data-stu-id="49e41-131">Element</span></span>|<span data-ttu-id="49e41-132">Description</span><span class="sxs-lookup"><span data-stu-id="49e41-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49e41-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="49e41-133">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="49e41-134">Ajoute un filtre à un écouteur dans la collection `Listeners` pour une source de trace.</span><span class="sxs-lookup"><span data-stu-id="49e41-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49e41-135">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="49e41-135">Parent Elements</span></span>  
  
|<span data-ttu-id="49e41-136">Élément</span><span class="sxs-lookup"><span data-stu-id="49e41-136">Element</span></span>|<span data-ttu-id="49e41-137">Description</span><span class="sxs-lookup"><span data-stu-id="49e41-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="49e41-138">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49e41-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="49e41-139">Spécifie les écouteurs de trace qui collectent, stockent et acheminent les messages, ainsi que le niveau auquel un commutateur de trace est défini.</span><span class="sxs-lookup"><span data-stu-id="49e41-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="49e41-140">Contient les sources de trace qui lancent des messages de traçage.</span><span class="sxs-lookup"><span data-stu-id="49e41-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="49e41-141">Spécifie une source de trace qui lance des messages de traçage.</span><span class="sxs-lookup"><span data-stu-id="49e41-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="49e41-142">Spécifie des écouteurs qui collectent, stockent et acheminent les messages.</span><span class="sxs-lookup"><span data-stu-id="49e41-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49e41-143">Notes</span><span class="sxs-lookup"><span data-stu-id="49e41-143">Remarks</span></span>  
 <span data-ttu-id="49e41-144">Les classes de l’écouteur fournis avec le .NET Framework dérivent la <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="49e41-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="49e41-145">Si vous ne spécifiez pas le `name` attribut de l’écouteur de suivi, le <xref:System.Diagnostics.TraceListener.Name%2A> propriété de l’écouteur de trace par défaut est une chaîne vide (« »).</span><span class="sxs-lookup"><span data-stu-id="49e41-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="49e41-146">Si votre application comporte un seul écouteur, vous pouvez l’ajouter sans spécifier de nom, et vous pouvez le supprimer en spécifiant une chaîne vide pour le nom.</span><span class="sxs-lookup"><span data-stu-id="49e41-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="49e41-147">Toutefois, si votre application a plusieurs écouteurs, vous devez spécifier un nom unique pour chaque écouteur de trace, qui vous permet d’identifier et de gérer des écouteurs de trace individuels dans le <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span><span class="sxs-lookup"><span data-stu-id="49e41-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49e41-148">Ajout de plusieurs écouteurs de trace du même type et avec le même nommez entraîne l’écouteur de suivi qu’un seul de ce type et ajouté à la `Listeners` collection.</span><span class="sxs-lookup"><span data-stu-id="49e41-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="49e41-149">Toutefois, vous pouvez ajouter par programmation plusieurs écouteurs identiques à la `Listeners` collection.</span><span class="sxs-lookup"><span data-stu-id="49e41-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="49e41-150">La valeur de la `initializeData` attribut varie selon le type d’écouteur que vous créez.</span><span class="sxs-lookup"><span data-stu-id="49e41-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="49e41-151">Pas tous les écouteurs de trace nécessitent que vous spécifiez `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="49e41-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49e41-152">Lorsque vous utilisez le `initializeData` attribut, vous risquez d’obtenir le compilateur Avertissement : « l’attribut 'initializeData' n’est pas déclaré. ».</span><span class="sxs-lookup"><span data-stu-id="49e41-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="49e41-153">Cet avertissement se produit parce que les paramètres de configuration sont validés par rapport à la classe de base abstraite <xref:System.Diagnostics.TraceListener>, qui ne reconnaît pas le `initializeData` attribut.</span><span class="sxs-lookup"><span data-stu-id="49e41-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="49e41-154">En règle générale, vous pouvez ignorer cet avertissement pour les implémentations d’écouteur de trace qui ont un constructeur qui accepte un paramètre.</span><span class="sxs-lookup"><span data-stu-id="49e41-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="49e41-155">Le tableau suivant présente les écouteurs de trace qui sont inclus avec le .NET Framework et décrit la valeur de leur `initializeData` attributs.</span><span class="sxs-lookup"><span data-stu-id="49e41-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="49e41-156">Classe d’écouteur de trace</span><span class="sxs-lookup"><span data-stu-id="49e41-156">Trace listener class</span></span>|<span data-ttu-id="49e41-157">valeur de l’attribut initializeData</span><span class="sxs-lookup"><span data-stu-id="49e41-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e41-158">Le `useErrorStream` valeur pour le <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructeur.</span><span class="sxs-lookup"><span data-stu-id="49e41-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="49e41-159">Définir le `initializeData` l’attribut «`true`« écrire trace et debug de sortie pour le flux d’erreurs standard ; affectez-lui la valeur »`false`» à écrire dans le flux de sortie standard.</span><span class="sxs-lookup"><span data-stu-id="49e41-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e41-160">Le nom du fichier le <xref:System.Diagnostics.DelimitedListTraceListener> écrit dans.</span><span class="sxs-lookup"><span data-stu-id="49e41-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e41-161">Le nom d’une source existante de journal des événements.</span><span class="sxs-lookup"><span data-stu-id="49e41-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e41-162">Le nom du fichier qui le <xref:System.Diagnostics.EventSchemaTraceListener> écrit dans.</span><span class="sxs-lookup"><span data-stu-id="49e41-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e41-163">Le nom du fichier qui le <xref:System.Diagnostics.TextWriterTraceListener> écrit dans.</span><span class="sxs-lookup"><span data-stu-id="49e41-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="49e41-164">Le nom du fichier qui le <xref:System.Diagnostics.XmlWriterTraceListener> écrit dans.</span><span class="sxs-lookup"><span data-stu-id="49e41-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="49e41-165">Fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="49e41-165">Configuration File</span></span>  
 <span data-ttu-id="49e41-166">Cet élément peut être utilisé dans le fichier de configuration machine (Machine.config) et le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="49e41-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49e41-167">Exemple</span><span class="sxs-lookup"><span data-stu-id="49e41-167">Example</span></span>  
 <span data-ttu-id="49e41-168">L’exemple suivant montre comment utiliser `<add>` éléments à ajouter les écouteurs `console` et `textListener` à la `Listeners` collection pour la source de suivi `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="49e41-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="49e41-169">Le `textListener` écouteur écrit la sortie de trace dans le fichier myListener.log.</span><span class="sxs-lookup"><span data-stu-id="49e41-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="49e41-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49e41-170">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="49e41-171">Schéma des paramètres de trace et de débogage</span><span class="sxs-lookup"><span data-stu-id="49e41-171">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="49e41-172">Écouteurs de suivi</span><span class="sxs-lookup"><span data-stu-id="49e41-172">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)

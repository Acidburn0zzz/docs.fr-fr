---
title: '&lt;sources&gt; élément'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a9c5c5529e349eca2ba089ed6fb71da4bd48430a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47203327"
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="39b15-102">&lt;sources&gt; élément</span><span class="sxs-lookup"><span data-stu-id="39b15-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="39b15-103">Spécifie les sources de trace qui initient des messages de suivi.</span><span class="sxs-lookup"><span data-stu-id="39b15-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="39b15-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="39b15-104">\<configuration></span></span>  
<span data-ttu-id="39b15-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="39b15-105">\<system.diagnostics></span></span>  
<span data-ttu-id="39b15-106">\<sources ></span><span class="sxs-lookup"><span data-stu-id="39b15-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b15-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="39b15-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39b15-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="39b15-108">Attributes and Elements</span></span>  
 <span data-ttu-id="39b15-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="39b15-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39b15-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="39b15-110">Attributes</span></span>  
 <span data-ttu-id="39b15-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="39b15-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39b15-112">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="39b15-112">Child Elements</span></span>  
  
|<span data-ttu-id="39b15-113">Élément</span><span class="sxs-lookup"><span data-stu-id="39b15-113">Element</span></span>|<span data-ttu-id="39b15-114">Description</span><span class="sxs-lookup"><span data-stu-id="39b15-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39b15-115">\<source></span><span class="sxs-lookup"><span data-stu-id="39b15-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="39b15-116">Élément requis.</span><span class="sxs-lookup"><span data-stu-id="39b15-116">Required element.</span></span><br /><br /> <span data-ttu-id="39b15-117">Spécifie une source de trace qui lance des messages de traçage.</span><span class="sxs-lookup"><span data-stu-id="39b15-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39b15-118">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="39b15-118">Parent Elements</span></span>  
  
|<span data-ttu-id="39b15-119">Élément</span><span class="sxs-lookup"><span data-stu-id="39b15-119">Element</span></span>|<span data-ttu-id="39b15-120">Description</span><span class="sxs-lookup"><span data-stu-id="39b15-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="39b15-121">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="39b15-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="39b15-122">Spécifie les écouteurs de trace qui collectent, stockent et acheminent les messages, ainsi que le niveau auquel un commutateur de trace est défini.</span><span class="sxs-lookup"><span data-stu-id="39b15-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39b15-123">Notes</span><span class="sxs-lookup"><span data-stu-id="39b15-123">Remarks</span></span>  
 <span data-ttu-id="39b15-124">Cet élément peut être utilisé dans le fichier de configuration machine (Machine.config) et le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="39b15-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39b15-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="39b15-125">Example</span></span>  
 <span data-ttu-id="39b15-126">L’exemple suivant montre comment utiliser le `<sources>` élément à ajouter la source de suivi `mySource` et pour définir le niveau du commutateur source nommé `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="39b15-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="39b15-127">Un écouteur de suivi de console est ajouté qui écrit les informations de trace dans la console.</span><span class="sxs-lookup"><span data-stu-id="39b15-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"   
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"   
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"   
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>    
   </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="39b15-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39b15-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="39b15-129">Schéma des paramètres de trace et de débogage</span><span class="sxs-lookup"><span data-stu-id="39b15-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="39b15-130">\<source></span><span class="sxs-lookup"><span data-stu-id="39b15-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)

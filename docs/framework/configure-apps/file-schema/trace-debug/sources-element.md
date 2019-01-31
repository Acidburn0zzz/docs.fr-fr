---
title: Élément <sources>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: d7d92f91838a8d1914ffe574f018cc701477d767
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262502"
---
# <a name="sources-element"></a><span data-ttu-id="46ea5-102">\<sources > élément</span><span class="sxs-lookup"><span data-stu-id="46ea5-102">\<sources> Element</span></span>
<span data-ttu-id="46ea5-103">Spécifie les sources de trace qui initient des messages de suivi.</span><span class="sxs-lookup"><span data-stu-id="46ea5-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="46ea5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="46ea5-104">\<configuration></span></span>  
<span data-ttu-id="46ea5-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="46ea5-105">\<system.diagnostics></span></span>  
<span data-ttu-id="46ea5-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="46ea5-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ea5-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="46ea5-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46ea5-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="46ea5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="46ea5-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="46ea5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46ea5-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="46ea5-110">Attributes</span></span>  
 <span data-ttu-id="46ea5-111">Aucun.</span><span class="sxs-lookup"><span data-stu-id="46ea5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46ea5-112">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="46ea5-112">Child Elements</span></span>  
  
|<span data-ttu-id="46ea5-113">Élément</span><span class="sxs-lookup"><span data-stu-id="46ea5-113">Element</span></span>|<span data-ttu-id="46ea5-114">Description</span><span class="sxs-lookup"><span data-stu-id="46ea5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46ea5-115">\<source></span><span class="sxs-lookup"><span data-stu-id="46ea5-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="46ea5-116">Élément requis.</span><span class="sxs-lookup"><span data-stu-id="46ea5-116">Required element.</span></span><br /><br /> <span data-ttu-id="46ea5-117">Spécifie une source de trace qui lance des messages de traçage.</span><span class="sxs-lookup"><span data-stu-id="46ea5-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46ea5-118">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="46ea5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="46ea5-119">Élément</span><span class="sxs-lookup"><span data-stu-id="46ea5-119">Element</span></span>|<span data-ttu-id="46ea5-120">Description</span><span class="sxs-lookup"><span data-stu-id="46ea5-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="46ea5-121">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46ea5-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="46ea5-122">Spécifie les écouteurs de trace qui collectent, stockent et acheminent les messages, ainsi que le niveau auquel un commutateur de trace est défini.</span><span class="sxs-lookup"><span data-stu-id="46ea5-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46ea5-123">Notes</span><span class="sxs-lookup"><span data-stu-id="46ea5-123">Remarks</span></span>  
 <span data-ttu-id="46ea5-124">Cet élément peut être utilisé dans le fichier de configuration machine (Machine.config) et le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="46ea5-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ea5-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="46ea5-125">Example</span></span>  
 <span data-ttu-id="46ea5-126">L’exemple suivant montre comment utiliser le `<sources>` élément à ajouter la source de suivi `mySource` et pour définir le niveau du commutateur source nommé `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="46ea5-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="46ea5-127">Un écouteur de suivi de console est ajouté qui écrit les informations de trace dans la console.</span><span class="sxs-lookup"><span data-stu-id="46ea5-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="46ea5-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46ea5-128">See also</span></span>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="46ea5-129">Schéma des paramètres de trace et de débogage</span><span class="sxs-lookup"><span data-stu-id="46ea5-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="46ea5-130">\<source></span><span class="sxs-lookup"><span data-stu-id="46ea5-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)

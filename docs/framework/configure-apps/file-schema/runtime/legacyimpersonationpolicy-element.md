---
title: Élément <legacyImpersonationPolicy>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a731a54771f3ac589031e856539ba0c21ca22778
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270487"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="4b478-102">\<legacyImpersonationPolicy > élément</span><span class="sxs-lookup"><span data-stu-id="4b478-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="4b478-103">Spécifie que l’identité Windows n’est pas transmise entre des points asynchrones, indépendamment des paramètres de flux du contexte d’exécution sur le thread actif.</span><span class="sxs-lookup"><span data-stu-id="4b478-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="4b478-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4b478-104">\<configuration></span></span>  
<span data-ttu-id="4b478-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="4b478-105">\<runtime></span></span>  
<span data-ttu-id="4b478-106">\<legacyImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="4b478-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b478-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4b478-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b478-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="4b478-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4b478-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="4b478-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b478-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="4b478-110">Attributes</span></span>  
  
|<span data-ttu-id="4b478-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4b478-111">Attribute</span></span>|<span data-ttu-id="4b478-112">Description</span><span class="sxs-lookup"><span data-stu-id="4b478-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4b478-113">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="4b478-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4b478-114">Spécifie que le <xref:System.Security.Principal.WindowsIdentity> n’est pas transmise entre des points asynchrones, indépendamment de la <xref:System.Threading.ExecutionContext> de flux de paramètres sur le thread actuel.</span><span class="sxs-lookup"><span data-stu-id="4b478-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4b478-115">Attribut enabled</span><span class="sxs-lookup"><span data-stu-id="4b478-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4b478-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="4b478-116">Value</span></span>|<span data-ttu-id="4b478-117">Description</span><span class="sxs-lookup"><span data-stu-id="4b478-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4b478-118"><xref:System.Security.Principal.WindowsIdentity> flux entre des points asynchrones, en fonction de la <xref:System.Threading.ExecutionContext> de flux de paramètres pour le thread actuel.</span><span class="sxs-lookup"><span data-stu-id="4b478-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="4b478-119">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="4b478-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4b478-120"><xref:System.Security.Principal.WindowsIdentity> n’est pas transmise entre des points asynchrones, indépendamment de la <xref:System.Threading.ExecutionContext> de flux de paramètres sur le thread actuel.</span><span class="sxs-lookup"><span data-stu-id="4b478-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b478-121">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="4b478-121">Child Elements</span></span>  
 <span data-ttu-id="4b478-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="4b478-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b478-123">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="4b478-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4b478-124">Élément</span><span class="sxs-lookup"><span data-stu-id="4b478-124">Element</span></span>|<span data-ttu-id="4b478-125">Description</span><span class="sxs-lookup"><span data-stu-id="4b478-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4b478-126">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b478-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4b478-127">Contient des informations sur les liaisons d’assembly et l’opération garbage collection.</span><span class="sxs-lookup"><span data-stu-id="4b478-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b478-128">Notes</span><span class="sxs-lookup"><span data-stu-id="4b478-128">Remarks</span></span>  
 <span data-ttu-id="4b478-129">Dans les versions de .NET Framework 1.0 et 1.1, le <xref:System.Security.Principal.WindowsIdentity> ne sera pas transmis entre des points asynchrones définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4b478-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="4b478-130">À compter de .NET Framework version 2.0, il existe un <xref:System.Threading.ExecutionContext> objet qui contient des informations sur le thread en cours d’exécution et il franchit les points asynchrones d’un domaine d’application.</span><span class="sxs-lookup"><span data-stu-id="4b478-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="4b478-131">Le <xref:System.Security.Principal.WindowsIdentity> est inclus dans ce contexte d’exécution et par conséquent également transmise entre des points asynchrones, ce qui signifie que si un contexte d’emprunt d’identité existe, il transmet également.</span><span class="sxs-lookup"><span data-stu-id="4b478-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="4b478-132">À compter de .NET Framework 2.0, vous pouvez utiliser la `<legacyImpersonationPolicy>` élément pour spécifier que <xref:System.Security.Principal.WindowsIdentity> ne sera pas transmis entre des points asynchrones.</span><span class="sxs-lookup"><span data-stu-id="4b478-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b478-133">Le common language runtime (CLR) tient compte d’emprunt d’identité de l’appeler des opérations effectuées utilisant uniquement du code managé, pas de l’emprunt d’identité effectuée en dehors du code managé, telles que via la plateforme au code non managé ou via des appels directs aux fonctions Win32.</span><span class="sxs-lookup"><span data-stu-id="4b478-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="4b478-134">Managé <xref:System.Security.Principal.WindowsIdentity> objets peuvent être transmis entre des points asynchrones, à moins que le `alwaysFlowImpersonationPolicy` élément a été défini sur true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="4b478-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="4b478-135">Définition de la `alwaysFlowImpersonationPolicy` élément true spécifie que l’identité Windows est toujours transmise entre des points asynchrones, indépendamment du mode d’emprunt d’identité.</span><span class="sxs-lookup"><span data-stu-id="4b478-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="4b478-136">Pour plus d’informations sur la transmission non gérés d’emprunt d’identité entre des points asynchrones, consultez [ \<alwaysFlowImpersonationPolicy > élément](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="4b478-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="4b478-137">Vous pouvez modifier ce comportement par défaut de deux manières :</span><span class="sxs-lookup"><span data-stu-id="4b478-137">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="4b478-138">Dans le code managé sur un thread par thread.</span><span class="sxs-lookup"><span data-stu-id="4b478-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="4b478-139">Vous pouvez supprimer le flux sur un thread par thread en modifiant le <xref:System.Threading.ExecutionContext> et <xref:System.Security.SecurityContext> paramètres à l’aide de la <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> ou <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> (méthode).</span><span class="sxs-lookup"><span data-stu-id="4b478-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="4b478-140">Dans l’appel à l’interface d’hébergement non managée pour charger le common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4b478-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="4b478-141">Si une interface d’hébergement non managée (au lieu d’un simple fichier exécutable managé) est utilisée pour charger le CLR, vous pouvez spécifier un indicateur spécial dans l’appel à la [fonction CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (fonction).</span><span class="sxs-lookup"><span data-stu-id="4b478-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="4b478-142">Pour activer le mode de compatibilité pour l’ensemble du processus, définissez la `flags` paramètre pour [fonction CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) valeur STARTUP_LEGACY_IMPERSONATION au.</span><span class="sxs-lookup"><span data-stu-id="4b478-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="4b478-143">Pour plus d’informations, consultez le [ \<alwaysFlowImpersonationPolicy > élément](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="4b478-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4b478-144">Fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="4b478-144">Configuration File</span></span>  
 <span data-ttu-id="4b478-145">Dans une application .NET Framework, cet élément peut être utilisé uniquement dans le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="4b478-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="4b478-146">Pour une application ASP.NET, le flux de l’emprunt d’identité peut être configuré dans le fichier aspnet.config dans le \<Windows dossier > \Microsoft.NET\Framework\vx.x.xxxx directory.</span><span class="sxs-lookup"><span data-stu-id="4b478-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="4b478-147">ASP.NET par défaut désactive le flux de l’emprunt d’identité dans le fichier aspnet.config à l’aide des paramètres de configuration suivants :</span><span class="sxs-lookup"><span data-stu-id="4b478-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="4b478-148">Dans ASP.NET, si vous souhaitez autoriser le flux d’emprunt d’identité au lieu de cela, vous devez utiliser explicitement les paramètres de configuration suivants :</span><span class="sxs-lookup"><span data-stu-id="4b478-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="4b478-149">Exemple</span><span class="sxs-lookup"><span data-stu-id="4b478-149">Example</span></span>  
 <span data-ttu-id="4b478-150">L’exemple suivant montre comment spécifier le comportement hérité qui ne transmet pas l’identité Windows entre des points asynchrones.</span><span class="sxs-lookup"><span data-stu-id="4b478-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b478-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b478-151">See also</span></span>
- [<span data-ttu-id="4b478-152">Schéma des paramètres d’exécution</span><span class="sxs-lookup"><span data-stu-id="4b478-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="4b478-153">Schéma des fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="4b478-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4b478-154">\<alwaysFlowImpersonationPolicy > élément</span><span class="sxs-lookup"><span data-stu-id="4b478-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)

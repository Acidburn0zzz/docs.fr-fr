---
title: '&lt;defaultProxy&gt; élément (paramètres réseau)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a91775ff9f46eba772a959cfac3115c9720ac5ab
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742716"
---
# <a name="ltdefaultproxygt-element-network-settings"></a><span data-ttu-id="0915d-102">&lt;defaultProxy&gt; élément (paramètres réseau)</span><span class="sxs-lookup"><span data-stu-id="0915d-102">&lt;defaultProxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="0915d-103">Configure le serveur proxy HTTP (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="0915d-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="0915d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0915d-104">\<configuration></span></span>  
<span data-ttu-id="0915d-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="0915d-105">\<system.net></span></span>  
<span data-ttu-id="0915d-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="0915d-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0915d-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0915d-107">Syntax</span></span>  
  
```xml  
      <defaultProxy  
        enabled="true|false"  
        useDefaultCredentials="true|false">  
           <bypasslist> … </bypasslist>  
           <proxy> … </proxy>  
           <module> … </module>  
      </defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0915d-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="0915d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0915d-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="0915d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0915d-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="0915d-110">Attributes</span></span>  
  
|<span data-ttu-id="0915d-111">**Élément**</span><span class="sxs-lookup"><span data-stu-id="0915d-111">**Element**</span></span>|<span data-ttu-id="0915d-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="0915d-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="0915d-113">Spécifie si un proxy web est utilisé.</span><span class="sxs-lookup"><span data-stu-id="0915d-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="0915d-114">La valeur par défaut est `true`.</span><span class="sxs-lookup"><span data-stu-id="0915d-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="0915d-115">Spécifie si les informations d'identification par défaut associées à cet hôte sont utilisées pour accéder au proxy web.</span><span class="sxs-lookup"><span data-stu-id="0915d-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="0915d-116">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="0915d-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0915d-117">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="0915d-117">Child Elements</span></span>  
  
|<span data-ttu-id="0915d-118">**Élément**</span><span class="sxs-lookup"><span data-stu-id="0915d-118">**Element**</span></span>|<span data-ttu-id="0915d-119">**Description**</span><span class="sxs-lookup"><span data-stu-id="0915d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0915d-120">BypassList</span><span class="sxs-lookup"><span data-stu-id="0915d-120">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="0915d-121">Fournit un ensemble d'expressions régulières décrivant les adresses qui n'utilisent pas le proxy.</span><span class="sxs-lookup"><span data-stu-id="0915d-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="0915d-122">Module</span><span class="sxs-lookup"><span data-stu-id="0915d-122">module</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|<span data-ttu-id="0915d-123">Ajoute un nouveau module proxy à l'application.</span><span class="sxs-lookup"><span data-stu-id="0915d-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="0915d-124">Proxy</span><span class="sxs-lookup"><span data-stu-id="0915d-124">proxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|<span data-ttu-id="0915d-125">Définit un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="0915d-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0915d-126">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="0915d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="0915d-127">**Élément**</span><span class="sxs-lookup"><span data-stu-id="0915d-127">**Element**</span></span>|<span data-ttu-id="0915d-128">**Description**</span><span class="sxs-lookup"><span data-stu-id="0915d-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0915d-129">System.NET</span><span class="sxs-lookup"><span data-stu-id="0915d-129">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="0915d-130">Contient des paramètres qui spécifient la manière dont .NET Framework se connecte au réseau.</span><span class="sxs-lookup"><span data-stu-id="0915d-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0915d-131">Notes</span><span class="sxs-lookup"><span data-stu-id="0915d-131">Remarks</span></span>  
 <span data-ttu-id="0915d-132">Si l'élément defaultProxy est vide, les paramètres du proxy Internet Explorer sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="0915d-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="0915d-133">Ce comportement est différent de la version 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0915d-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="0915d-134">Une exception est levée si le [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) élément spécifie un type non public, le type ne dérive pas de la <xref:System.Net.IWebProxy> (classe), une exception à partir du constructeur par défaut de cet objet s’est produite, ou une exception s’est produite alors que la récupération du proxy système spécifié la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="0915d-134">An exception is thrown if the [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the default constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="0915d-135">La propriété <xref:System.Exception.InnerException%2A> de l'exception fournit normalement plus d'informations sur la cause première de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="0915d-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0915d-136">Fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="0915d-136">Configuration Files</span></span>  
 <span data-ttu-id="0915d-137">Cet élément peut être défini dans le fichier de configuration de l'application ou dans le fichier de configuration de l'ordinateur (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0915d-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0915d-138">Exemple</span><span class="sxs-lookup"><span data-stu-id="0915d-138">Example</span></span>  
 <span data-ttu-id="0915d-139">L’exemple suivant utilise les valeurs par défaut du proxy Internet Explorer, spécifie l’adresse proxy et contourne le proxy pour l’accès local et contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0915d-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0915d-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0915d-140">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="0915d-141">Schéma des paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="0915d-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

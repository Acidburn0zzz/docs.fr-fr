---
title: '&lt;NetFx40_PInvokeStackResilience&gt; élément'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cfd8c971edd4537de6e073c49f128f86eb8a042
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748995"
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a><span data-ttu-id="93bad-102">&lt;NetFx40_PInvokeStackResilience&gt; élément</span><span class="sxs-lookup"><span data-stu-id="93bad-102">&lt;NetFx40_PInvokeStackResilience&gt; Element</span></span>
<span data-ttu-id="93bad-103">Indique si le runtime corrige automatiquement les déclarations incorrectes d’appel de code non managé à l’exécution, au prix de transitions plus lentes entre le code managé et le code non managé.</span><span class="sxs-lookup"><span data-stu-id="93bad-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="93bad-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="93bad-104">\<configuration></span></span>  
<span data-ttu-id="93bad-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="93bad-105">\<runtime></span></span>  
<span data-ttu-id="93bad-106">< NetFx40_PInvokeStackResilience ></span><span class="sxs-lookup"><span data-stu-id="93bad-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93bad-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="93bad-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93bad-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="93bad-108">Attributes and Elements</span></span>  
 <span data-ttu-id="93bad-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="93bad-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93bad-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="93bad-110">Attributes</span></span>  
  
|<span data-ttu-id="93bad-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="93bad-111">Attribute</span></span>|<span data-ttu-id="93bad-112">Description</span><span class="sxs-lookup"><span data-stu-id="93bad-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="93bad-113">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="93bad-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="93bad-114">Spécifie si le runtime détecte plateforme incorrect déclarations d’appel et résout automatiquement la pile au moment de l’exécution sur les plateformes 32 bits.</span><span class="sxs-lookup"><span data-stu-id="93bad-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="93bad-115">Attribut enabled</span><span class="sxs-lookup"><span data-stu-id="93bad-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="93bad-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="93bad-116">Value</span></span>|<span data-ttu-id="93bad-117">Description</span><span class="sxs-lookup"><span data-stu-id="93bad-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="93bad-118">Le runtime utilise l’architecture introduite dans de marshaling d’interopérabilité plus rapide la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], qui ne détecte pas et les déclarations d’appel de plateforme incorrect de correctif.</span><span class="sxs-lookup"><span data-stu-id="93bad-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="93bad-119">Il s'agit de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="93bad-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="93bad-120">Les runtime utilise les transitions lentes pour détecter et corriger la plateforme incorrecte les déclarations d’appel.</span><span class="sxs-lookup"><span data-stu-id="93bad-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93bad-121">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="93bad-121">Child Elements</span></span>  
 <span data-ttu-id="93bad-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="93bad-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93bad-123">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="93bad-123">Parent Elements</span></span>  
  
|<span data-ttu-id="93bad-124">Élément</span><span class="sxs-lookup"><span data-stu-id="93bad-124">Element</span></span>|<span data-ttu-id="93bad-125">Description</span><span class="sxs-lookup"><span data-stu-id="93bad-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="93bad-126">Élément racine de chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93bad-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="93bad-127">Contient des informations sur les options d'initialisation du runtime.</span><span class="sxs-lookup"><span data-stu-id="93bad-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93bad-128">Notes</span><span class="sxs-lookup"><span data-stu-id="93bad-128">Remarks</span></span>  
 <span data-ttu-id="93bad-129">Cet élément vous permet aux échanges plus rapidement le marshaling d’interopérabilité pour les déclarations d’appel de résilience d’exécution sur la plateforme incorrecte.</span><span class="sxs-lookup"><span data-stu-id="93bad-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="93bad-130">En commençant par le [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], une architecture de marshaling d’interopérabilité simplifiée offre une amélioration significative des performances pour les transitions du code managé au code non managé.</span><span class="sxs-lookup"><span data-stu-id="93bad-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="93bad-131">Dans les versions antérieures du .NET Framework, la plateforme incorrecte détectée de couche marshaling sur les plateformes 32 bits, les déclarations d’appel et corrigés automatiquement la pile.</span><span class="sxs-lookup"><span data-stu-id="93bad-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="93bad-132">La nouvelle architecture de marshaling élimine cette étape.</span><span class="sxs-lookup"><span data-stu-id="93bad-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="93bad-133">Par conséquent, les transitions sont très rapides, mais une déclaration non managé incorrectes peuvent provoquer un échec du programme.</span><span class="sxs-lookup"><span data-stu-id="93bad-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="93bad-134">Pour faciliter la détection des déclarations incorrectes pendant le développement, le débogage de Visual Studio a été amélioré.</span><span class="sxs-lookup"><span data-stu-id="93bad-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="93bad-135">Le [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) assistant débogage managé (MDA) vous notifie de plateforme incorrect appel déclarations lorsque votre application s’exécute avec le débogueur attaché.</span><span class="sxs-lookup"><span data-stu-id="93bad-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="93bad-136">Pour les scénarios où votre application utilise des composants que vous ne pouvez pas recompiler et qu’avez incorrect non managé déclarations, vous pouvez utiliser la `NetFx40_PInvokeStackResilience` élément.</span><span class="sxs-lookup"><span data-stu-id="93bad-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="93bad-137">Ajout de cet élément à votre fichier de configuration d’application avec `enabled="1"` opte pour un mode de compatibilité avec le comportement des versions antérieures du .NET Framework, au prix de transitions plus lentes.</span><span class="sxs-lookup"><span data-stu-id="93bad-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="93bad-138">Les assemblys qui ont été compilés avec des versions antérieures du .NET Framework sont automatiquement choisis dans ce mode de compatibilité et n’avez pas besoin de cet élément.</span><span class="sxs-lookup"><span data-stu-id="93bad-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="93bad-139">Fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="93bad-139">Configuration File</span></span>  
 <span data-ttu-id="93bad-140">Cet élément peut être utilisé uniquement dans le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="93bad-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93bad-141">Exemple</span><span class="sxs-lookup"><span data-stu-id="93bad-141">Example</span></span>  
 <span data-ttu-id="93bad-142">L’exemple suivant montre comment adopter une résistance accrue contre incorrect pour une application, au prix de transitions plus lentes entre les déclarations d’appel de plateforme de code managé et.</span><span class="sxs-lookup"><span data-stu-id="93bad-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="93bad-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93bad-143">See Also</span></span>  
 [<span data-ttu-id="93bad-144">Schéma des paramètres d’exécution</span><span class="sxs-lookup"><span data-stu-id="93bad-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="93bad-145">Schéma des fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="93bad-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="93bad-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="93bad-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)

---
title: '&lt;mexNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 7144584f1bf64048f94d6172cfee887362813639
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861467"
---
# <a name="ltmexnamedpipebindinggt"></a><span data-ttu-id="18f8e-102">&lt;mexNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="18f8e-102">&lt;mexNamedPipeBinding&gt;</span></span>
<span data-ttu-id="18f8e-103">Spécifie les paramètres pour une liaison utilisée pour l’échange de messages WS-MetadataExchange (WS-MEX) sur le canal nommé.</span><span class="sxs-lookup"><span data-stu-id="18f8e-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="18f8e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="18f8e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="18f8e-105">\<liaisons ></span><span class="sxs-lookup"><span data-stu-id="18f8e-105">\<bindings></span></span>  
<span data-ttu-id="18f8e-106">\<mexNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="18f8e-106">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f8e-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="18f8e-107">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18f8e-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="18f8e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18f8e-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="18f8e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18f8e-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="18f8e-110">Attributes</span></span>  
  
|<span data-ttu-id="18f8e-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="18f8e-111">Attribute</span></span>|<span data-ttu-id="18f8e-112">Description</span><span class="sxs-lookup"><span data-stu-id="18f8e-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="18f8e-113"><xref:System.TimeSpan> qui spécifie l'intervalle de temps prévu pour la réalisation d'une opération de fermeture.</span><span class="sxs-lookup"><span data-stu-id="18f8e-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="18f8e-114">Cette valeur doit être supérieure ou égale à <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="18f8e-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="18f8e-115">La valeur par défaut est 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="18f8e-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="18f8e-116">Chaîne qui contient le nom de configuration de la liaison.</span><span class="sxs-lookup"><span data-stu-id="18f8e-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="18f8e-117">Cette valeur doit être unique car elle permet d'identifier la liaison.</span><span class="sxs-lookup"><span data-stu-id="18f8e-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="18f8e-118">Chaque liaison porte un `name` et a un attribut `namespace` qui l'identifient de façon unique dans les métadonnées du service.</span><span class="sxs-lookup"><span data-stu-id="18f8e-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="18f8e-119">De plus, ce nom est unique parmi les liaisons du même type.</span><span class="sxs-lookup"><span data-stu-id="18f8e-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="18f8e-120">Depuis [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], les liaisons et les comportements ne sont pas obligés d'avoir un nom.</span><span class="sxs-lookup"><span data-stu-id="18f8e-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="18f8e-121">Pour plus d’informations sur la configuration par défaut et les liaisons sans nom et les comportements, consultez [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) et [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="18f8e-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="18f8e-122"><xref:System.TimeSpan> qui spécifie l'intervalle de temps prévu pour la réalisation d'une opération d'ouverture.</span><span class="sxs-lookup"><span data-stu-id="18f8e-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="18f8e-123">Cette valeur doit être supérieure ou égale à <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="18f8e-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="18f8e-124">La valeur par défaut est 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="18f8e-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="18f8e-125"><xref:System.TimeSpan> qui spécifie l'intervalle de temps prévu pour la réalisation d'une opération de réception.</span><span class="sxs-lookup"><span data-stu-id="18f8e-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="18f8e-126">Cette valeur doit être supérieure ou égale à <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="18f8e-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="18f8e-127">La valeur par défaut est 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="18f8e-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="18f8e-128"><xref:System.TimeSpan> qui spécifie l'intervalle de temps prévu pour la réalisation d'une opération d'envoi.</span><span class="sxs-lookup"><span data-stu-id="18f8e-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="18f8e-129">Cette valeur doit être supérieure ou égale à <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="18f8e-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="18f8e-130">La valeur par défaut est 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="18f8e-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18f8e-131">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="18f8e-131">Child Elements</span></span>  
 <span data-ttu-id="18f8e-132">Aucun.</span><span class="sxs-lookup"><span data-stu-id="18f8e-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18f8e-133">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="18f8e-133">Parent Elements</span></span>  
  
|<span data-ttu-id="18f8e-134">Élément</span><span class="sxs-lookup"><span data-stu-id="18f8e-134">Element</span></span>|<span data-ttu-id="18f8e-135">Description</span><span class="sxs-lookup"><span data-stu-id="18f8e-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18f8e-136">\<liaisons ></span><span class="sxs-lookup"><span data-stu-id="18f8e-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="18f8e-137">Cet élément conserve une collection de liaisons standard et personnalisées.</span><span class="sxs-lookup"><span data-stu-id="18f8e-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18f8e-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18f8e-138">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>  
 [<span data-ttu-id="18f8e-139">Guide pratique pour publier les métadonnées d’un service à l’aide d’un fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="18f8e-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="18f8e-140">Publication et récupération de métadonnées sur une liaison personnalisée</span><span class="sxs-lookup"><span data-stu-id="18f8e-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="18f8e-141">Métadonnées</span><span class="sxs-lookup"><span data-stu-id="18f8e-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="18f8e-142">Liaisons</span><span class="sxs-lookup"><span data-stu-id="18f8e-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="18f8e-143">Configuration des liaisons fournies par le système</span><span class="sxs-lookup"><span data-stu-id="18f8e-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="18f8e-144">Utilisation de liaisons pour configurer les Clients et les Services Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="18f8e-144">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="18f8e-145">\<liaison ></span><span class="sxs-lookup"><span data-stu-id="18f8e-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

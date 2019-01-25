---
title: '&lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: c8ca9f37b799087337f7dff6be48744f4f9dea6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703625"
---
# <a name="ltpeertransportgt"></a><span data-ttu-id="9d4e0-102">&lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="9d4e0-102">&lt;peerTransport&gt;</span></span>
<span data-ttu-id="9d4e0-103">Définit un transport d’homologue pour une liaison personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-103">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="9d4e0-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9d4e0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9d4e0-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9d4e0-105">\<bindings></span></span>  
<span data-ttu-id="9d4e0-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9d4e0-106">\<customBinding></span></span>  
<span data-ttu-id="9d4e0-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9d4e0-107">\<binding></span></span>  
<span data-ttu-id="9d4e0-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="9d4e0-108">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4e0-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9d4e0-109">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d4e0-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="9d4e0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9d4e0-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d4e0-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="9d4e0-112">Attributes</span></span>  
  
|<span data-ttu-id="9d4e0-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9d4e0-113">Attribute</span></span>|<span data-ttu-id="9d4e0-114">Description</span><span class="sxs-lookup"><span data-stu-id="9d4e0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d4e0-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="9d4e0-115">listenIpAddress</span></span>|<span data-ttu-id="9d4e0-116">Chaîne indiquant une adresse IP utilisée par le nœud homologue pour écouter les messages TCP.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="9d4e0-117">La valeur par défaut est `null`.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-117">The default is `null`.</span></span>|  
|<span data-ttu-id="9d4e0-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="9d4e0-118">maxBufferPoolSize</span></span>|<span data-ttu-id="9d4e0-119">Entier positif indiquant la taille maximale du pool de mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="9d4e0-120">La valeur par défaut est 524288.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="9d4e0-121">De nombreux éléments de WCF utilisent des mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="9d4e0-122">La création et la destruction des mémoires tampons à chaque utilisation sont chères, tout comme leur nettoyage.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="9d4e0-123">Avec les pools de mémoires tampons, vous pouvez prendre une mémoire tampon du pool, l'utiliser et la retourner au pool une fois que vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="9d4e0-124">Ainsi, la surcharge de la création et de la destruction des mémoires tampons est évitée.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="9d4e0-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="9d4e0-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="9d4e0-126">Entier positif définissant la taille maximale du message (en octets, en-têtes compris).</span><span class="sxs-lookup"><span data-stu-id="9d4e0-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="9d4e0-127">L'expéditeur d'un message reçoit une erreur SOAP si ce message est trop volumineux pour le récepteur.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="9d4e0-128">Ce dernier abandonne le message et crée une entrée d'événement dans le journal de suivi.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="9d4e0-129">La valeur par défaut est 65536.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-129">The default is 65536.</span></span>|  
|<span data-ttu-id="9d4e0-130">port</span><span class="sxs-lookup"><span data-stu-id="9d4e0-130">port</span></span>|<span data-ttu-id="9d4e0-131">Entier indiquant le port d'interface réseau utilisé par cette liaison pour traiter les messages TCP du canal homologue.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="9d4e0-132">Cette valeur doit être comprise entre <xref:System.Net.IPEndPoint.MinPort> et <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="9d4e0-133">La valeur par défaut est 0.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d4e0-134">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="9d4e0-134">Child Elements</span></span>  
  
|<span data-ttu-id="9d4e0-135">Élément</span><span class="sxs-lookup"><span data-stu-id="9d4e0-135">Element</span></span>|<span data-ttu-id="9d4e0-136">Description</span><span class="sxs-lookup"><span data-stu-id="9d4e0-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d4e0-137">\<security></span><span class="sxs-lookup"><span data-stu-id="9d4e0-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="9d4e0-138">Définit les paramètres de sécurité correspondant à ce transport.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="9d4e0-139">Cet élément est de type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d4e0-140">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="9d4e0-140">Parent Elements</span></span>  
  
|<span data-ttu-id="9d4e0-141">Élément</span><span class="sxs-lookup"><span data-stu-id="9d4e0-141">Element</span></span>|<span data-ttu-id="9d4e0-142">Description</span><span class="sxs-lookup"><span data-stu-id="9d4e0-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d4e0-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="9d4e0-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9d4e0-144">Définit toutes les fonctions de liaison d’une liaison personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d4e0-145">Notes</span><span class="sxs-lookup"><span data-stu-id="9d4e0-145">Remarks</span></span>  
 <span data-ttu-id="9d4e0-146">Ce transport ne peut pas être utilisé avec les contrats comportant des opérations de demande/réponse.</span><span class="sxs-lookup"><span data-stu-id="9d4e0-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4e0-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d4e0-147">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9d4e0-148">Transports</span><span class="sxs-lookup"><span data-stu-id="9d4e0-148">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="9d4e0-149">Choix d’un transport</span><span class="sxs-lookup"><span data-stu-id="9d4e0-149">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="9d4e0-150">Liaisons</span><span class="sxs-lookup"><span data-stu-id="9d4e0-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9d4e0-151">Extension de liaisons</span><span class="sxs-lookup"><span data-stu-id="9d4e0-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9d4e0-152">Liaisons personnalisées</span><span class="sxs-lookup"><span data-stu-id="9d4e0-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9d4e0-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9d4e0-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

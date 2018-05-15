---
title: '&lt;announcementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 3ce141d70e17c14facd6aa8560c7b3424a8d9ae8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ltannouncementendpointgt"></a><span data-ttu-id="b90b4-102">&lt;announcementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="b90b4-102">&lt;announcementEndpoint&gt;</span></span>
<span data-ttu-id="b90b4-103">Cet élément de configuration définit un point de terminaison standard avec un contrat d'annonce fixe.</span><span class="sxs-lookup"><span data-stu-id="b90b4-103">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="b90b4-104">Un service peut éventuellement annoncer sa disponibilité en envoyant un message d'annonce en ligne ou hors connexion selon qu'il est respectivement ouvert ou fermé.</span><span class="sxs-lookup"><span data-stu-id="b90b4-104">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="b90b4-105">Un service Windows Communication Foundation (WCF) spécifie les points de terminaison d’annonce dans le [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) élément et utilise le AnnouncementClient pour effectuer les annonces.</span><span class="sxs-lookup"><span data-stu-id="b90b4-105">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="b90b4-106">Un client souhaite écouter l’annonce à partir de l’autre service est en réalité agissant comme un [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service ; par conséquent, vous devez configurer les points de terminaison d’annonce pour le client dans le [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span><span class="sxs-lookup"><span data-stu-id="b90b4-106">A client wishing to listen for the announcement from other service is actually acting as a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="b90b4-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b90b4-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="b90b4-108">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b90b4-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b90b4-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b90b4-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxAnnouncementDelay="Timespan" 
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b90b4-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="b90b4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b90b4-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="b90b4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b90b4-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="b90b4-112">Attributes</span></span>  
  
|<span data-ttu-id="b90b4-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b90b4-113">Attribute</span></span>|<span data-ttu-id="b90b4-114">Description</span><span class="sxs-lookup"><span data-stu-id="b90b4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b90b4-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="b90b4-115">discoveryVersion</span></span>|<span data-ttu-id="b90b4-116">Chaîne qui spécifie l'une des deux versions du protocole WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="b90b4-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="b90b4-117">Les valeurs valides sont WSDiscovery11 et WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="b90b4-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="b90b4-118">Cette valeur est de type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="b90b4-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="b90b4-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="b90b4-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="b90b4-120">Valeur Timespan qui spécifie le délai d'attente maximal du protocole de découverte avant l'envoi d'un message de type Hello.</span><span class="sxs-lookup"><span data-stu-id="b90b4-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="b90b4-121">Les messages attendent pendant un délai aléatoire compris entre 0 et la valeur de cet attribut avant d'être envoyés.</span><span class="sxs-lookup"><span data-stu-id="b90b4-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="b90b4-122">Cet attribut permet de définir un délai court et aléatoire pour empêcher toute tempête de réseau lorsqu'un réseau est en panne et que tous les services reviennent en ligne en même temps.</span><span class="sxs-lookup"><span data-stu-id="b90b4-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="b90b4-123">name</span><span class="sxs-lookup"><span data-stu-id="b90b4-123">name</span></span>|<span data-ttu-id="b90b4-124">Chaîne qui spécifie le nom de la configuration du point de terminaison standard.</span><span class="sxs-lookup"><span data-stu-id="b90b4-124">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="b90b4-125">Le nom est utilisé dans l'attribut `endpointConfiguration` du point de terminaison de service pour lier un point de terminaison standard à sa configuration.</span><span class="sxs-lookup"><span data-stu-id="b90b4-125">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b90b4-126">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="b90b4-126">Child Elements</span></span>  
 <span data-ttu-id="b90b4-127">Aucun.</span><span class="sxs-lookup"><span data-stu-id="b90b4-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b90b4-128">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="b90b4-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b90b4-129">Élément</span><span class="sxs-lookup"><span data-stu-id="b90b4-129">Element</span></span>|<span data-ttu-id="b90b4-130">Description</span><span class="sxs-lookup"><span data-stu-id="b90b4-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b90b4-131">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b90b4-131">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="b90b4-132">Collection de points de terminaison standard qui sont des points de terminaison prédéfinis dont une ou plusieurs propriétés (adresse, liaison, contrat) sont fixes.</span><span class="sxs-lookup"><span data-stu-id="b90b4-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b90b4-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="b90b4-133">Example</span></span>  
 <span data-ttu-id="b90b4-134">L'exemple suivant montre un client qui écoute des messages d'annonce sur HTTP et Peernet.</span><span class="sxs-lookup"><span data-stu-id="b90b4-134">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>  
  <service name="ServiceAnnouncementListener">  
    <endpoint name="httpAnnouncementEndpoint"  
              kind="announcementEndpoint"  
              binding="basicHttpBinding"  
              address="announcements" />  
    <endpoint name="peerNetAnnouncementEndpoint"  
              kind="announcementEndpoint"  
              binding="peerTcpBinding"  
              address="net.p2p://discoveryMesh/multicast"  
              bindingConfiguration="discoveryPeerTcpBindingConfig" />  
  ...  
  </service>  
</services>  
  
<standardEndpoints>  
  <announcementEndpoint>  
    <standardEndpoint name="httpAnnouncementEndpoint"                         
                      version="WSDiscoveryApril2005" />  
    <standardEndpoint name="peerNetAnnouncementEndpoint"                         
                      version="WSDiscoveryApril2005" />  
   </announcementEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b90b4-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b90b4-135">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>

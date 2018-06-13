---
title: '&lt;webMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: fc1f83128dacb588d8179dea95c132da1ab2be91
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755264"
---
# <a name="ltwebmessageencodinggt"></a><span data-ttu-id="65588-102">&lt;webMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="65588-102">&lt;webMessageEncoding&gt;</span></span>
<span data-ttu-id="65588-103">Permet de lire et d’écrire du contenu XML en texte brut, les encodages de message JSON (JavaScript Objet Notation) et du contenu binaire brut dans une liaison Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="65588-103">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
 <span data-ttu-id="65588-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="65588-104">\<system.serviceModel></span></span>  
<span data-ttu-id="65588-105">\<liaisons ></span><span class="sxs-lookup"><span data-stu-id="65588-105">\<bindings></span></span>  
<span data-ttu-id="65588-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="65588-106">\<customBinding></span></span>  
<span data-ttu-id="65588-107">\<liaison ></span><span class="sxs-lookup"><span data-stu-id="65588-107">\<binding></span></span>  
<span data-ttu-id="65588-108">\<webMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="65588-108">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65588-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="65588-109">Syntax</span></span>  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65588-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="65588-110">Attributes and Elements</span></span>  
 <span data-ttu-id="65588-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="65588-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65588-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="65588-112">Attributes</span></span>  
  
|<span data-ttu-id="65588-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="65588-113">Attribute</span></span>|<span data-ttu-id="65588-114">Description</span><span class="sxs-lookup"><span data-stu-id="65588-114">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="65588-115">Quantité maximale de messages pouvant être consultés simultanément sans allouer de nouveaux lecteurs.</span><span class="sxs-lookup"><span data-stu-id="65588-115">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="65588-116">Des pools plus volumineux permettent au système d'être plus tolérant aux pics d'activité au prix d'une plage de travail plus volumineuse.</span><span class="sxs-lookup"><span data-stu-id="65588-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="65588-117">La valeur par défaut est de 64 lecteurs par encodeur interne (texte, JSON, et « brut »).</span><span class="sxs-lookup"><span data-stu-id="65588-117">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="65588-118">L'augmentation de ce nombre entraîne celle de la consommation de mémoire, mais prépare l'encodeur afin de traiter les rafales soudaines de messages entrants. En effet, il peut ainsi utiliser les lecteurs existants du pool au lieu d'en créer.</span><span class="sxs-lookup"><span data-stu-id="65588-118">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="65588-119">Quantité maximale de messages pouvant être envoyés simultanément sans allouer de nouveaux enregistreurs.</span><span class="sxs-lookup"><span data-stu-id="65588-119">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="65588-120">Des pools plus volumineux permettent au système d'être plus tolérant aux pics d'activité au prix d'une plage de travail plus volumineuse.</span><span class="sxs-lookup"><span data-stu-id="65588-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="65588-121">La valeur par défaut est de 16 enregistreurs par encodeur interne (texte, JSON, et « brut »).</span><span class="sxs-lookup"><span data-stu-id="65588-121">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="65588-122">L'augmentation de ce nombre entraîne celle de la consommation de mémoire, mais prépare l'encodeur afin de traiter les rafales soudaines de messages sortants. En effet, il peut ainsi utiliser les writers existants du pool au lieu d'en créer.</span><span class="sxs-lookup"><span data-stu-id="65588-122">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="65588-123">Spécifie l'encodage de jeu de caractères à utiliser pour l'émission de messages sur la liaison.</span><span class="sxs-lookup"><span data-stu-id="65588-123">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="65588-124">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="65588-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="65588-125">-UnicodeFffeTextEncoding : Encodage Unicode Big Endian.</span><span class="sxs-lookup"><span data-stu-id="65588-125">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="65588-126">-Utf16TextEncoding : L’encodage Unicode.</span><span class="sxs-lookup"><span data-stu-id="65588-126">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="65588-127">-Utf8TextEncoding : encodage de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="65588-127">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="65588-128">La valeur par défaut est Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="65588-128">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="65588-129">Cet attribut est de type <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="65588-129">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65588-130">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="65588-130">Child Elements</span></span>  
  
|<span data-ttu-id="65588-131">Élément</span><span class="sxs-lookup"><span data-stu-id="65588-131">Element</span></span>|<span data-ttu-id="65588-132">Description</span><span class="sxs-lookup"><span data-stu-id="65588-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65588-133">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="65588-133">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="65588-134">Définit les contraintes sur la complexité des messages SOAP pouvant être traités par les points de terminaison configurés avec cette liaison.</span><span class="sxs-lookup"><span data-stu-id="65588-134">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="65588-135">Cet élément est de type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="65588-135">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65588-136">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="65588-136">Parent Elements</span></span>  
  
|<span data-ttu-id="65588-137">Élément</span><span class="sxs-lookup"><span data-stu-id="65588-137">Element</span></span>|<span data-ttu-id="65588-138">Description</span><span class="sxs-lookup"><span data-stu-id="65588-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65588-139">\<liaison ></span><span class="sxs-lookup"><span data-stu-id="65588-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="65588-140">Définit toutes les fonctions de liaison d’une liaison personnalisée.</span><span class="sxs-lookup"><span data-stu-id="65588-140">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65588-141">Notes</span><span class="sxs-lookup"><span data-stu-id="65588-141">Remarks</span></span>  
 <span data-ttu-id="65588-142">L'encodage est le processus de transformation d'un message en une séquence d'octets.</span><span class="sxs-lookup"><span data-stu-id="65588-142">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="65588-143">Le décodage est le processus inverse.</span><span class="sxs-lookup"><span data-stu-id="65588-143">Decoding is the reverse process.</span></span> <span data-ttu-id="65588-144">Ces processus nécessitent l'encodage de caractères à titre de spécification.</span><span class="sxs-lookup"><span data-stu-id="65588-144">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="65588-145">L'élément `webMessageEncoding` fonctionne par délégation à une série d'encodeurs internes afin de gérer les données XML de texte brut, les encodages JSON et les données binaires brutes.</span><span class="sxs-lookup"><span data-stu-id="65588-145">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="65588-146">Cette délégation a lieu par le biais d'un encodeur de message composite.</span><span class="sxs-lookup"><span data-stu-id="65588-146">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="65588-147">Cet élément de liaison et son encodeur composite sont utilisés pour contrôler l'encodage dans des scénarios qui n'utilisent pas la messagerie SOAP utilisée par l'élément `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="65588-147">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="65588-148">Ces scénarios incluent les protocoles POX (Plain Old XML) et REST (Representational State Transfer), la syndication RSS (Really Simple Syndication) et Atom, ainsi que le protocole AJAX (Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="65588-148">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="65588-149">L'encodeur de messages composite ne prend pas en charge SOAP ni WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="65588-149">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="65588-150">L'élément de liaison peut être configuré avec un encodage de caractères d'écriture à l'aide de l'attribut `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="65588-150">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="65588-151">La valeur <xref:System.Text.Encoding> fournie spécifie le comportement sur l'écriture pour les cas JSON et XML textuels.</span><span class="sxs-lookup"><span data-stu-id="65588-151">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="65588-152">Lors de la lecture, tous les encodages de texte et de message valides sont maîtrisés.</span><span class="sxs-lookup"><span data-stu-id="65588-152">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="65588-153">`maxReadPoolSize` et `maxWritePoolSize` peuvent également être utilisés pour définir respectivement le nombre maximal de lecteurs et de writers à allouer.</span><span class="sxs-lookup"><span data-stu-id="65588-153">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="65588-154">Par défaut, 64 lecteurs et 16 writers sont alloués.</span><span class="sxs-lookup"><span data-stu-id="65588-154">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="65588-155">Contraintes de complexité par défaut sont également définies à l’aide de la [ \<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) élément pour vous protéger contre une classe d’attaques de déni de service (DOS) qui tentent d’exploiter la complexité des messages pour bloquer le traitement de point de terminaison des attaques ressources.</span><span class="sxs-lookup"><span data-stu-id="65588-155">Default complexity constraints are also set using the [\<readerQuotas>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65588-156">Exemple</span><span class="sxs-lookup"><span data-stu-id="65588-156">Example</span></span>  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65588-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65588-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [<span data-ttu-id="65588-158">Encodage de message</span><span class="sxs-lookup"><span data-stu-id="65588-158">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="65588-159">Sélection d’un encodeur de message</span><span class="sxs-lookup"><span data-stu-id="65588-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="65588-160">Liaisons</span><span class="sxs-lookup"><span data-stu-id="65588-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="65588-161">Extension de liaisons</span><span class="sxs-lookup"><span data-stu-id="65588-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="65588-162">Liaisons personnalisées</span><span class="sxs-lookup"><span data-stu-id="65588-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="65588-163">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="65588-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

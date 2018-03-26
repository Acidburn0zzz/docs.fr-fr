---
title: Encodage de message
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b3040a16b6d167c4f066b2ddbd0a542741f88d62
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2018
---
# <a name="message-encoding"></a><span data-ttu-id="a4310-102">Encodage de message</span><span class="sxs-lookup"><span data-stu-id="a4310-102">Message Encoding</span></span>
<span data-ttu-id="a4310-103">L'encodage est le processus de transformation d'un jeu de caractères Unicode en une séquence d'octets.</span><span class="sxs-lookup"><span data-stu-id="a4310-103">Encoding is the process of transforming a set of Unicode characters into a sequence of bytes.</span></span> <span data-ttu-id="a4310-104">Le décodage est le processus inverse.</span><span class="sxs-lookup"><span data-stu-id="a4310-104">Decoding is the reverse process.</span></span> <span data-ttu-id="a4310-105">Windows Communication Foundation (WCF) inclut trois types d'encodage des messages SOAP : Texte, Binaire et MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="a4310-105">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="a4310-106">La section de configuration `binaryMessageEncoding` spécifie l'encodage de caractères et le suivi des versions de message utilisés pour les messages XML binaires.</span><span class="sxs-lookup"><span data-stu-id="a4310-106">The `binaryMessageEncoding` configuration section specifies the character encoding and message versioning used for binary-based XML messages.</span></span> <span data-ttu-id="a4310-107">L'encodeur de message binaire encode des messages de Windows Communication Foundation (WCF) en binaire sur le câble.</span><span class="sxs-lookup"><span data-stu-id="a4310-107">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="a4310-108">Même si cet encodage permet une transmission très rapide des messages, l'interopérabilité basée sur les normes WS-\* est perdue.</span><span class="sxs-lookup"><span data-stu-id="a4310-108">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
 <span data-ttu-id="a4310-109">La section de configuration `mtomMessageEncoding` spécifie l'encodage de caractères et le suivi des versions de message utilisés pour un message employant un encodage MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="a4310-109">The `mtomMessageEncoding` configuration section specifies the character encoding and message versioning used for a message using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="a4310-110">MTOM est une technologie efficace pour la transmission de données binaires dans les messages de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a4310-110">(MTOM) is an efficient technology for transmitting binary data in Windows Communication Foundation (WCF) messages.</span></span> <span data-ttu-id="a4310-111">L'encodeur MTOM tente de parvenir à un équilibre entre rendement et interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="a4310-111">The MTOM encoder attempts to strike a balance between efficiency and interoperability.</span></span> <span data-ttu-id="a4310-112">L'encodage MTOM transmet la plupart du XML sous forme textuelle, mais optimise les grands blocs de données binaires en les transmettant tels quels, sans conversion en texte.</span><span class="sxs-lookup"><span data-stu-id="a4310-112">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to text.</span></span>  
  
 <span data-ttu-id="a4310-113">La section de configuration `textMessageEncoding` spécifie un encodeur de texte utilisé pour créer des messages textuels sur le câble.</span><span class="sxs-lookup"><span data-stu-id="a4310-113">The `textMessageEncoding` configuration section specifies a text encoder used to create text-based messages on the wire.</span></span> <span data-ttu-id="a4310-114">Les messages produits par cet encodeur sont adaptés à l'interopérabilité basée sur WS-\*.</span><span class="sxs-lookup"><span data-stu-id="a4310-114">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="a4310-115">Les services Web ou les clients de ces services comprennent généralement le XML textuel.</span><span class="sxs-lookup"><span data-stu-id="a4310-115">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="a4310-116">Toutefois, la transmission de grands blocs de données binaires sous forme de texte est la méthode d'encodage de messages XML la moins efficace.</span><span class="sxs-lookup"><span data-stu-id="a4310-116">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4310-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4310-117">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 [<span data-ttu-id="a4310-118">Liaisons</span><span class="sxs-lookup"><span data-stu-id="a4310-118">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a4310-119">Extension de liaisons</span><span class="sxs-lookup"><span data-stu-id="a4310-119">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a4310-120">Liaisons personnalisées</span><span class="sxs-lookup"><span data-stu-id="a4310-120">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a4310-121">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a4310-121">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="a4310-122">Sélection d’un encodeur de message</span><span class="sxs-lookup"><span data-stu-id="a4310-122">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)

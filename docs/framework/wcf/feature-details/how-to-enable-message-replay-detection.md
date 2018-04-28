---
title: 'Comment : activer la détection de relecture des messages'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF security
- replay detection [WCF]
- WCF, custom bindings
- WCF, security
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 55cd4b928c640f506e058f6a441189842bc9b8a3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-enable-message-replay-detection"></a><span data-ttu-id="ef199-102">Comment : activer la détection de relecture des messages</span><span class="sxs-lookup"><span data-stu-id="ef199-102">How to: Enable Message Replay Detection</span></span>
<span data-ttu-id="ef199-103">Une attaque par relecture se produit lorsqu'un intrus copie un flux de messages entre deux correspondants et relit le flux à l'un ou plusieurs des correspondants.</span><span class="sxs-lookup"><span data-stu-id="ef199-103">A replay attack occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="ef199-104">Sauf atténuation, les ordinateurs sujets à l'attaque traiteront le flux comme messages légitimes, ce qui a des conséquences néfastes telles que des ordres redondants d'un élément.</span><span class="sxs-lookup"><span data-stu-id="ef199-104">Unless mitigated, the computers subject to the attack will process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="ef199-105"> la détection de relecture de message, consultez [détection de relecture de Message](http://go.microsoft.com/fwlink/?LinkId=88536).</span><span class="sxs-lookup"><span data-stu-id="ef199-105"> message replay detection, see [Message Replay Detection](http://go.microsoft.com/fwlink/?LinkId=88536).</span></span>  
  
 <span data-ttu-id="ef199-106">La procédure suivante illustre différentes propriétés que vous pouvez utiliser pour contrôler la détection de relecture à l'aide de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef199-106">The following procedure demonstrates various properties that you can use to control replay detection using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
### <a name="to-control-replay-detection-on-the-client-using-code"></a><span data-ttu-id="ef199-107">Pour contrôler la détection de relecture sur le client à l'aide du code</span><span class="sxs-lookup"><span data-stu-id="ef199-107">To control replay detection on the client using code</span></span>  
  
1.  <span data-ttu-id="ef199-108">Créez un <xref:System.ServiceModel.Channels.SecurityBindingElement> à utiliser dans un <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="ef199-108">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="ef199-109">Pour plus d’informations, consultez [Comment : créer un personnalisé de liaison à l’aide de SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="ef199-109">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="ef199-110">L'exemple suivant utilise un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> créé avec le <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> de la classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="ef199-110">The following example uses a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> created with the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span>  
  
2.  <span data-ttu-id="ef199-111">Utilisez la propriété <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> pour retourner une référence à la classe <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> et définir les propriétés suivantes, selon le cas :</span><span class="sxs-lookup"><span data-stu-id="ef199-111">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class and set any of the following properties, as appropriate:</span></span>  
  
    1.  <span data-ttu-id="ef199-112">`DetectReplay`.</span><span class="sxs-lookup"><span data-stu-id="ef199-112">`DetectReplay`.</span></span> <span data-ttu-id="ef199-113">Valeur Boolean.</span><span class="sxs-lookup"><span data-stu-id="ef199-113">A Boolean value.</span></span> <span data-ttu-id="ef199-114">Elle détermine si le client doit détecter les relectures à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="ef199-114">This governs whether the client should detect replays from the server.</span></span> <span data-ttu-id="ef199-115">La valeur par défaut est `true`.</span><span class="sxs-lookup"><span data-stu-id="ef199-115">The default is `true`.</span></span>  
  
    2.  <span data-ttu-id="ef199-116">`MaxClockSkew`.</span><span class="sxs-lookup"><span data-stu-id="ef199-116">`MaxClockSkew`.</span></span> <span data-ttu-id="ef199-117">Valeur <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="ef199-117">A <xref:System.TimeSpan> value.</span></span> <span data-ttu-id="ef199-118">Détermine l'inclinaison d'horloge que peut tolérer le mécanisme de relecture entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ef199-118">Governs how much time skew the replay mechanism can tolerate between the client and the server.</span></span> <span data-ttu-id="ef199-119">Le mécanisme de sécurité examine l'horodatage envoyé et détermine s'il a été envoyé il y a trop longtemps.</span><span class="sxs-lookup"><span data-stu-id="ef199-119">The security mechanism examines the time stamp sent and determines whether it was sent too far back in the past.</span></span> <span data-ttu-id="ef199-120">La valeur par défaut est 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="ef199-120">The default is 5 minutes.</span></span>  
  
    3.  <span data-ttu-id="ef199-121">`ReplayWindow`.</span><span class="sxs-lookup"><span data-stu-id="ef199-121">`ReplayWindow`.</span></span> <span data-ttu-id="ef199-122">Valeur `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="ef199-122">A `TimeSpan` value.</span></span> <span data-ttu-id="ef199-123">Détermine pendant combien de temps un message peut vivre sur le réseau après que le serveur l'a envoyé (par le biais d'intermédiaires) avant d'atteindre le client.</span><span class="sxs-lookup"><span data-stu-id="ef199-123">This governs how long a message can live in the network after the server sends it (through intermediaries) before reaching the client.</span></span> <span data-ttu-id="ef199-124">Le client effectue le suivi des signatures des messages envoyés dans le `ReplayWindow` le plus récent pour les besoins de la détection de relecture.</span><span class="sxs-lookup"><span data-stu-id="ef199-124">The client tracks the signatures of the messages sent within the latest `ReplayWindow` for the purposes of replay detection.</span></span>  
  
    4.  <span data-ttu-id="ef199-125">`ReplayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="ef199-125">`ReplayCacheSize`.</span></span> <span data-ttu-id="ef199-126">Valeur entière.</span><span class="sxs-lookup"><span data-stu-id="ef199-126">An integer value.</span></span> <span data-ttu-id="ef199-127">Le client stocke les signatures du message dans un cache.</span><span class="sxs-lookup"><span data-stu-id="ef199-127">The client stores the signatures of the message in a cache.</span></span> <span data-ttu-id="ef199-128">Ce paramètre spécifie combien de signatures le cache peut stocker.</span><span class="sxs-lookup"><span data-stu-id="ef199-128">This setting specifies how many signatures the cache can store.</span></span> <span data-ttu-id="ef199-129">Si le nombre de messages envoyés dans la dernière fenêtre de relecture atteint la limite de cache, les nouveaux messages sont rejetés jusqu'à ce que les signatures mises en cache les plus anciennes atteignent la limite de temps.</span><span class="sxs-lookup"><span data-stu-id="ef199-129">If the number of messages sent within the last replay window reaches the cache limit, new messages are rejected until the oldest cached signatures reach the time limit.</span></span> <span data-ttu-id="ef199-130">La valeur par défaut est 500000.</span><span class="sxs-lookup"><span data-stu-id="ef199-130">The default is 500000.</span></span>  
  
### <a name="to-control-replay-detection-on-the-service-using-code"></a><span data-ttu-id="ef199-131">Pour contrôler la détection de relecture sur le service à l'aide du code</span><span class="sxs-lookup"><span data-stu-id="ef199-131">To control replay detection on the service using code</span></span>  
  
1.  <span data-ttu-id="ef199-132">Créez un <xref:System.ServiceModel.Channels.SecurityBindingElement> à utiliser dans un <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="ef199-132">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
2.  <span data-ttu-id="ef199-133">Utilisez la propriété <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> pour retourner une référence à la classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> et définissez les propriétés comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="ef199-133">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class, and set the properties as described previously.</span></span>  
  
### <a name="to-control-replay-detection-in-configuration-for-the-client-or-service"></a><span data-ttu-id="ef199-134">Pour contrôler la détection de relecture dans la configuration pour le client ou le service</span><span class="sxs-lookup"><span data-stu-id="ef199-134">To control replay detection in configuration for the client or service</span></span>  
  
1.  <span data-ttu-id="ef199-135">Créer un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="ef199-135">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
2.  <span data-ttu-id="ef199-136">Créez un élément `<security>`.</span><span class="sxs-lookup"><span data-stu-id="ef199-136">Create a `<security>` element.</span></span>  
  
3.  <span data-ttu-id="ef199-137">Créer un [ \<localClientSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) ou [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="ef199-137">Create a [\<localClientSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) or [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).</span></span>  
  
4.  <span data-ttu-id="ef199-138">Définissez les valeurs d'attributs suivantes, le cas échéant : `detectReplays`, `maxClockSkew`, `replayWindow` et `replayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="ef199-138">Set the following attribute values, as appropriate: `detectReplays`, `maxClockSkew`, `replayWindow`, and `replayCacheSize`.</span></span> <span data-ttu-id="ef199-139">L'exemple suivant définit les attributs d'un élément `<localServiceSettings>` et d'un élément `<localClientSettings>` :</span><span class="sxs-lookup"><span data-stu-id="ef199-139">The following example sets the attributes of both a `<localServiceSettings>` and a `<localClientSettings>` element:</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings   
          replayCacheSize="800000"   
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="ef199-140">Exemple</span><span class="sxs-lookup"><span data-stu-id="ef199-140">Example</span></span>  
 <span data-ttu-id="ef199-141">L'exemple suivant crée un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> à l'aide de la méthode <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> et définit les propriétés de relecture de la liaison.</span><span class="sxs-lookup"><span data-stu-id="ef199-141">The following example creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> using the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> method, and sets the replay properties of the binding.</span></span>  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## <a name="scope-of-replay-message-security-only"></a><span data-ttu-id="ef199-142">Étendue de relecture : sécurité de message uniquement</span><span class="sxs-lookup"><span data-stu-id="ef199-142">Scope of Replay: Message Security Only</span></span>  
 <span data-ttu-id="ef199-143">Notez que les procédures suivantes s'appliquent uniquement au mode de sécurité Message.</span><span class="sxs-lookup"><span data-stu-id="ef199-143">Note that the following procedures apply only to Message security mode.</span></span> <span data-ttu-id="ef199-144">Pour les modes Transport et Transport avec informations d'identification de message, les mécanismes de transport détectent les relectures.</span><span class="sxs-lookup"><span data-stu-id="ef199-144">For Transport and Transport with Message Credential modes, the transport mechanisms detect replays.</span></span>  
  
## <a name="secure-conversation-notes"></a><span data-ttu-id="ef199-145">Remarques relatives aux conversations sécurisées</span><span class="sxs-lookup"><span data-stu-id="ef199-145">Secure Conversation Notes</span></span>  
 <span data-ttu-id="ef199-146">Pour les liaisons qui activent les conversations sécurisées, vous pouvez ajuster ces paramètres à la fois pour le canal d’application et pour la liaison du démarrage de conversation sécurisée.</span><span class="sxs-lookup"><span data-stu-id="ef199-146">For bindings that enable secure conversations, you can adjust these settings both for the application channel as well as for the secure conversation bootstrap binding.</span></span> <span data-ttu-id="ef199-147">Par exemple, vous pouvez désactiver les relectures pour le canal d'application mais les activer pour le canal de démarrage qui établit la conversation sécurisée.</span><span class="sxs-lookup"><span data-stu-id="ef199-147">For example, you can turn off replays for the application channel but enable them for the bootstrap channel that establishes the secure conversation.</span></span>  
  
 <span data-ttu-id="ef199-148">Si vous n'utilisez pas de sessions de conversation sécurisée, la détection des relectures n'est pas garantie dans les scénarios de batterie de serveurs et lorsque le processus est recyclé.</span><span class="sxs-lookup"><span data-stu-id="ef199-148">If you do not use secure conversation sessions, replay detection does not guarantee detecting replays in server farm scenarios and when the process is recycled.</span></span> <span data-ttu-id="ef199-149">Cela s'applique aux liaisons fournies par le système suivantes :</span><span class="sxs-lookup"><span data-stu-id="ef199-149">This applies to the following system-provided bindings:</span></span>  
  
-   <span data-ttu-id="ef199-150"><xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="ef199-150"><xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
-   <span data-ttu-id="ef199-151">Objet <xref:System.ServiceModel.WSHttpBinding> avec la propriété <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> définie à la valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="ef199-151"><xref:System.ServiceModel.WSHttpBinding> with the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property set to `false`.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ef199-152">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="ef199-152">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ef199-153">Les espaces de noms suivants sont requis pour compiler le code :</span><span class="sxs-lookup"><span data-stu-id="ef199-153">The following namespaces are required to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
## <a name="see-also"></a><span data-ttu-id="ef199-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef199-154">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [<span data-ttu-id="ef199-155">Conversations sécurisées et sessions sécurisées</span><span class="sxs-lookup"><span data-stu-id="ef199-155">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)  
 [<span data-ttu-id="ef199-156">\<localClientSettings ></span><span class="sxs-lookup"><span data-stu-id="ef199-156">\<localClientSettings></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)  
 [<span data-ttu-id="ef199-157">Guide pratique pour créer une liaison personnalisée à l’aide de SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ef199-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)

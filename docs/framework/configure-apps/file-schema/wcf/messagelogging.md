---
title: '&lt;enregistrement des messages&gt;'
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: e137070b71cf8a481eef3ea16260c135e29b4932
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750685"
---
# <a name="ltmessagelogginggt"></a><span data-ttu-id="101b4-102">&lt;enregistrement des messages&gt;</span><span class="sxs-lookup"><span data-stu-id="101b4-102">&lt;messageLogging&gt;</span></span>
<span data-ttu-id="101b4-103">Cet élément définit les paramètres pour les fonctions d'enregistrement des messages de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="101b4-103">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="101b4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="101b4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="101b4-105">\<diagnostic ></span><span class="sxs-lookup"><span data-stu-id="101b4-105">\<diagnostic></span></span>  
<span data-ttu-id="101b4-106">\<enregistrement des messages ></span><span class="sxs-lookup"><span data-stu-id="101b4-106">\<messageLogging></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="101b4-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="101b4-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
                    maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
                            <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="101b4-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="101b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="101b4-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="101b4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="101b4-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="101b4-110">Attributes</span></span>  
  
|<span data-ttu-id="101b4-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="101b4-111">Attribute</span></span>|<span data-ttu-id="101b4-112">Description</span><span class="sxs-lookup"><span data-stu-id="101b4-112">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="101b4-113">Valeur booléenne qui spécifie si le message entier (en-tête et corps du message) est enregistré.</span><span class="sxs-lookup"><span data-stu-id="101b4-113">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="101b4-114">La valeur par défaut est `false` ce qui signifie que seul l'en-tête de message est enregistré.</span><span class="sxs-lookup"><span data-stu-id="101b4-114">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="101b4-115">Ce paramètre affecte tous les niveaux d'enregistrement de message (messages de service, de transport et malformés).</span><span class="sxs-lookup"><span data-stu-id="101b4-115">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="101b4-116">Valeur booléenne qui spécifie si les messages incorrects sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="101b4-116">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="101b4-117">Les messages incorrects ne comptent pas pour le `maxMessagesToLog`.</span><span class="sxs-lookup"><span data-stu-id="101b4-117">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="101b4-118">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="101b4-118">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="101b4-119">Valeur booléenne qui spécifie si les messages sont suivis au niveau du service (avant les transformations associées au chiffrement et au transport).</span><span class="sxs-lookup"><span data-stu-id="101b4-119">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="101b4-120">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="101b4-120">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="101b4-121">Valeur booléenne qui spécifie si les messages sont suivis au niveau du transport.</span><span class="sxs-lookup"><span data-stu-id="101b4-121">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="101b4-122">Tous les filtres spécifiés dans le fichier de configuration sont appliqués et seuls les messages qui correspondent aux filtres sont suivis.</span><span class="sxs-lookup"><span data-stu-id="101b4-122">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="101b4-123">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="101b4-123">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="101b4-124">Entier positif qui spécifie le nombre maximal de messages à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="101b4-124">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="101b4-125">La valeur par défaut est 1000.</span><span class="sxs-lookup"><span data-stu-id="101b4-125">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="101b4-126">Entier positif qui spécifie la taille maximale, en octets, d'un message à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="101b4-126">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="101b4-127">Les messages plus grands que la limite ne seront pas enregistrés.</span><span class="sxs-lookup"><span data-stu-id="101b4-127">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="101b4-128">Ce paramètre affecte tous les niveaux de suivi.</span><span class="sxs-lookup"><span data-stu-id="101b4-128">This setting affects all trace levels.</span></span> <span data-ttu-id="101b4-129">La valeur par défaut est 262144(0x4000).</span><span class="sxs-lookup"><span data-stu-id="101b4-129">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="101b4-130">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="101b4-130">Child Elements</span></span>  
  
|<span data-ttu-id="101b4-131">Élément</span><span class="sxs-lookup"><span data-stu-id="101b4-131">Element</span></span>|<span data-ttu-id="101b4-132">Description</span><span class="sxs-lookup"><span data-stu-id="101b4-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="101b4-133">filtres</span><span class="sxs-lookup"><span data-stu-id="101b4-133">filters</span></span>|<span data-ttu-id="101b4-134">L'élément `filters` maintient une collection de filtres XPath.</span><span class="sxs-lookup"><span data-stu-id="101b4-134">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="101b4-135">Lorsque l'enregistrement des messages de transport est activé (`logMessagesAtTransportLevel` a la valeur `true`), seuls les messages correspondant aux filtres sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="101b4-135">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="101b4-136">Les filtres sont appliqués uniquement à la couche transport.</span><span class="sxs-lookup"><span data-stu-id="101b4-136">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="101b4-137">Le niveau de service et l'enregistrement du message incorrect ne sont pas affectés par les filtres.</span><span class="sxs-lookup"><span data-stu-id="101b4-137">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="101b4-138">Le seul attribut pour cet élément, `filter`, est un XpathFilter.</span><span class="sxs-lookup"><span data-stu-id="101b4-138">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="101b4-139">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="101b4-139">Parent Elements</span></span>  
  
|<span data-ttu-id="101b4-140">Élément</span><span class="sxs-lookup"><span data-stu-id="101b4-140">Element</span></span>|<span data-ttu-id="101b4-141">Description</span><span class="sxs-lookup"><span data-stu-id="101b4-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="101b4-142">diagnostics</span><span class="sxs-lookup"><span data-stu-id="101b4-142">diagnostics</span></span>|<span data-ttu-id="101b4-143">Définit des paramètres WCF pour l'inspection et le contrôle au moment de l'exécution pour l'administrateur.</span><span class="sxs-lookup"><span data-stu-id="101b4-143">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="101b4-144">Notes</span><span class="sxs-lookup"><span data-stu-id="101b4-144">Remarks</span></span>  
 <span data-ttu-id="101b4-145">Les messages sont entrés à trois niveaux différents dans la pile : les messages de service, de transport et incorrects.</span><span class="sxs-lookup"><span data-stu-id="101b4-145">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="101b4-146">Chaque niveau peut être activé séparément.</span><span class="sxs-lookup"><span data-stu-id="101b4-146">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="101b4-147">Les filtres XPath peuvent être ajoutés afin d'enregistrer des messages spécifiques aux niveaux de transport et de service.</span><span class="sxs-lookup"><span data-stu-id="101b4-147">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="101b4-148">Si aucun filtre n'est défini, tous les messages sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="101b4-148">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="101b4-149">Les filtres sont appliqués uniquement aux en-têtes du message.</span><span class="sxs-lookup"><span data-stu-id="101b4-149">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="101b4-150">Le corps est ignoré.</span><span class="sxs-lookup"><span data-stu-id="101b4-150">The body is ignored.</span></span> <span data-ttu-id="101b4-151">WCF ignore le corps du message pour améliorer la performance.</span><span class="sxs-lookup"><span data-stu-id="101b4-151">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="101b4-152">Si vous souhaitez filtrer le contenu du corps, vous pouvez créer un écouteur personnalisé avec un filtre approprié.</span><span class="sxs-lookup"><span data-stu-id="101b4-152">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="101b4-153">Vous devez créer un écouteur de trace pour activer le suivi de message.</span><span class="sxs-lookup"><span data-stu-id="101b4-153">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="101b4-154">L'écouteur lui-même peut être tout écouteur qui fonctionne avec le <xref:System.Diagnostics> qui effectue le suivi de l'architecture.</span><span class="sxs-lookup"><span data-stu-id="101b4-154">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="101b4-155">L'exemple suivant montre comment créer un écouteur de ce type.</span><span class="sxs-lookup"><span data-stu-id="101b4-155">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
          <source name="System.ServiceModel" switchValue="Verbose">  
              <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="ServiceModel Listener" traceOutputOptions="None" />  
               </listeners>  
        </source>  
            <source name="System.ServiceModel.MessageLogging">  
                <listeners>  
                    <clear />  
                    <add type="System.Diagnostics.DefaultTraceListener" name="Default"  
                        traceOutputOptions="None" />  
                    <add name="MessageLogging Listener" traceOutputOptions="None"/>  
               </listeners>  
        </source>  
    </sources>  
     <sharedListeners>  
            <add initializeData="C:\ItProTools\TraceLog.xml"  
                    type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
                    name="ServiceModel Listener"  
                    traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />  
            <add initializeData="C:\ItProTools\MessageLog.log"  
                    type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
                   name="MessageLogging Listener"  
                   traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />  
    </sharedListeners>  
</system.diagnostics>  
```  
  
## <a name="example"></a><span data-ttu-id="101b4-156">Exemple</span><span class="sxs-lookup"><span data-stu-id="101b4-156">Example</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"  
    logMalformedMessages="true"  
    logMessagesAtServiceLevel="true"  
    logMessagesAtTransportLevel="true"  
    maxMessagesToLog="42"  
    maxSizeOfMessageToLog="42">  
     <filters>  
         <clear />  
     </filters>  
 </messageLogging>  
```  
  
## <a name="see-also"></a><span data-ttu-id="101b4-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="101b4-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 [<span data-ttu-id="101b4-158">Configuration de la journalisation des messages</span><span class="sxs-lookup"><span data-stu-id="101b4-158">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)

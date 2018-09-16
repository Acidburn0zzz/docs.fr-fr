---
title: '&lt;wsFederationHttpBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 943887dd2bf3b309c0663a9eb06e658ee5957844
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649959"
---
# <a name="ltwsfederationhttpbindinggt"></a><span data-ttu-id="127b3-102">&lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="127b3-102">&lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="127b3-103">Définit une liaison qui prend en charge WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="127b3-103">Defines a binding that supports WS-Federation.</span></span>  
  
 <span data-ttu-id="127b3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="127b3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="127b3-105">\<liaisons ></span><span class="sxs-lookup"><span data-stu-id="127b3-105">\<bindings></span></span>  
<span data-ttu-id="127b3-106">wsFederationBinding (élément)</span><span class="sxs-lookup"><span data-stu-id="127b3-106">wsFederationBinding element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="127b3-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="127b3-107">Syntax</span></span>  
  
```xml  
<wsFederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"   
        hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        privacyNoticeAt="Uri"  
        privacyNoticeVersion="Integer"  
        proxyAddress="Uri"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                                 <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="127b3-108">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="127b3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="127b3-109">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="127b3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="127b3-110">Attributs</span><span class="sxs-lookup"><span data-stu-id="127b3-110">Attributes</span></span>  
  
|<span data-ttu-id="127b3-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="127b3-111">Attribute</span></span>|<span data-ttu-id="127b3-112">Description</span><span class="sxs-lookup"><span data-stu-id="127b3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="127b3-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="127b3-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="127b3-114">Valeur booléenne qui indique s'il faut ignorer le serveur proxy pour les adresses locales.</span><span class="sxs-lookup"><span data-stu-id="127b3-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="127b3-115">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="127b3-115">The default is `false`.</span></span>|  
|<span data-ttu-id="127b3-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="127b3-116">closeTimeout</span></span>|<span data-ttu-id="127b3-117"><xref:System.TimeSpan> qui spécifie l'intervalle de temps prévu pour la réalisation d'une opération de fermeture.</span><span class="sxs-lookup"><span data-stu-id="127b3-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="127b3-118">Cette valeur doit être supérieure ou égale à <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="127b3-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="127b3-119">La valeur par défaut est 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="127b3-119">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="127b3-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="127b3-120">hostnameComparisonMode</span></span>|<span data-ttu-id="127b3-121">Spécifie le mode de comparaison du nom d'hôte HTTP utilisé pour analyser des URI.</span><span class="sxs-lookup"><span data-stu-id="127b3-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="127b3-122">Cet attribut est de type <xref:System.ServiceModel.HostNameComparisonMode>, ce qui indique si le nom d'hôte est utilisé pour atteindre le service en cas de correspondance sur l'URI.</span><span class="sxs-lookup"><span data-stu-id="127b3-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="127b3-123">La valeur par défaut est <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, qui ignore le nom d'hôte dans la correspondance.</span><span class="sxs-lookup"><span data-stu-id="127b3-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="127b3-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="127b3-124">maxBufferPoolSize</span></span>|<span data-ttu-id="127b3-125">Entier qui spécifie la taille maximale du pool de mémoires tampons pour cette liaison.</span><span class="sxs-lookup"><span data-stu-id="127b3-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="127b3-126">La valeur par défaut est 524 288 octets (512 x 1024).</span><span class="sxs-lookup"><span data-stu-id="127b3-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="127b3-127">De nombreuses parties de Windows Communication Foundation (WCF) utilisent des mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="127b3-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="127b3-128">La création et la destruction des mémoires tampons à chaque utilisation sont chères, tout comme leur nettoyage.</span><span class="sxs-lookup"><span data-stu-id="127b3-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="127b3-129">Avec les pools de mémoires tampons, vous pouvez prendre une mémoire tampon du pool, l'utiliser et la retourner au pool une fois que vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="127b3-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="127b3-130">Ainsi, la surcharge de la création et de la destruction des mémoires tampons est évitée.</span><span class="sxs-lookup"><span data-stu-id="127b3-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="127b3-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="127b3-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="127b3-132">Entier positif qui spécifie la taille maximale du message, en octets, y compris les en-têtes, pouvant être reçu sur un canal configuré avec cette liaison.</span><span class="sxs-lookup"><span data-stu-id="127b3-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="127b3-133">L'expéditeur d'un message qui dépasse cette limite se verra notifier une erreur SOAP.</span><span class="sxs-lookup"><span data-stu-id="127b3-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="127b3-134">Ce dernier abandonne le message et crée une entrée d'événement dans le journal de suivi.</span><span class="sxs-lookup"><span data-stu-id="127b3-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="127b3-135">La valeur par défaut est 65536.</span><span class="sxs-lookup"><span data-stu-id="127b3-135">The default is 65536.</span></span>|  
|<span data-ttu-id="127b3-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="127b3-136">messageEncoding</span></span>|<span data-ttu-id="127b3-137">Définit l'encodeur utilisé pour encoder le message.</span><span class="sxs-lookup"><span data-stu-id="127b3-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="127b3-138">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="127b3-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="127b3-139">-Text : Utiliser un encodeur de message texte.</span><span class="sxs-lookup"><span data-stu-id="127b3-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="127b3-140">-Mtom : Utiliser un encodeur Message Transmission Organization Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="127b3-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="127b3-141">La valeur par défaut est Text.</span><span class="sxs-lookup"><span data-stu-id="127b3-141">The default is Text.</span></span><br /><br /> <span data-ttu-id="127b3-142">Cet attribut est de type <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="127b3-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="127b3-143">name</span><span class="sxs-lookup"><span data-stu-id="127b3-143">name</span></span>|<span data-ttu-id="127b3-144">Chaîne qui contient le nom de configuration de la liaison.</span><span class="sxs-lookup"><span data-stu-id="127b3-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="127b3-145">Cette valeur doit être unique car elle permet d'identifier la liaison.</span><span class="sxs-lookup"><span data-stu-id="127b3-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="127b3-146">Depuis [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], les liaisons et les comportements ne sont pas obligés d'avoir un nom.</span><span class="sxs-lookup"><span data-stu-id="127b3-146">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="127b3-147">Pour plus d’informations sur la configuration par défaut et les liaisons sans nom et les comportements, consultez [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) et [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="127b3-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="127b3-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="127b3-148">openTimeout</span></span>|<span data-ttu-id="127b3-149"><xref:System.TimeSpan> qui spécifie l'intervalle de temps prévu pour la réalisation d'une opération d'ouverture.</span><span class="sxs-lookup"><span data-stu-id="127b3-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="127b3-150">Cette valeur doit être supérieure ou égale à <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="127b3-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="127b3-151">La valeur par défaut est 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="127b3-151">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="127b3-152">privactyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="127b3-152">privactyNoticeAt</span></span>|<span data-ttu-id="127b3-153">Chaîne qui spécifie un URI dans lequel l'information préalable de confidentialité est située.</span><span class="sxs-lookup"><span data-stu-id="127b3-153">A String that specifies a URI at which the privacy notice is located.</span></span>|  
|<span data-ttu-id="127b3-154">privactyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="127b3-154">privactyNoticeVersion</span></span>|<span data-ttu-id="127b3-155">Entier qui spécifie la version de l'avis de confidentialité actuel.</span><span class="sxs-lookup"><span data-stu-id="127b3-155">An integer that specifies the version of the current privacy notice.</span></span>|  
|<span data-ttu-id="127b3-156">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="127b3-156">proxyAddress</span></span>|<span data-ttu-id="127b3-157">URI qui spécifie l'adresse du proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="127b3-157">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="127b3-158">Si `useDefaultWebProxy` est `true`, ce paramètre doit avoir la valeur `null`.</span><span class="sxs-lookup"><span data-stu-id="127b3-158">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="127b3-159">La valeur par défaut est `null`.</span><span class="sxs-lookup"><span data-stu-id="127b3-159">The default is `null`.</span></span>|  
|<span data-ttu-id="127b3-160">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="127b3-160">receiveTimeout</span></span>|<span data-ttu-id="127b3-161"><xref:System.TimeSpan> qui spécifie l'intervalle de temps prévu pour la réalisation d'une opération de réception.</span><span class="sxs-lookup"><span data-stu-id="127b3-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="127b3-162">Cette valeur doit être supérieure ou égale à <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="127b3-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="127b3-163">La valeur par défaut est 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="127b3-163">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="127b3-164">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="127b3-164">sendTimeout</span></span>|<span data-ttu-id="127b3-165"><xref:System.TimeSpan> qui spécifie l'intervalle de temps prévu pour la réalisation d'une opération d'envoi.</span><span class="sxs-lookup"><span data-stu-id="127b3-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="127b3-166">Cette valeur doit être supérieure ou égale à <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="127b3-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="127b3-167">La valeur par défaut est 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="127b3-167">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="127b3-168">textEncoding</span><span class="sxs-lookup"><span data-stu-id="127b3-168">textEncoding</span></span>|<span data-ttu-id="127b3-169">Définit l'encodage de jeu de caractères à utiliser pour l'émission de messages sur la liaison.</span><span class="sxs-lookup"><span data-stu-id="127b3-169">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="127b3-170">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="127b3-170">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="127b3-171">-BigEndianUnicode : Codage Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="127b3-171">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="127b3-172">-Unicode : encodage de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="127b3-172">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="127b3-173">-UTF8 : encodage 8 bits</span><span class="sxs-lookup"><span data-stu-id="127b3-173">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="127b3-174">La valeur par défaut est UTF8.</span><span class="sxs-lookup"><span data-stu-id="127b3-174">The default is UTF8.</span></span> <span data-ttu-id="127b3-175">Cet attribut est de type <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="127b3-175">This attribute is of type <xref:System.Text.Encoding>..</span></span>|  
|<span data-ttu-id="127b3-176">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="127b3-176">transactionFlow</span></span>|<span data-ttu-id="127b3-177">Valeur booléenne qui spécifie si la liaison prend en charge le flux WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="127b3-177">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="127b3-178">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="127b3-178">The default is `false`.</span></span>|  
|<span data-ttu-id="127b3-179">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="127b3-179">useDefaultWebProxy</span></span>|<span data-ttu-id="127b3-180">Valeur booléenne qui indique si le proxy HTTP du système configuré automatiquement est utilisé.</span><span class="sxs-lookup"><span data-stu-id="127b3-180">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="127b3-181">L'adresse proxy doit être `null` (autrement dit, pas de jeu) si cet attribut est `true`.</span><span class="sxs-lookup"><span data-stu-id="127b3-181">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="127b3-182">La valeur par défaut est `true`.</span><span class="sxs-lookup"><span data-stu-id="127b3-182">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="127b3-183">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="127b3-183">Child Elements</span></span>  
  
|<span data-ttu-id="127b3-184">Élément</span><span class="sxs-lookup"><span data-stu-id="127b3-184">Element</span></span>|<span data-ttu-id="127b3-185">Description</span><span class="sxs-lookup"><span data-stu-id="127b3-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="127b3-186">\<sécurité ></span><span class="sxs-lookup"><span data-stu-id="127b3-186">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="127b3-187">Définit les paramètres de sécurité pour le message.</span><span class="sxs-lookup"><span data-stu-id="127b3-187">Defines the security settings for the message.</span></span> <span data-ttu-id="127b3-188">Cet élément est de type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="127b3-188">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="127b3-189">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="127b3-189">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="127b3-190">Définit les contraintes sur la complexité des messages SOAP pouvant être traités par les points de terminaison configurés avec cette liaison.</span><span class="sxs-lookup"><span data-stu-id="127b3-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="127b3-191">Cet élément est de type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="127b3-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="127b3-192">reliableSession</span><span class="sxs-lookup"><span data-stu-id="127b3-192">reliableSession</span></span>](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="127b3-193">Spécifie si des sessions fiables sont établies entre les points de terminaison du canal.</span><span class="sxs-lookup"><span data-stu-id="127b3-193">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="127b3-194">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="127b3-194">Parent Elements</span></span>  
  
|<span data-ttu-id="127b3-195">Élément</span><span class="sxs-lookup"><span data-stu-id="127b3-195">Element</span></span>|<span data-ttu-id="127b3-196">Description</span><span class="sxs-lookup"><span data-stu-id="127b3-196">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="127b3-197">\<liaisons ></span><span class="sxs-lookup"><span data-stu-id="127b3-197">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="127b3-198">Cet élément conserve une collection de liaisons standard et personnalisées.</span><span class="sxs-lookup"><span data-stu-id="127b3-198">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="127b3-199">Notes</span><span class="sxs-lookup"><span data-stu-id="127b3-199">Remarks</span></span>  
 <span data-ttu-id="127b3-200">La fédération est la capacité à partager des identités sur plusieurs systèmes pour authentification et autorisation.</span><span class="sxs-lookup"><span data-stu-id="127b3-200">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="127b3-201">Ces identités peuvent faire référence à des utilisateurs ou des ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="127b3-201">These identities can refer to users or to machines.</span></span> <span data-ttu-id="127b3-202">Le protocole HTTP fédéré prend en charge la sécurité SOAP, ainsi que la sécurité en mode mixte, mais il ne prend pas en charge exclusivement à l'aide de la sécurité de transport.</span><span class="sxs-lookup"><span data-stu-id="127b3-202">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="127b3-203">Cette liaison prend en charge de Windows Communication Foundation (WCF) pour le protocole WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="127b3-203">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="127b3-204">Les services configurés avec cette liaison doivent utiliser le transport HTTP.</span><span class="sxs-lookup"><span data-stu-id="127b3-204">Services configured with this binding must use the HTTP transport.</span></span>  
  
 <span data-ttu-id="127b3-205">Les liaisons se composent d'une pile d'éléments de liaison.</span><span class="sxs-lookup"><span data-stu-id="127b3-205">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="127b3-206">La pile d’éléments de liaison dans</span><span class="sxs-lookup"><span data-stu-id="127b3-206">The stack of binding elements in</span></span>  
  
 <span data-ttu-id="127b3-207">`wsFederationHttpBinding` est la même que celle contenue dans `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="127b3-207">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>  
  
 <span data-ttu-id="127b3-208">Lorsque [ \<sécurité >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) est défini sur la valeur par défaut <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="127b3-208">when [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>  
  
 <span data-ttu-id="127b3-209">Le `wsFederationHttpBinding` contrôle les détails des paramètres de sécurité de message dans [ \<message >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="127b3-209">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="127b3-210">Notez que le [ \<sécurité >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) élément fournit l’accès uniquement lorsque la sécurité utilisée par la liaison ne peut pas être modifiée une fois que la liaison est créée.</span><span class="sxs-lookup"><span data-stu-id="127b3-210">Note that the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>  
  
 <span data-ttu-id="127b3-211">`wsFederationHttpBinding` fournit également un attribut privactyNoticeAt pour définir et récupérer l'URI où se trouve l'avis de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="127b3-211">The `wsFederationHttpBinding` also provides a privactyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>  
  
 <span data-ttu-id="127b3-212">Maintenir la sécurité de la stratégie est particulièrement important dans les scénarios de fédération.</span><span class="sxs-lookup"><span data-stu-id="127b3-212">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="127b3-213">Il est recommandé d'utiliser un type de sécurité, tel que HTTPS, pour protéger la stratégie d'utilisateurs malveillants.</span><span class="sxs-lookup"><span data-stu-id="127b3-213">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>  
  
 <span data-ttu-id="127b3-214">Dans les scénarios de fédération utilisant cette liaison, la stratégie de service comporte potentiellement des informations importantes, telles que la clé à utiliser pour chiffrer le jeton émis (SAML), le type de revendications à mettre dans le jeton, etc.</span><span class="sxs-lookup"><span data-stu-id="127b3-214">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="127b3-215">Si cette stratégie était falsifiée, un intrus pourrait découvrir la clé du jeton émis, entraînant davantage de falsification, de divulgation d'informations et autres comportements malveillants.</span><span class="sxs-lookup"><span data-stu-id="127b3-215">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="127b3-216">Pour que ce type de problème puisse être évité, la stratégie doit être obtenue de manière sécurisée auprès du service (par exemple à l'aide de HTTPS).</span><span class="sxs-lookup"><span data-stu-id="127b3-216">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>  
  
 <span data-ttu-id="127b3-217">Pour plus d’informations sur cette liaison, consultez [Comment : créer une liaison WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="127b3-217">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="127b3-218">Exemple</span><span class="sxs-lookup"><span data-stu-id="127b3-218">Example</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<wsFederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://foo/bar"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="saml"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</wsFederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="127b3-219">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="127b3-219">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>  
 [<span data-ttu-id="127b3-220">Guide pratique pour créer une liaison WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="127b3-220">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="127b3-221">Liaisons</span><span class="sxs-lookup"><span data-stu-id="127b3-221">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="127b3-222">Configuration des liaisons fournies par le système</span><span class="sxs-lookup"><span data-stu-id="127b3-222">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="127b3-223">Utilisation de liaisons pour configurer les Clients et les Services Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="127b3-223">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="127b3-224">\<liaison ></span><span class="sxs-lookup"><span data-stu-id="127b3-224">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

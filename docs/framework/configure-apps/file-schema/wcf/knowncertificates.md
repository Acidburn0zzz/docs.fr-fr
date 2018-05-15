---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 394ae246ad29a0747f3814b36fae2557b04c235a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="391ff-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="391ff-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="391ff-103">Représente une collection des certificats X.509 fournis pour authentifier des informations d’identification de sécurité publiées à partir d’un service d’émission de jetons de sécurité (STS).</span><span class="sxs-lookup"><span data-stu-id="391ff-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="391ff-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="391ff-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="391ff-105">\<comportements ></span><span class="sxs-lookup"><span data-stu-id="391ff-105">\<behaviors></span></span>  
<span data-ttu-id="391ff-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="391ff-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="391ff-107">\<comportement ></span><span class="sxs-lookup"><span data-stu-id="391ff-107">\<behavior></span></span>  
<span data-ttu-id="391ff-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="391ff-108">\<serviceCredentials></span></span>  
<span data-ttu-id="391ff-109">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="391ff-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="391ff-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="391ff-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="391ff-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="391ff-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="391ff-112">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="391ff-112">Attributes and Elements</span></span>  
 <span data-ttu-id="391ff-113">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="391ff-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="391ff-114">Attributs</span><span class="sxs-lookup"><span data-stu-id="391ff-114">Attributes</span></span>  
 <span data-ttu-id="391ff-115">Aucun.</span><span class="sxs-lookup"><span data-stu-id="391ff-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="391ff-116">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="391ff-116">Child Elements</span></span>  
  
|<span data-ttu-id="391ff-117">Élément</span><span class="sxs-lookup"><span data-stu-id="391ff-117">Element</span></span>|<span data-ttu-id="391ff-118">Description</span><span class="sxs-lookup"><span data-stu-id="391ff-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="391ff-119">\<add></span><span class="sxs-lookup"><span data-stu-id="391ff-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="391ff-120">Ajoute un certificat X.509 à la collection.</span><span class="sxs-lookup"><span data-stu-id="391ff-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="391ff-121">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="391ff-121">Parent Elements</span></span>  
  
|<span data-ttu-id="391ff-122">Élément</span><span class="sxs-lookup"><span data-stu-id="391ff-122">Element</span></span>|<span data-ttu-id="391ff-123">Description</span><span class="sxs-lookup"><span data-stu-id="391ff-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="391ff-124">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="391ff-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="391ff-125">Spécifie un jeton émis en guise d'information d'identification du service.</span><span class="sxs-lookup"><span data-stu-id="391ff-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="391ff-126">Notes</span><span class="sxs-lookup"><span data-stu-id="391ff-126">Remarks</span></span>  
 <span data-ttu-id="391ff-127">Le scénario de jeton émis comporte trois étapes.</span><span class="sxs-lookup"><span data-stu-id="391ff-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="391ff-128">Dans la première phase, un client tente d’accéder à un service est appelée un *service de jeton sécurisé*.</span><span class="sxs-lookup"><span data-stu-id="391ff-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="391ff-129">Le service d'émission de jeton sécurisé authentifie ensuite le client et émet par la suite un jeton au client, généralement un jeton SAML (Security Assertions Markup Language).</span><span class="sxs-lookup"><span data-stu-id="391ff-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="391ff-130">Le client retourne ensuite au service avec le jeton.</span><span class="sxs-lookup"><span data-stu-id="391ff-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="391ff-131">Le service recherche dans le jeton les données lui permettant de l'authentifier, et par conséquent d'authentifier le client.</span><span class="sxs-lookup"><span data-stu-id="391ff-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="391ff-132">Pour authentifier le jeton, le service doit connaître le certificat utilisé par le service d'émission de jeton sécurisé.</span><span class="sxs-lookup"><span data-stu-id="391ff-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="391ff-133">Le [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) élément est le référentiel pour tous les certificats de service de jeton sécurisé ce type.</span><span class="sxs-lookup"><span data-stu-id="391ff-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="391ff-134">Pour ajouter des certificats, utilisez le [ \<knownCertificates > élément](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="391ff-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="391ff-135">Insérer un [ \<Ajouter >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) pour chaque certificat, comme indiqué dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="391ff-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="391ff-136">Par défaut, les certificats doivent être obtenus auprès d'un service d'émission de jeton sécurisé.</span><span class="sxs-lookup"><span data-stu-id="391ff-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="391ff-137">Ces certificats « connus » garantissent que seuls les clients légitimes peuvent accéder à un service.</span><span class="sxs-lookup"><span data-stu-id="391ff-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="391ff-138">Pour passer en revue les conditions requises pour un client soit authentifié par un service fédéré, ainsi que de plus d’informations sur l’utilisation de cet élément de configuration, consultez [Comment : configurer les informations d’identification sur un Service de fédération](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="391ff-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="391ff-139">Pour plus d’informations sur les scénarios de fédération, consultez [fédération et les jetons émis](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="391ff-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="391ff-140">Pour obtenir un exemple qui montre comment remplir la collection dans la configuration, consultez [ \<Ajouter >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="391ff-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="391ff-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="391ff-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="391ff-142">\<add></span><span class="sxs-lookup"><span data-stu-id="391ff-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="391ff-143">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="391ff-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="391ff-144">Comportements de sécurité</span><span class="sxs-lookup"><span data-stu-id="391ff-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="391ff-145">Guide pratique pour configurer des informations d’identification sur un service FS (Federation Service)</span><span class="sxs-lookup"><span data-stu-id="391ff-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="391ff-146">Utilisation des certificats</span><span class="sxs-lookup"><span data-stu-id="391ff-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="391ff-147">Fédération et jetons émis</span><span class="sxs-lookup"><span data-stu-id="391ff-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="391ff-148">\<add></span><span class="sxs-lookup"><span data-stu-id="391ff-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="391ff-149">Sécurisation des services et des clients</span><span class="sxs-lookup"><span data-stu-id="391ff-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

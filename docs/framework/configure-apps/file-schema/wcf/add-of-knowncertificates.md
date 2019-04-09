---
title: <add> de <knownCertificates>
ms.date: 03/30/2017
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
ms.openlocfilehash: 3eb5bf74f909e6036154b7f5f7c6181b09fefbff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077717"
---
# <a name="add-of-knowncertificates"></a><span data-ttu-id="cf175-102">\<Ajouter > de \<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="cf175-102">\<add> of \<knownCertificates></span></span>
<span data-ttu-id="cf175-103">Ajoute un certificat X.509 à la collection de certificats connus.</span><span class="sxs-lookup"><span data-stu-id="cf175-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="cf175-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cf175-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cf175-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="cf175-105">\<behaviors></span></span>  
<span data-ttu-id="cf175-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="cf175-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="cf175-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cf175-107">\<behavior></span></span>  
<span data-ttu-id="cf175-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="cf175-108">\<serviceCredentials></span></span>  
<span data-ttu-id="cf175-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="cf175-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="cf175-110">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="cf175-110">\<knownCertificates></span></span>  
<span data-ttu-id="cf175-111">\<add></span><span class="sxs-lookup"><span data-stu-id="cf175-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf175-112">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cf175-112">Syntax</span></span>  
  
```xml  
<knownCertificates>
   <add findValue="String"
      storeLocation="CurrentUser/LocalMachine"
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>
</knownCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf175-113">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="cf175-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cf175-114">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="cf175-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf175-115">Attributs</span><span class="sxs-lookup"><span data-stu-id="cf175-115">Attributes</span></span>  
  
|<span data-ttu-id="cf175-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="cf175-116">Attribute</span></span>|<span data-ttu-id="cf175-117">Description</span><span class="sxs-lookup"><span data-stu-id="cf175-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf175-118">findValue</span><span class="sxs-lookup"><span data-stu-id="cf175-118">findValue</span></span>|<span data-ttu-id="cf175-119">Chaîne.</span><span class="sxs-lookup"><span data-stu-id="cf175-119">String.</span></span> <span data-ttu-id="cf175-120">La valeur à rechercher.</span><span class="sxs-lookup"><span data-stu-id="cf175-120">The value to search for.</span></span>|  
|<span data-ttu-id="cf175-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="cf175-121">storeLocation</span></span>|<span data-ttu-id="cf175-122">Énumération.</span><span class="sxs-lookup"><span data-stu-id="cf175-122">Enumeration.</span></span> <span data-ttu-id="cf175-123">L'un des deux emplacements du magasin dans lequel effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="cf175-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="cf175-124">storeName</span><span class="sxs-lookup"><span data-stu-id="cf175-124">storeName</span></span>|<span data-ttu-id="cf175-125">Énumération.</span><span class="sxs-lookup"><span data-stu-id="cf175-125">Enumeration.</span></span> <span data-ttu-id="cf175-126">L'un des magasins de systèmes à rechercher.</span><span class="sxs-lookup"><span data-stu-id="cf175-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="cf175-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="cf175-127">x509FindType</span></span>|<span data-ttu-id="cf175-128">Énumération.</span><span class="sxs-lookup"><span data-stu-id="cf175-128">Enumeration.</span></span> <span data-ttu-id="cf175-129">L'un des champs de certificat à rechercher.</span><span class="sxs-lookup"><span data-stu-id="cf175-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="cf175-130">findValue, attribute</span><span class="sxs-lookup"><span data-stu-id="cf175-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="cf175-131">Value</span><span class="sxs-lookup"><span data-stu-id="cf175-131">Value</span></span>|<span data-ttu-id="cf175-132">Description</span><span class="sxs-lookup"><span data-stu-id="cf175-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf175-133">Chaîne</span><span class="sxs-lookup"><span data-stu-id="cf175-133">String</span></span>|<span data-ttu-id="cf175-134">La valeur dépend du champ (spécifié par l'attribut X509FindType) qui est recherché.</span><span class="sxs-lookup"><span data-stu-id="cf175-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="cf175-135">Par exemple, lors de la recherche d'une empreinte numérique, la valeur doit être une chaîne de nombres hexadécimaux.</span><span class="sxs-lookup"><span data-stu-id="cf175-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="cf175-136">x509FindType, attribut</span><span class="sxs-lookup"><span data-stu-id="cf175-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="cf175-137">Value</span><span class="sxs-lookup"><span data-stu-id="cf175-137">Value</span></span>|<span data-ttu-id="cf175-138">Description</span><span class="sxs-lookup"><span data-stu-id="cf175-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf175-139">Énumération</span><span class="sxs-lookup"><span data-stu-id="cf175-139">Enumeration</span></span>|<span data-ttu-id="cf175-140">Les valeurs incluent : FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="cf175-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="cf175-141">storeLocation, attribut</span><span class="sxs-lookup"><span data-stu-id="cf175-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="cf175-142">Value</span><span class="sxs-lookup"><span data-stu-id="cf175-142">Value</span></span>|<span data-ttu-id="cf175-143">Description</span><span class="sxs-lookup"><span data-stu-id="cf175-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf175-144">Énumération</span><span class="sxs-lookup"><span data-stu-id="cf175-144">Enumeration</span></span>|<span data-ttu-id="cf175-145">CurrentUser ou LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="cf175-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="cf175-146">storeName, attribut</span><span class="sxs-lookup"><span data-stu-id="cf175-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="cf175-147">Value</span><span class="sxs-lookup"><span data-stu-id="cf175-147">Value</span></span>|<span data-ttu-id="cf175-148">Description</span><span class="sxs-lookup"><span data-stu-id="cf175-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf175-149">Énumération</span><span class="sxs-lookup"><span data-stu-id="cf175-149">Enumeration</span></span>|<span data-ttu-id="cf175-150">Les valeurs incluent : AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, racine, TrustedPeople et TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="cf175-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf175-151">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="cf175-151">Child Elements</span></span>  
 <span data-ttu-id="cf175-152">Aucun.</span><span class="sxs-lookup"><span data-stu-id="cf175-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf175-153">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="cf175-153">Parent Elements</span></span>  
  
|<span data-ttu-id="cf175-154">Élément</span><span class="sxs-lookup"><span data-stu-id="cf175-154">Element</span></span>|<span data-ttu-id="cf175-155">Description</span><span class="sxs-lookup"><span data-stu-id="cf175-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf175-156">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="cf175-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="cf175-157">Représente une collection des certificats X.509 fournis par un service d’émission de jetons de sécurité (STS) pour valider les jetons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="cf175-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf175-158">Notes</span><span class="sxs-lookup"><span data-stu-id="cf175-158">Remarks</span></span>  
 <span data-ttu-id="cf175-159">Le scénario de jeton émis comporte trois étapes.</span><span class="sxs-lookup"><span data-stu-id="cf175-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="cf175-160">Dans la première phase, un client tente d’accéder à un service est appelé un *secure token service*.</span><span class="sxs-lookup"><span data-stu-id="cf175-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="cf175-161">Le service d'émission de jeton sécurisé authentifie ensuite le client et émet par la suite un jeton au client, généralement un jeton SAML (Security Assertions Markup Language).</span><span class="sxs-lookup"><span data-stu-id="cf175-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="cf175-162">Le client retourne ensuite au service avec le jeton.</span><span class="sxs-lookup"><span data-stu-id="cf175-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="cf175-163">Le service recherche dans le jeton les données lui permettant de l'authentifier, et par conséquent d'authentifier le client.</span><span class="sxs-lookup"><span data-stu-id="cf175-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="cf175-164">Pour authentifier le jeton, le service doit connaître le certificat utilisé par le service d'émission de jeton sécurisé.</span><span class="sxs-lookup"><span data-stu-id="cf175-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="cf175-165">Le [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) élément est le référentiel pour les certificats de service de jeton sécurisé ce type.</span><span class="sxs-lookup"><span data-stu-id="cf175-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="cf175-166">Pour ajouter des certificats, utilisez le [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span><span class="sxs-lookup"><span data-stu-id="cf175-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="cf175-167">Insérer un [ \<Ajouter > élément \<knownCertificates > élément](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) pour chaque certificat, comme illustré dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="cf175-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 <span data-ttu-id="cf175-168">Par défaut, les certificats doivent être obtenus auprès d'un service d'émission de jeton sécurisé.</span><span class="sxs-lookup"><span data-stu-id="cf175-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="cf175-169">Ces certificats « connus » garantissent que seuls les clients légitimes peuvent accéder à un service.</span><span class="sxs-lookup"><span data-stu-id="cf175-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="cf175-170">Pour passer en revue les conditions requises pour un client d’être authentifiés par un service fédéré, ainsi que plus d’informations sur l’utilisation de cet élément de configuration, consultez [Comment : Configurer les informations d’identification sur un Service de fédération](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="cf175-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="cf175-171">Pour plus d’informations sur les scénarios fédérés, consultez [fédération et jetons émis](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="cf175-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf175-172">Exemple</span><span class="sxs-lookup"><span data-stu-id="cf175-172">Example</span></span>  
 <span data-ttu-id="cf175-173">L'exemple suivant ajoute un certificat au référentiel pour tous les certificats STS.</span><span class="sxs-lookup"><span data-stu-id="cf175-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <serviceCredentials>
      <issuedTokenAuthentication>
        <knownCertificates>
          <add findValue="www.contoso.com"
               storeLocation="LocalMachine"
               storeName="CertificateAuthority"
               x509FindType="FindByIssuerName" />
        </knownCertificates>
      </issuedTokenAuthentication>
    </serviceCredentials>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="cf175-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf175-174">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>
- <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>
- [<span data-ttu-id="cf175-175">\<knownCertificates></span><span class="sxs-lookup"><span data-stu-id="cf175-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)
- [<span data-ttu-id="cf175-176">Utilisation des certificats</span><span class="sxs-lookup"><span data-stu-id="cf175-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="cf175-177">Fédération et jetons émis</span><span class="sxs-lookup"><span data-stu-id="cf175-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="cf175-178">Procédure : configurer des informations d’identification sur un service de fédération</span><span class="sxs-lookup"><span data-stu-id="cf175-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="cf175-179">Sécurisation des services et des clients</span><span class="sxs-lookup"><span data-stu-id="cf175-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

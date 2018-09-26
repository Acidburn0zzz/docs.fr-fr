---
title: '&lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 4cd86a858223997ed379d2b26518e14f6d3ebb3e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47188698"
---
# <a name="ltaddgt"></a><span data-ttu-id="6a1df-102">&lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="6a1df-102">&lt;add&gt;</span></span>
<span data-ttu-id="6a1df-103">Ajoute le Gestionnaire de jetons de sécurité spécifié à la collection de gestionnaires de jetons.</span><span class="sxs-lookup"><span data-stu-id="6a1df-103">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="6a1df-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6a1df-104">\<system.identityModel></span></span>  
<span data-ttu-id="6a1df-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6a1df-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6a1df-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6a1df-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6a1df-107">\<add></span><span class="sxs-lookup"><span data-stu-id="6a1df-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1df-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6a1df-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a1df-109">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="6a1df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6a1df-110">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="6a1df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a1df-111">Attributs</span><span class="sxs-lookup"><span data-stu-id="6a1df-111">Attributes</span></span>  
  
|<span data-ttu-id="6a1df-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="6a1df-112">Attribute</span></span>|<span data-ttu-id="6a1df-113">Description</span><span class="sxs-lookup"><span data-stu-id="6a1df-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a1df-114">type</span><span class="sxs-lookup"><span data-stu-id="6a1df-114">type</span></span>|<span data-ttu-id="6a1df-115">Le nom de type CLR de gestionnaire de jetons à ajouter.</span><span class="sxs-lookup"><span data-stu-id="6a1df-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="6a1df-116">Pour plus d’informations sur la façon de spécifier le `type` d’attribut, consultez [références de Type personnalisé](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="6a1df-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a1df-117">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="6a1df-117">Child Elements</span></span>  
  
|<span data-ttu-id="6a1df-118">Élément</span><span class="sxs-lookup"><span data-stu-id="6a1df-118">Element</span></span>|<span data-ttu-id="6a1df-119">Description</span><span class="sxs-lookup"><span data-stu-id="6a1df-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a1df-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="6a1df-120">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="6a1df-121">Fournit une configuration pour le <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe ou une classe dérivée d’un de ces classes.</span><span class="sxs-lookup"><span data-stu-id="6a1df-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="6a1df-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="6a1df-122">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="6a1df-123">Fournit une configuration pour la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe ou les classes dérivées.</span><span class="sxs-lookup"><span data-stu-id="6a1df-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="6a1df-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="6a1df-124">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="6a1df-125">Fournit une configuration pour la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe ou les classes dérivées.</span><span class="sxs-lookup"><span data-stu-id="6a1df-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="6a1df-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="6a1df-126">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="6a1df-127">Fournit une configuration facultative pour le <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe ou les classes dérivées.</span><span class="sxs-lookup"><span data-stu-id="6a1df-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a1df-128">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="6a1df-128">Parent Elements</span></span>  
  
|<span data-ttu-id="6a1df-129">Élément</span><span class="sxs-lookup"><span data-stu-id="6a1df-129">Element</span></span>|<span data-ttu-id="6a1df-130">Description</span><span class="sxs-lookup"><span data-stu-id="6a1df-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a1df-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6a1df-131">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="6a1df-132">Spécifie une collection de gestionnaires de jetons de sécurité qui sont inscrits avec le point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6a1df-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a1df-133">Notes</span><span class="sxs-lookup"><span data-stu-id="6a1df-133">Remarks</span></span>  
 <span data-ttu-id="6a1df-134">Le `<add>` élément peut prendre un seul élément enfant qui spécifie la configuration pour le Gestionnaire de jetons.</span><span class="sxs-lookup"><span data-stu-id="6a1df-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="6a1df-135">Cela dépend de la classe de gestionnaire référencée ou non par le biais du `type` attribut de la `<add>` élément prend en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6a1df-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="6a1df-136">Les classes de gestionnaire de jetons qui fournissent cette fonctionnalité doivent exposer un constructeur qui accepte un <xref:System.Xml.XmlElement> objet.</span><span class="sxs-lookup"><span data-stu-id="6a1df-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="6a1df-137">Plusieurs des classes de gestionnaire de jetons de sécurité intégrés ne fournissent pas cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6a1df-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="6a1df-138">Ces classes sont <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, et <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="6a1df-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a1df-139">La collection de gestionnaires de jetons ne peut contenir qu’un seul gestionnaire de tout type donné.</span><span class="sxs-lookup"><span data-stu-id="6a1df-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="6a1df-140">Cela signifie, par exemple, que si vous souhaitez ajouter un gestionnaire qui est dérivé de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe à la collection, vous devez d’abord supprimer la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, qui n’est présent par défaut, à partir de la collection.</span><span class="sxs-lookup"><span data-stu-id="6a1df-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="6a1df-141">Vous pouvez utiliser la [ \<Supprimer >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) élément à supprimer un gestionnaire unique à partir de la collection ou utilisez le [ \<Effacer >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) élément à supprimer tous les gestionnaires de la collection.</span><span class="sxs-lookup"><span data-stu-id="6a1df-141">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="6a1df-142">Les paramètres spécifiés sur un gestionnaire de remplacent les paramètres équivalents spécifiés sur la collection de gestionnaires de jetons sous le [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) élément et ceux spécifiés au niveau du service sous le [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) élément.</span><span class="sxs-lookup"><span data-stu-id="6a1df-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a1df-143">Exemple</span><span class="sxs-lookup"><span data-stu-id="6a1df-143">Example</span></span>  
 <span data-ttu-id="6a1df-144">Le code XML suivant illustre l’utilisation de la `<add>` et `<remove>` éléments pour remplacer le Gestionnaire de jetons de session par défaut par un gestionnaire de jetons de session personnalisée.</span><span class="sxs-lookup"><span data-stu-id="6a1df-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="6a1df-145">Le code XML provient de la `ClaimsAwareWebFarm` exemple.</span><span class="sxs-lookup"><span data-stu-id="6a1df-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

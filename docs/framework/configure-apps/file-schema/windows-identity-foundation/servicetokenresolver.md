---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c25ea1fc32c93e7eb57ef8ed06d6f786ae0a670e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="f2719-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="f2719-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="f2719-103">Inscrit le résolveur de jeton de service qui est utilisé par les gestionnaires de la collection du Gestionnaire de jetons.</span><span class="sxs-lookup"><span data-stu-id="f2719-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f2719-104">Le programme de résolution de jeton de service permet de résoudre le jeton de chiffrement sur les jetons et les messages entrant.</span><span class="sxs-lookup"><span data-stu-id="f2719-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="f2719-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f2719-105">\<system.identityModel></span></span>  
<span data-ttu-id="f2719-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f2719-106">\<identityConfiguration></span></span>  
<span data-ttu-id="f2719-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f2719-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f2719-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f2719-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="f2719-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="f2719-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2719-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f2719-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2719-111">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="f2719-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f2719-112">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="f2719-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2719-113">Attributs</span><span class="sxs-lookup"><span data-stu-id="f2719-113">Attributes</span></span>  
  
|<span data-ttu-id="f2719-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="f2719-114">Attribute</span></span>|<span data-ttu-id="f2719-115">Description</span><span class="sxs-lookup"><span data-stu-id="f2719-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2719-116">type</span><span class="sxs-lookup"><span data-stu-id="f2719-116">type</span></span>|<span data-ttu-id="f2719-117">Spécifie le type du programme de résolution de jeton de service.</span><span class="sxs-lookup"><span data-stu-id="f2719-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="f2719-118">Soit le <xref:System.IdentityModel.Selectors.SecurityTokenResolver> ou un type qui dérive de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="f2719-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="f2719-119">Pour plus d’informations sur la façon de spécifier le `type` d’attribut, consultez [références de Type personnalisé].</span><span class="sxs-lookup"><span data-stu-id="f2719-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="f2719-120">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="f2719-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2719-121">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="f2719-121">Child Elements</span></span>  
 <span data-ttu-id="f2719-122">Aucun</span><span class="sxs-lookup"><span data-stu-id="f2719-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2719-123">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="f2719-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f2719-124">Élément</span><span class="sxs-lookup"><span data-stu-id="f2719-124">Element</span></span>|<span data-ttu-id="f2719-125">Description</span><span class="sxs-lookup"><span data-stu-id="f2719-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2719-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f2719-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="f2719-127">Fournit des gestionnaires de jetons de configuration pour une collection de sécurité.</span><span class="sxs-lookup"><span data-stu-id="f2719-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2719-128">Notes</span><span class="sxs-lookup"><span data-stu-id="f2719-128">Remarks</span></span>  
 <span data-ttu-id="f2719-129">Le programme de résolution de jeton de service peut être utilisé pour résoudre le jeton de chiffrement sur les jetons et les messages entrant.</span><span class="sxs-lookup"><span data-stu-id="f2719-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="f2719-130">Il est utilisé pour récupérer la clé doit être utilisée pour déchiffrer les jetons entrants.</span><span class="sxs-lookup"><span data-stu-id="f2719-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="f2719-131">Vous devez spécifier le `type` attribut.</span><span class="sxs-lookup"><span data-stu-id="f2719-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="f2719-132">Le type spécifié peut être <xref:System.IdentityModel.Selectors.SecurityTokenResolver> ou un type personnalisé qui dérive de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="f2719-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="f2719-133">Certains gestionnaires de jetons permettent de spécifier les paramètres de résolution de jeton de service dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="f2719-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="f2719-134">Paramètres de gestionnaires de jetons individuels remplacent celles spécifiées dans la collection de gestionnaire de jetons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="f2719-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2719-135">En spécifiant le `<serviceTokenResolver>` élément comme un élément enfant de le [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) l’élément a été déconseillée, mais est toujours prise en charge pour la compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="f2719-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="f2719-136">Paramètres de la `<securityTokenHandlerConfiguration>` élément remplacent celles sur le `<identityConfiguration>` élément.</span><span class="sxs-lookup"><span data-stu-id="f2719-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2719-137">Exemple</span><span class="sxs-lookup"><span data-stu-id="f2719-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```

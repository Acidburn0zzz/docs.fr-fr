---
title: '&lt;remove&gt;'
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: dfea0b0eb4b133308f10b523a659cc00f87252b8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755071"
---
# <a name="ltremovegt"></a><span data-ttu-id="7e65c-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="7e65c-102">&lt;remove&gt;</span></span>
<span data-ttu-id="7e65c-103">Supprime le Gestionnaire de jetons de sécurité spécifié de la collection de gestionnaires de jetons.</span><span class="sxs-lookup"><span data-stu-id="7e65c-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="7e65c-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7e65c-104">\<system.identityModel></span></span>  
<span data-ttu-id="7e65c-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7e65c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="7e65c-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7e65c-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7e65c-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="7e65c-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e65c-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7e65c-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e65c-109">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="7e65c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7e65c-110">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="7e65c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e65c-111">Attributs</span><span class="sxs-lookup"><span data-stu-id="7e65c-111">Attributes</span></span>  
  
|<span data-ttu-id="7e65c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="7e65c-112">Attribute</span></span>|<span data-ttu-id="7e65c-113">Description</span><span class="sxs-lookup"><span data-stu-id="7e65c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e65c-114">type</span><span class="sxs-lookup"><span data-stu-id="7e65c-114">type</span></span>|<span data-ttu-id="7e65c-115">Le nom de type CLR du Gestionnaire de jetons à supprimer.</span><span class="sxs-lookup"><span data-stu-id="7e65c-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="7e65c-116">Pour plus d’informations sur la façon de spécifier le `type` d’attribut, consultez [références de Type personnalisé](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="7e65c-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="7e65c-117">Obligatoire.</span><span class="sxs-lookup"><span data-stu-id="7e65c-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e65c-118">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="7e65c-118">Child Elements</span></span>  
 <span data-ttu-id="7e65c-119">Aucun</span><span class="sxs-lookup"><span data-stu-id="7e65c-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e65c-120">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="7e65c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7e65c-121">Élément</span><span class="sxs-lookup"><span data-stu-id="7e65c-121">Element</span></span>|<span data-ttu-id="7e65c-122">Description</span><span class="sxs-lookup"><span data-stu-id="7e65c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e65c-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7e65c-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="7e65c-124">Spécifie une collection de gestionnaires de jetons de sécurité qui sont enregistrés avec le point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="7e65c-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7e65c-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="7e65c-125">Example</span></span>  
 <span data-ttu-id="7e65c-126">Le code XML suivant illustre l’utilisation de la `<add>` et `<remove>` éléments pour remplacer le Gestionnaire de jetons de session par défaut avec un gestionnaire de jeton de session personnalisée.</span><span class="sxs-lookup"><span data-stu-id="7e65c-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="7e65c-127">Le code XML provient de la `ClaimsAwareWebFarm` exemple.</span><span class="sxs-lookup"><span data-stu-id="7e65c-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

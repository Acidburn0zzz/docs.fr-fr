---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c1c4630e6191dbbe02688a4e4a9db9e18b8d36d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508415"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="669c0-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="669c0-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="669c0-103">Contient une collection d’éléments de configuration qui spécifient l’utilisateur des comptes pour les processus qui hébergent les services Windows Communication Foundation (WCF) et qui disposent d’accès à la connexion au service de partage.</span><span class="sxs-lookup"><span data-stu-id="669c0-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="669c0-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="669c0-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="669c0-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="669c0-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="669c0-106">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="669c0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="669c0-107">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="669c0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="669c0-108">Attributs</span><span class="sxs-lookup"><span data-stu-id="669c0-108">Attributes</span></span>  
 <span data-ttu-id="669c0-109">Aucun.</span><span class="sxs-lookup"><span data-stu-id="669c0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="669c0-110">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="669c0-110">Child Elements</span></span>  
  
|<span data-ttu-id="669c0-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="669c0-111">Attribute</span></span>|<span data-ttu-id="669c0-112">Description</span><span class="sxs-lookup"><span data-stu-id="669c0-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="669c0-113">\<add></span><span class="sxs-lookup"><span data-stu-id="669c0-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="669c0-114">Ajoute un compte d’utilisateur pour les processus qui hébergent des services WCF et qui disposent d’accès à la connexion au service de partage</span><span class="sxs-lookup"><span data-stu-id="669c0-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="669c0-115">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="669c0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="669c0-116">Élément</span><span class="sxs-lookup"><span data-stu-id="669c0-116">Element</span></span>|<span data-ttu-id="669c0-117">Description</span><span class="sxs-lookup"><span data-stu-id="669c0-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="669c0-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="669c0-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="669c0-119">Spécifie les paramètres de configuration pour le canal du réseau ou les services de partage TCP.</span><span class="sxs-lookup"><span data-stu-id="669c0-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="669c0-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="669c0-120">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>

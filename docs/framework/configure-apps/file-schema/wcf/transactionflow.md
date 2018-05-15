---
title: '&lt;transactionFlow&gt;'
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c708098676e5634281e29c17639304a1a9cf5afe
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="a21ee-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="a21ee-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="a21ee-103">Spécifie le support du flux de la transaction pour la liaison personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a21ee-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="a21ee-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a21ee-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a21ee-105">\<liaisons ></span><span class="sxs-lookup"><span data-stu-id="a21ee-105">\<bindings></span></span>  
<span data-ttu-id="a21ee-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a21ee-106">\<customBinding></span></span>  
<span data-ttu-id="a21ee-107">\<liaison ></span><span class="sxs-lookup"><span data-stu-id="a21ee-107">\<binding></span></span>  
<span data-ttu-id="a21ee-108">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="a21ee-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a21ee-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a21ee-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a21ee-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="a21ee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a21ee-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="a21ee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a21ee-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="a21ee-112">Attributes</span></span>  
  
|<span data-ttu-id="a21ee-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a21ee-113">Attribute</span></span>|<span data-ttu-id="a21ee-114">Description</span><span class="sxs-lookup"><span data-stu-id="a21ee-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a21ee-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="a21ee-115">transactionProtocol</span></span>|<span data-ttu-id="a21ee-116">Spécifie le protocole de transaction à utiliser.</span><span class="sxs-lookup"><span data-stu-id="a21ee-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="a21ee-117">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a21ee-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a21ee-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="a21ee-118">-   OleTransactions</span></span><br /><span data-ttu-id="a21ee-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="a21ee-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="a21ee-120">La valeur par défaut est OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="a21ee-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="a21ee-121">Cet attribut est de type <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="a21ee-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a21ee-122">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="a21ee-122">Child Elements</span></span>  
 <span data-ttu-id="a21ee-123">Aucun.</span><span class="sxs-lookup"><span data-stu-id="a21ee-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a21ee-124">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="a21ee-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a21ee-125">Élément</span><span class="sxs-lookup"><span data-stu-id="a21ee-125">Element</span></span>|<span data-ttu-id="a21ee-126">Description</span><span class="sxs-lookup"><span data-stu-id="a21ee-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a21ee-127">\<liaison ></span><span class="sxs-lookup"><span data-stu-id="a21ee-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a21ee-128">Définit toutes les fonctions de liaison d’une liaison personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a21ee-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a21ee-129">Notes</span><span class="sxs-lookup"><span data-stu-id="a21ee-129">Remarks</span></span>  
 <span data-ttu-id="a21ee-130">Cet élément vous permet d’activer ou de désactiver le flux de transactions entrantes dans les paramètres de liaison d’un point de terminaison, ainsi que de spécifier le format de protocole souhaité pour les transactions entrantes.</span><span class="sxs-lookup"><span data-stu-id="a21ee-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="a21ee-131">Pour plus d’informations sur l’utilisation de cet élément de configuration, consultez [Configuration des transactions ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) et [l’activation de flux de Transaction](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="a21ee-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a21ee-132">Lors de l'utilisation du protocole `OleTransactions` pour faire passer les transactions d'un point de terminaison vers un autre, le délai d'attente de transaction peut se perdre si le point de terminaison de destination tente un nouveau flux à l'aide d'un autre protocole que `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="a21ee-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="a21ee-133">Cela peut provoquer l'expiration de tous les nœuds de niveau inférieur après le tronçon OleTransactions selon un délai plus long que prévu.</span><span class="sxs-lookup"><span data-stu-id="a21ee-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a21ee-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a21ee-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="a21ee-135">Configuration des transactions ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a21ee-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="a21ee-136">Activation du flux de transaction</span><span class="sxs-lookup"><span data-stu-id="a21ee-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="a21ee-137">Liaisons</span><span class="sxs-lookup"><span data-stu-id="a21ee-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a21ee-138">Extension de liaisons</span><span class="sxs-lookup"><span data-stu-id="a21ee-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a21ee-139">Liaisons personnalisées</span><span class="sxs-lookup"><span data-stu-id="a21ee-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a21ee-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a21ee-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

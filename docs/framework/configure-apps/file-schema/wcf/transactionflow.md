---
title: '&lt;transactionFlow&gt;'
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c708098676e5634281e29c17639304a1a9cf5afe
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748709"
---
# <a name="lttransactionflowgt"></a>&lt;transactionFlow&gt;
Spécifie le support du flux de la transaction pour la liaison personnalisée.  
  
 \<system.serviceModel>  
\<liaisons >  
\<customBinding >  
\<liaison >  
\<transactionFlow >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|transactionProtocol|Spécifie le protocole de transaction à utiliser. Les valeurs valides sont les suivantes :<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> La valeur par défaut est OleTransactions.<br /><br /> Cet attribut est de type <xref:System.ServiceModel.TransactionProtocol>.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<liaison >](../../../../../docs/framework/misc/binding.md)|Définit toutes les fonctions de liaison d’une liaison personnalisée.|  
  
## <a name="remarks"></a>Notes  
 Cet élément vous permet d’activer ou de désactiver le flux de transactions entrantes dans les paramètres de liaison d’un point de terminaison, ainsi que de spécifier le format de protocole souhaité pour les transactions entrantes. Pour plus d’informations sur l’utilisation de cet élément de configuration, consultez [Configuration des transactions ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) et [l’activation de flux de Transaction](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
> [!CAUTION]
>  Lors de l'utilisation du protocole `OleTransactions` pour faire passer les transactions d'un point de terminaison vers un autre, le délai d'attente de transaction peut se perdre si le point de terminaison de destination tente un nouveau flux à l'aide d'un autre protocole que `OleTransactions`. Cela peut provoquer l'expiration de tous les nœuds de niveau inférieur après le tronçon OleTransactions selon un délai plus long que prévu.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Configuration des transactions ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [Activation du flux de transaction](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [Liaisons](../../../../../docs/framework/wcf/bindings.md)  
 [Extension de liaisons](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Liaisons personnalisées](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

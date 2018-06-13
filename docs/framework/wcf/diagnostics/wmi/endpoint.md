---
title: Point de terminaison
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 5d597e9e029cec3552c94b47a64dfbf36d933e67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487644"
---
# <a name="endpoint"></a>Point de terminaison
Point de terminaison  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a>Méthodes  
 La classe Endpoint définit la méthode suivante.  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetOperationCounterInstanceName](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|Récupère le nom d'instance du compteur de performance d'opération|  
  
## <a name="properties"></a>Propriétés  
 La classe Endpoint a les propriétés suivantes :  
  
### <a name="address"></a>Address  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 URI qui contient l'adresse du point de terminaison.  
  
### <a name="addressheaders"></a>AddressHeaders  
 Type de données : tableau de chaînes  
  
 Type d'accès : lecture seule  
  
 Collection d'en-têtes d'adresse jointe à ce point de terminaison.  
  
### <a name="addressidentity"></a>AddressIdentity  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 Identité du point de terminaison.  
  
### <a name="appdomainid"></a>AppDomainId  
 Type de données : sint32  
  
 Type d'accès : lecture seule  
  
 ID du domaine d'application qui héberge le point de terminaison.  
  
### <a name="behaviors"></a>Comportements  
 Type de données : tableau de comportements  
  
 Type d'accès : lecture seule  
  
 Collection de comportements implémentée par ce point de terminaison.  
  
### <a name="binding"></a>Binding  
 Type de données : liaison  
  
 Type d'accès : lecture seule  
  
 Liaison utilisée par ce point de terminaison.  
  
### <a name="contractname"></a>ContractName  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 Chaîne qui spécifie quel contrat est exposé par ce point de terminaison.  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 Nom de l'instance des compteurs de performance du point de terminaison.  
  
### <a name="listenuri"></a>ListenUri  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 URI sur lequel le point de terminaison écoute.  
  
### <a name="name"></a>Nom  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 Nom unique de ce point de terminaison.  
  
### <a name="processid"></a>ProcessId  
 Type de données : sint32  
  
 Type d'accès : lecture seule  
  
 ID du processus qui héberge le point de terminaison.  
  
### <a name="ref"></a>ref  
 Type de données: contrat  
  
 Type d'accès : lecture seule  
  
 Le contrat exposé par ce point de terminaison.  
  
## <a name="requirements"></a>Spécifications  
  
|MOF|Déclaré dans Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espace de noms|Défini dans root\ServiceModel|

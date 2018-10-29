---
title: Service
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2018
ms.locfileid: "50196906"
---
# <a name="service"></a>Service
Service  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a>Méthodes  
 La classe Service ne définit aucune méthode.  
  
## <a name="properties"></a>Properties  
 La classe Service a les propriétés suivantes :  
  
### <a name="baseaddresses"></a>BaseAddresses  
 Type de données : tableau de chaînes  
  
 Type d'accès : lecture seule  
  
 Les adresses de base utilisées par le service.  
  
### <a name="behaviors"></a>comportements  
 Type de données : tableau de comportements  
  
 Type d'accès : lecture seule  
  
 Les comportements associés à ce service.  
  
### <a name="configurationname"></a>ConfigurationName  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 ServiceElement_BehaviorConfiguration  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 Le nom d'instance de l'instance des compteurs de performances du service.  
  
### <a name="distinguishedname"></a>DistinguishedName  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 Nom du service à cette adresse.  
  
### <a name="extensions"></a>Extensions  
 Type de données : tableau de chaînes  
  
 Type d'accès : lecture seule  
  
 Les contextes d’instance pour les extensions de l’instance de service.  
  
### <a name="metadata"></a>Métadonnées  
 Type de données : tableau de chaînes  
  
 Type d'accès : lecture seule  
  
 Les paramètres de métadonnées du service.  
  
### <a name="name"></a>Name  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 Le nom unique de ce service.  
  
### <a name="namespace"></a>Espace de noms  
 Type de données : chaîne  
  
 Type d'accès : lecture seule  
  
 L'espace de noms du service.  
  
### <a name="opened"></a>Opened  
 Type de données : datetime  
  
 Type d'accès : lecture seule  
  
 L'heure à laquelle le service a été ouvert.  
  
### <a name="outgoingchannels"></a>OutgoingChannels  
 Type de données : tableau de canaux  
  
 Type d'accès : lecture seule  
  
 Les canaux qui sortent de l'instance de service.  
  
### <a name="processid"></a>ProcessId  
 Type de données : sint32  
  
 Type d'accès : lecture seule  
  
 L'ID de processus du processus qui héberge le service.  
  
## <a name="requirements"></a>Configuration requise  
  
|MOF|Déclaré dans Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espace de noms|Défini dans root\ServiceModel|

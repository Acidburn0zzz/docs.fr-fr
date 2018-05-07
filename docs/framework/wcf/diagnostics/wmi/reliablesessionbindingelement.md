---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: 2f04e6794342d7bd0acd51481efcbeceb04fd459
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="reliablesessionbindingelement"></a>ReliableSessionBindingElement
ReliableSessionBindingElement  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a>Méthodes  
 La classe ReliableSessionBindingElement ne définit pas de méthodes.  
  
## <a name="properties"></a>Propriétés  
 La classe ReliableSessionBindingElement a les propriétés suivantes :  
  
### <a name="acknowledgementinterval"></a>AcknowledgementInterval  
 Type de données : datetime  
  
 Type d'accès : lecture seule  
  
 Intervalle d'attente d'une destination avant l'envoi d'un accusé de réception à la source de message sur les canaux fiables créés par la fabrique.  
  
### <a name="flowcontrolenabled"></a>FlowControlEnabled  
 Type de données : booléen  
  
 Type d'accès : lecture seule  
  
 Valeur booléenne qui spécifie si le contrôle de flux est activé.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  
 Type de données : datetime  
  
 Type d'accès : lecture seule  
  
 Spécifie la durée maximale pendant laquelle le canal va laisser l'autre partie communicante ne pas envoyer des messages avant de provoquer une erreur sur le canal.  
  
### <a name="maxpendingchannels"></a>MaxPendingChannels  
 Type de données : sint32  
  
 Type d'accès : lecture seule  
  
 Nombre maximal de canaux qui peuvent attendre d'être acceptés sur l'écouteur.  
  
### <a name="maxretrycount"></a>MaxRetryCount  
 Type de données : sint32  
  
 Type d'accès : lecture seule  
  
 Nombre maximal de tentatives qu'un canal fiable peut effectuer pour retransmettre un message dont il n'a pas reçu d'accusé de réception, en appelant `Send` sur son canal sous-jacent.  
  
### <a name="maxtransferwindowsize"></a>MaxTransferWindowSize  
 Type de données : sint32  
  
 Type d'accès : lecture seule  
  
 Taille de fenêtre de transfert maximale pour la session fiable.  
  
### <a name="ordered"></a>Ordered  
 Type de données : booléen  
  
 Type d'accès : lecture seule  
  
 Valeur booléenne qui spécifie si l'arrivée de messages est garantie dans leur ordre d'envoi.  
  
### <a name="reliablemessagingversion"></a>ReliableMessagingVersion  
 Type de données : entier  
  
 Type d'accès : lecture seule  
  
 Entier qui spécifie la version du protocole WS-ReliableMessaging utilisée dans la session fiable.  
  
## <a name="requirements"></a>Spécifications  
  
|MOF|Déclaré dans Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espace de noms|Défini dans root\ServiceModel|  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>

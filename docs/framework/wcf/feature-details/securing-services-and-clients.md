---
title: Sécurisation des services et des clients
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2e0440aadcad7c4297cdc6e6489ca004480420ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="securing-services-and-clients"></a>Sécurisation des services et des clients
Les informations contenues dans cette section se concentre sur la programmation de la sécurité dans Windows Communication Foundation (WCF). En général, l’opération inclut la sélection d’une liaison appropriée fournie par le système, la définition des propriétés de l’élément de sécurité, puis la définition des propriétés des comportements du service qui déterminent la manière dont les informations d’identification sont récupérées pour être utilisées par le service ou le client. Ces techniques couvrent les exigences de sécurité de la plupart des utilisateurs pour la plupart des scénarios, comme indiqué dans [des scénarios de sécurité courants](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Si votre scénario requiert plus de fonctionnalités, consultez tout d’abord [fonctionnalités de sécurité avec les liaisons personnalisées](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); si une solution n’est pas visible, consultez [extension de sécurité](../../../../docs/framework/wcf/extending/extending-security.md). Si vous créez (ou il interagit avec) un système qui utilise des revendications riche, consultez les rubriques de [autorisation](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>Dans cette section  
 [Programmation de la sécurité dans WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 Vue d'ensemble du modèle de programmation utilisé pour sécuriser des messages.  
  
 [Vue d’ensemble de la sécurité de transport](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 Vue d'ensemble de la sécurisation des messages par le biais de la couche transport.  
  
 [Sécurité de message](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 Résume les raisons d’utiliser la sécurité au niveau du message dans Windows Communication Foundation (WCF).  
  
 [Sessions sécurisées](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 En savoir plus sur les considérations requis lors de la sécurisation d’une session WCF.  
  
 [Utilisation des certificats](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 Explication de quelques-unes des tâches courantes requises lors de l’utilisation de certificats X.509.  
  
## <a name="reference"></a>Référence  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Concepts relatifs à la sécurité](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [Extension de la sécurité](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [Scénarios de sécurité courants](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [Liaisons et sécurité](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Fonctionnalités de sécurité avec des liaisons personnalisées](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [Extension de la sécurité](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [Autorisation](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Programmation WCF de base](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Modèle de sécurité pour Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)

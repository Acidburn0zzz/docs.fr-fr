---
title: Classe d'opération
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 9696a7f026e54afacb5ccbfa8703a2ba617a9f3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165072"
---
# <a name="operation-class"></a>Classe d'opération
Opération  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a>Méthodes  
 La classe Operation ne définit pas de méthodes.  
  
## <a name="properties"></a>Properties  
 La classe Operation a les propriétés suivantes :  
  
### <a name="action"></a>Action  
 Type de données : chaîne  
  
 Type d’accès : Propriétés en lecture seule  
  
 L'action WS-Addressing du message de demande.  
  
### <a name="asyncpattern"></a>AsyncPattern  
 Type de données : booléen  
  
 Type d’accès : Propriétés en lecture seule  
  
 Indique qu’une opération est implémentée de façon asynchrone à l’aide un `Begin`[Ouvrir/fermer les crochets] et `End`paire de méthodes [ouverture/fermeture crochets] dans un contrat de service.  
  
### <a name="behaviors"></a>comportements  
 Type de données : Tableau de comportements  
  
 Type d’accès : Propriétés en lecture seule  
  
 Comportements associés à cette opération.  
  
### <a name="iscallback"></a>IsCallback  
 Type de données : booléen  
  
 Type d’accès : Propriétés en lecture seule  
  
 True lorsque l'opération est une opération de rappel.  
  
### <a name="isinitiating"></a>IsInitiating  
 Type de données : booléen  
  
 Type d’accès : Propriétés en lecture seule  
  
 Indique si la méthode implémente une opération qui peut initialiser une session sur le serveur.  
  
### <a name="isoneway"></a>IsOneWay  
 Type de données : booléen  
  
 Type d’accès : Propriétés en lecture seule  
  
 Indique si une opération retourne un message de réponse.  
  
### <a name="isterminating"></a>IsTerminating  
 Type de données : booléen  
  
 Type d’accès : Propriétés en lecture seule  
  
 Indique si une opération retourne un message de réponse.  
  
### <a name="methodsignature"></a>MethodSignature  
 Type de données : chaîne  
  
 Type d’accès : Propriétés en lecture seule  
  
 Signature de méthode de l'opération.  
  
### <a name="name"></a>Nom  
 Type de données : chaîne  
  
 Type d’accès : Propriétés en lecture seule  
  
 Nom de l'opération.  
  
### <a name="parametertypes"></a>ParameterTypes  
 Type de données : tableau de chaînes  
  
 Type d’accès : Propriétés en lecture seule  
  
 Types des paramètres de l'opération.  
  
### <a name="replyaction"></a>ReplyAction  
 Type de données : chaîne  
  
 Type d’accès : Propriétés en lecture seule  
  
 Valeur de l'action SOAP pour le message de réponse de l'opération.  
  
### <a name="returntype"></a>ReturnType  
 Type de données : chaîne  
  
 Type d’accès : Propriétés en lecture seule  
  
 Type de retour de l’opération.  
  
## <a name="requirements"></a>Configuration requise  
  
|MOF|Déclaré dans Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espace de noms|Défini dans root\ServiceModel|  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.ServiceModel.Description.OperationDescription>

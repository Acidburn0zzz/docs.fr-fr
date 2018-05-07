---
title: '&lt;soapProcessing&gt;'
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: cc720c9e3a8ab934ffa8d3cb0c6eceb47a708fb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="ltsoapprocessinggt"></a>&lt;soapProcessing&gt;

Définit le comportement de point de terminaison client utilisé pour marshaler des messages entre les versions de message et les types de liaison différents.

**\<système. ServiceModel >**   
&nbsp;&nbsp;**\<comportements >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors >**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comportement >**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing >**

## <a name="syntax"></a>Syntaxe

```xml
<soapProcessing processMessages="true|false" />
```

## <a name="attributes-and-elements"></a>Attributs et éléments

Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.

### <a name="attributes"></a>Attributs

|                   | Description |
| ----------------- | ----------- |
| `processMessages` | Valeur booléenne qui spécifie si les messages doivent être marshalés entre des versions de message SOAP. |

### <a name="child-elements"></a>Éléments enfants

Aucun

### <a name="parent-elements"></a>Éléments parents

|     | Description |
| --- | ----------- |
| [**\<comportement >**](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) | Spécifie un comportement de point de terminaison. |

## <a name="remarks"></a>Notes

Le traitement SOAP est le processus par lequel les messages sont convertis entre des versions de message.

Le Service de routage de Windows Communication Foundation (WCF) peut convertir des messages à partir d’un protocole à un autre. Si les versions des messages entrant et sortant sont différentes, un nouveau message est créé dans la version correcte. Le traitement des messages à partir d’un <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion` à un autre s’effectue en créant un nouveau message WCF qui contient la partie de corps et en-têtes pertinents du message WCF entrant. Les en-têtes spécifiques à l'adressage ou reconnus au niveau du routeur ne sont pas utilisés pendant la création du nouveau message WCF car ils sont de versions différentes (dans le cas d'en-têtes d'adressage) ou ont été traités dans le cadre de la communication entre le client et le routeur.

Le placement d'un en-tête dans le message sortant dépend de son balisage comme étant compris au moment où il traverse la couche du canal entrant. Les en-têtes non reconnus (tels que les en-têtes personnalisés) ne sont pas supprimés et traversent donc le service de routage en étant copiés dans le message sortant. Le corps du message est copié dans le message sortant. Le message est ensuite envoyé via le canal de sortie ; les en-têtes et autres données d'enveloppe spécifiques à ce protocole de communication/transport sont alors créés et ajoutés.

Ces étapes de traitement s'exécutent lorsque le comportement de traitement SOAP est spécifié. Cela [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) comportement est un comportement de point de terminaison qui est appliqué à tous les points de terminaison de client (sortant) au démarrage du Service de routage. par défaut, le [ \<routage >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportement crée et attache un nouveau [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) comportement avec `processMessages` la valeur `true` pour chaque point de terminaison client. Si vous utilisez un protocole non reconnu par le service de routage ou souhaitez remplacer le comportement de traitement par défaut, vous pouvez désactiver le traitement SOAP pour l'intégralité du service de routage ou pour des points de terminaison particuliers.  Pour désactiver le traitement pour le service de routage entier sur tous les points de terminaison SOAP, définissez la `soapProcessing` attribut de la [ \<routage >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportement `false`. Pour désactiver le traitement SOAP pour un point de terminaison particulier, utilisez ce comportement et affectez à son attribut `processMessages` la valeur `false`, puis attachez ce comportement au point de terminaison au niveau duquel vous ne voulez pas exécuter le code de traitement par défaut.  Lorsque le [ \<routage >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportement configure le Service de routage, elle sera ignorée en réappliquant le comportement de point de terminaison, car il en existe déjà.

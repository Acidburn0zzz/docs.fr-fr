---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485185"
---
# <a name="1004---workflowinstanceaborted"></a>1004 - WorkflowInstanceAborted

## <a name="properties"></a>Properties

|||
|-|-|
|ID|1004|
|Mots clés|WFRuntime|
|Niveau|Information|
|Canal|Microsoft-Windows-Application Server-Applications/Débogage|

## <a name="description"></a>Description

Indique une instance de workflow a été abandonnée avec une exception.

## <a name="message"></a>Message

ID WorkflowInstance : « %1 » a été abandonné avec une exception.

## <a name="details"></a>Détails

|Nom d'élément de données|Type d'élément de données|Description|
|--------------------|--------------------|-----------------|
|WorkflowInstanceId|`xs:string`|ID d'instance pour le workflow|
|Exception|`xs:string`|Détails de l'exception|
|AppDomain|`xs:string`|Chaîne retournée par AppDomain.CurrentDomain.FriendlyName.|

---
title: IAppIdAuthority, interface
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 819afec2c448e5f396ab54e2dde00c01da310b12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority, interface
Fournit des méthodes qui génèrent et comparer les clés pour les identités d’application et les références.  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Obtient une valeur qui indique si les deux spécifiés [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances sont égales. Vous pouvez passer la valeur d’indicateur IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION pour ignorer leurs informations de version respectives.|  
|`IAppIdAuthority::AreReferencesEqual`|Obtient une valeur qui indique si les deux spécifiés [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances sont égales. Vous pouvez passer la valeur d’indicateur IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION pour ignorer leurs informations de version respectives.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Obtient une valeur qui indique si les deux définitions de chaîne spécifié sont égale. Vous pouvez passer la valeur d’indicateur IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION pour ignorer leurs informations de version respectives.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Obtient une valeur qui indique si les deux références de chaîne spécifié sont égaux. Vous pouvez passer la valeur d’indicateur IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION pour ignorer leurs informations de version respectives.|  
|`IAppIdAuthority::CreateDefinition`|Obtient un pointeur d’interface qui vient d’être généré `IDefinitionAppId` instance qui représente l’assembly dans la portée actuelle.|  
|`IAppIdAuthority::CreateReference`|Obtient un pointeur d’interface nouvellement créé `IReferenceAppId` qui représente l’assembly dans la portée actuelle.|  
|`IAppIdAuthority::DefinitionToText`|Obtient une version de chaîne spécifié `IDefinitionAppId`, à l’aide des valeurs d’indicateur spécifiées.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Obtient une valeur qui indique si le texte spécifié `IDefinitionAppId` et `IReferenceAppId` représentent le même assembly.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Obtient une valeur qui indique si la chaîne de définition spécifié et la chaîne de référence représentent le même assembly.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Obtient une clé de chaîne qui représente l’élément `IDefinitionAppId` instance.|  
|`IAppIdAuthority::GenerateReferenceKey`|Obtient une clé de chaîne qui représente l’élément `IReferenceAppId` instance.|  
|`IAppIdAuthority::HashDefinition`|Obtient une clé de hachage spécifié `IDefinitionAppId` instance.|  
|`IAppIdAuthority::HashReference`|Obtient une clé de hachage spécifié `IReferenceAppId` instance.|  
|`IAppIdAuthority::ReferenceToText`|Obtient une version de chaîne spécifié `IReferenceAppId`, à l’aide des valeurs d’indicateur spécifiées.|  
|`IAppIdAuthority::TextToDefinition`|Obtient un pointeur d’interface vers un `IDefinitionAppId` instance qui représente l’assembly référencé par la clé de chaîne spécifiée.|  
|`IAppIdAuthority::TextToReference`|Obtient un pointeur d’interface vers un `IReferenceAppId` instance qui représente l’assembly référencé par la clé de chaîne spécifiée.|  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Isolation.h  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces de fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

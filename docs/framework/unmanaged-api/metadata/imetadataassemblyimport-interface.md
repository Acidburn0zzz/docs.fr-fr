---
title: IMetaDataAssemblyImport, interface
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 373ff0470e2403f91534df0c0ffe4039dbb0f832
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112630"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport, interface
Fournit des méthodes pour accéder au contenu d'un manifeste d'assembly et l'examiner.  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[CloseEnum, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Libère le handle pour l’énumérateur spécifié.|  
|[EnumAssemblyRefs, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Obtient un pointeur d’interface vers un énumérateur qui contient le `mdAssemblyRef` jetons des assemblys référencés par l’assembly dans la portée de métadonnées actuelle.|  
|[EnumExportedTypes, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Obtient un pointeur d’interface vers un énumérateur qui contient le `mdExportedType` jetons des types COM référencés par l’assembly dans la portée de métadonnées actuelle.|  
|[EnumFiles, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Obtient un pointeur d’interface vers un énumérateur qui contient le `mdFile` jetons des fichiers référencés par l’assembly dans la portée de métadonnées actuelle.|  
|[EnumManifestResources, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Obtient un pointeur d’interface vers un énumérateur qui contient le `mdManifestResource` jetons des ressources référencées par l’assembly dans la portée de métadonnées actuelle.|  
|[FindAssembliesByName, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Obtient un tableau de `mdAssemblyRef` jetons pour les assemblys portant le nom spécifié.|  
|[FindExportedTypeByName, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Obtient un `mdExportedType` jeton pour le type COM avec le nom spécifié.|  
|[FindManifestResourceByName, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Obtient un `mdManifestResource` jeton pour la ressource avec le nom spécifié.|  
|[GetAssemblyFromScope, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Obtient le jeton pour l’assembly dans la portée de métadonnées actuelle.|  
|[GetAssemblyProps, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Obtient les paramètres de propriété de l’assembly spécifié.|  
|[GetAssemblyRefProps, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Obtient les paramètres de propriété spécifié `mdAssemblyRef` jeton.|  
|[GetExportedTypeProps, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Obtient les paramètres de propriété du type COM spécifié.|  
|[GetFileProps, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Obtient les paramètres de propriété du fichier spécifié.|  
|[GetManifestResourceProps, méthode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Obtient les paramètres de propriété de la ressource de manifeste spécifiée.|  
  
## <a name="requirements"></a>Configuration requise  
 **Plateforme :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Cor.h  
  
 **Bibliothèque :** Utilisé en tant que ressource dans MsCorEE.dll  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [Interfaces de métadonnées](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataAssemblyEmit, interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

---
title: "Énumération AssemblyOptions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6ad4f9e02ed0d22009fcb8a5ac078231f2cb22e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyoptions-enumeration"></a>Énumération AssemblyOptions
Énumère les options de l’assembly.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Champs  
  
|Champ|Description|  
|-----------|-----------------|  
|optAssemTitle|Chaîne - représente le titre de l’assembly.|  
|optAssemDescription|Chaîne - contient la description de l’assembly.|  
|optAssemConfig|Chaîne - contient la configuration de l’assembly.|  
|optAssemOS|Chaîne - encodée comme : « dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion ».|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Chaîne - contient les paramètres régionaux d’assembly.|  
|optAssemVersion|Chaîne - encodée comme : « Major.Minor.Build.Revision ».|  
|optAssemCompany|Chaîne - contient la société.|  
|optAssemProduct|Chaîne - contient le nom du produit.|  
|optAssemProductVersion|Chaîne (également appelé InformationalVersion).|  
|optAssemCopyright|Chaîne - contient les informations de copyright.|  
|optAssemTrademark|Chaîne - contient les informations de marque.|  
|optAssemKeyFile|String (nom de fichier).|  
|optAssemKeyName|Chaîne (le nom de clé).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (également appelé DelaySign).|  
|optAssemFileVersion|Chaîne - encodée comme « Major.Minor.Build.Revision » - identique à ProductVersion.|  
|optAssemSatelliteVer|Chaîne - encodée sous la forme « Major.Minor.Build.Revision ».|  
|optLastAssemOption|Un compteur du nombre d’éléments.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** alink.h  
  
 **Bibliothèque**: alink.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)

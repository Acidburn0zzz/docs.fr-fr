---
title: AssemblyComparisonResult, énumération
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82b81ec29dece182548ead046edc7cb754fbf00e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430659"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult, énumération
Indique l’équivalence de deux identités d’assembly, comme déterminé par le [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) (fonction).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>Membres  
  
|Nom de membre|Description|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Indique qu’assembly tous les champs dans la correspondance de la comparaison.|  
|`ACR_EquivalentFXUnified`|Indique que les assemblys sont considérés comme équivalents selon l’unification de version (CLR) common language runtime de numéros de version d’assembly dans le .NET Framework version 2.0.|  
|`ACR_EquivalentPartialFXUnified`|Indique une correspondance partielle des assemblys selon l’unification CLR de numéros de version d’assembly dans le .NET Framework 2.0.|  
|`ACR_EquivalentPartialMatch`|Indique une correspondance partielle des assemblys.|  
|`ACR_EquivalentPartialUnified`|Indique une correspondance partielle des assemblys selon l’unification héritée des numéros de version.|  
|`ACR_EquivalentPartialWeakNamed`|Indique une correspondance partielle d’assemblys simplement nommés.|  
|`ACR_EquivalentUnified`|Indique que les assemblys sont considérés comme équivalents selon l’unification de numéros de version dans les anciennes versions du .NET Framework CLR.|  
|`ACR_EquivalentWeakNamed`|Indique une correspondance entre deux assemblys simplement nommés dont les numéros de version ont été ignorés.|  
|`ACR_NonEquivalent`|Indique qu’aucune correspondance s’est produite entre les deux assemblys.|  
|`ACR_NonEquivalentPartialVersion`|Indique que les deux assemblys correspondent à l’exception de leurs numéros de version qui ne correspondent que partiellement.|  
|`ACR_NonEquivalentVersion`|Indique que les deux assemblys correspondent à l’exception de leurs numéros de version qui ne correspondent pas.|  
|`ACR_Unknown`|Indique que la raison de non-équivalence n’est pas connue.|  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Fusion.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [CompareAssemblyIdentity, fonction](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [Énumérations de fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)

---
title: CeeSectionRelocType, énumération
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: babd7d87f1bb6f238c347d68814a3ecdaef64b40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType, énumération
Fournit des valeurs pour influencer le type de `reloc` instruction émise dans un appel à [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a>Membres  
  
|Membre|Description|  
|------------|-----------------|  
|`srRelocAbsolute`|Génère uniquement une section relatifs à `reloc`, en envoyant rien dans une section .reloc.|  
|`srRelocHighLow`|Génère un `reloc` pour un emplacement de la taille du pointeur. Il est transformé en BASED_HIGHLOW ou en BASED_DIR64 selon la plateforme.|  
|`srRelocHighAdj`|Génère un `reloc` pour les 16 bits supérieurs d’un nombre 32 bits, où les 16 bits inférieurs sont inclus dans le mot suivant dans la table .reloc.|  
|`srRelocMapToken`|Génère un déplacement de la table de jetons, envoyant rien dans une section .reloc.|  
|`srRelocRelative`|Indique que la valeur est une correction de l’adresse relative.|  
|`srRelocFilePos`|Génère uniquement une section relatifs à `reloc`, en envoyant rien dans une section .reloc. Cela `reloc` est relatif à la position de la section, pas une adresse virtuelle de la section du fichier.|  
|`srRelocCodeRelative`|Spécifie une correction de l’adresse relative du code.|  
|`srRelocIA64Imm64`|Génère un `reloc` pour une adresse 64 bits dans un ia64 `movl` instruction.|  
|`srRelocDir64`|Génère un `reloc` pour une adresse 64 bits.|  
|`srRelocIA64PcRel25`|Générer un `reloc` pour chaque adresse relative PC 25 bits dans un ia64 `br.call` instruction.|  
|`srRelocIA64PcRel64`|Génère un `reloc` pour chaque adresse relative PC 64 bits dans un ia64 `brl.call` instruction.|  
|`srRelocAbsoluteTagged`|Génère une section de 30 bits-relative `reloc`, utilisé pour les valeurs de pointeur avec balises.|  
|`srRelocSentinel`|Une valeur de sentinelle afin de garantir des ajouts à cet enum sont reflétées dans le texte interne `reloc` tableau de noms.|  
|`srNoBaseReloc`|Spécifie de ne pas émettre d’une base de `reloc`.|  
|`srRelocPtr`|Une valeur qui indique que le contenu de pre-correction de la mémoire est un pointeur plutôt qu’une section de décalage.|  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Cor.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations de métadonnées](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [ICeeGen, interface](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [AddSectionReloc, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)

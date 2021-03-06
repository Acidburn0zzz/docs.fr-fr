---
title: ICeeGen, interface
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fb081c48abf899b44da1c1351efa3f6036f1c8d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176122"
---
# <a name="iceegen-interface"></a>ICeeGen, interface
Fournit des méthodes pour la compilation de code dynamique.  
  
 Cette interface est obsolète et ne doit pas être utilisée.  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[AddSectionReloc, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Obsolète. Ajoute une instruction .reloc à la base de code.|  
|[AllocateMethodBuffer, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Obsolète. Crée une mémoire tampon de la taille spécifiée pour une méthode et obtient l’adresse virtuelle relative de la méthode.|  
|[ComputePointer, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Obsolète. Détermine la mémoire tampon pour la section de code spécifié.|  
|[EmitString, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Obsolète. Émet la chaîne spécifiée dans la base de code.|  
|[GenerateCeeFile, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Obsolète. Génère un fichier de base de code qui contient la base de code actuellement chargé dans ce `ICeeGen`.|  
|[GenerateCeeMemoryImage, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Obsolète. Génère une image dans la mémoire pour la base de code.|  
|[GetIlSection, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Obsolète. Obtient la section de la base de code de langage intermédiaire référencée par le handle spécifié.|  
|[GetIMapTokenIface, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Obsolète. Obtient l’interface référencée par le jeton spécifié.|  
|[GetMethodBuffer, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Obsolète. Obtient une mémoire tampon de la taille appropriée pour la méthode à l’adresse virtuelle relative spécifiée.|  
|[GetSectionBlock, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Obsolète. Obtient un bloc de section de la base de code.|  
|[GetSectionCreate, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Obsolète. Génère et obtient une section de code utilisant le nom spécifié et les valeurs d’indicateur.|  
|[GetSectionDataLen, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Obsolète. Obtient la longueur de la section spécifiée.|  
|[GetString, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Obsolète. Obtient la chaîne stockée à l’adresse virtuelle relative spécifiée.|  
|[GetStringSection, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Obsolète. Obtient une représentation sous forme de chaîne de la section de code référencée par le handle spécifié.|  
|[TruncateSection, méthode](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Obsolète. Tronque la section de code spécifié par la longueur spécifiée.|  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** Cor.h  
  
 **Bibliothèque :** Utilisé en tant que ressource dans MsCorEE.dll  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [Interfaces de métadonnées](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

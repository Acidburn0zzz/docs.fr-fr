---
title: Méthode ICLRStrongName::StrongNameSignatureVerificationFromImage
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60dbb8d8461015c791a70d6c2617b1c81e5ba17f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434266"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a>Méthode ICLRStrongName::StrongNameSignatureVerificationFromImage
Vérifie qu’un assembly qui a déjà été mappé à la mémoire est valide pour la clé publique associée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pbBase`  
 [in] L’adresse virtuelle relative du manifeste d’assembly mappé.  
  
 `dwLength`  
 [in] La taille, en octets, de l’image mappée.  
  
 `dwInFlags`  
 [in] Indicateurs qui influencent le comportement de vérification. Les valeurs suivantes sont prises en charge :  
  
-   `SN_INFLAG_FORCE_VER` (0 x 00000001) - force la vérification même s’il est nécessaire de remplacer les paramètres du Registre.  
  
-   `SN_INFLAG_INSTALL` (0 x 00000002) - Spécifie qu’il s’agit de la première vérification effectuée sur cette image.  
  
-   `SN_INFLAG_ADMIN_ACCESS` (0 x 00000004) - Spécifie que le cache autorise l’accès uniquement aux utilisateurs qui ont des privilèges d’administrateur.  
  
-   `SN_INFLAG_USER_ACCESS` (0 x 00000008) - Spécifie que l’assembly est accessible uniquement à l’utilisateur actuel.  
  
-   `SN_INFLAG_ALL_ACCESS` (0 x 00000010) - Spécifie que le cache ne va fournir aucune garantie de restriction d’accès.  
  
-   `SN_INFLAG_RUNTIME` (0 x 80000000) - réservé pour le débogage interne.  
  
 `pdwOutFlags`  
 [out] Un indicateur pour les données de sortie supplémentaires. La valeur suivante est prise en charge :  
  
-   `SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001) - cette valeur est définie sur `false` pour spécifier que la vérification a réussi en raison des paramètres de Registre.  
  
## <a name="return-value"></a>Valeur de retour  
 `S_OK` Si la méthode a réussi ; Sinon, une valeur HRESULT qui indique un échec (voir [valeurs HRESULT courantes](http://go.microsoft.com/fwlink/?LinkId=213878) pour obtenir la liste).  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MetaHost.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [ICLRStrongName, interface](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

---
title: LoadStringRCEx, fonction
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38c942b9a94c83f5a3316cf3ae3ccbbad2b0ec69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444315"
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx, fonction
Traduit une valeur HRESULT à un message d’erreur approprié pour la culture spécifiée.  
  
 Cette fonction est déconseillée dans le [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lcid`  
 [in] Un identificateur de culture. Passez -1 `lcid` pour utiliser la culture par défaut.  
  
 `iResourceID`  
 [in] Une valeur HRESULT.  
  
 `szBuffer`  
 [out] Une mémoire tampon qui contient le message d’erreur en cas de réussite.  
  
 `iMax`  
 [in] La taille de la mémoire tampon de message.  
  
 `bQuiet`  
 [in] Ignoré.  
  
 `pcwchUsed`  
 [out] Pointeur vers la longueur du message d’erreur.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne des codes d’erreur COM standard, tel que défini dans WinError.h, en plus des valeurs suivantes.  
  
|Code de retour|Description|  
|-----------------|-----------------|  
|S_OK|La commande s'est correctement terminée.|  
|E_INVALIDARG|`szBuffer` a la valeur null ou `iMax` est zéro (0).|  
  
## <a name="remarks"></a>Notes  
 Si la méthode ne se termine pas correctement, `szBuffer` contient une chaîne vide.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MSCorEE.h  
  
 **Bibliothèque :** MSCorEE.dll  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [LoadStringRC, fonction](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [Fonctions d’hébergement CLR dépréciées](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

---
title: ICLRMetaHost::GetRuntime, méthode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b71d0f29d770b2722b0dfaabc8b9667e524c99e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207602"
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime, méthode
Obtient le [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface qui correspond à une version particulière du common language runtime (CLR). Cette méthode remplace la [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) fonction utilisée avec le [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) indicateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>Paramètres  
 `pwzVersion`  
 [in] La version de compilation .NET Framework stockée dans les métadonnées, au format « v*A*. *B*[. *X*] ». *Un*, *B*, et *X* sont des nombres décimaux qui correspondent à la version principale, la version secondaire et le numéro de build.  
  
> [!NOTE]
>  Ce paramètre doit correspondre au nom de répertoire pour la version de .NET Framework, tel qu’il apparaît sous C:\Windows\Microsoft.NET\Framework ou C:\Windows\Microsoft.NET\Framework64.  
  
 Exemples de valeurs : « v1.0.3705 », « v1.1.4322 », « v2.0.50727 » et « v4.0. *X*», où *X* varie selon le numéro de build installé. Le préfixe « v » est requis.  
  
 `riid`  
 [in] L’identificateur de l’interface souhaitée. Actuellement, la seule valeur valide pour ce paramètre est IID_ICLRRuntimeInfo.  
  
 `ppRuntime`  
 [out] Un pointeur vers le [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface qui correspond au runtime demandé.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne les HRESULT spécifiques suivants ainsi que les erreurs HRESULT indiquant l'échec de la méthode.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|La commande s'est correctement terminée.|  
|E_POINTER|`pwzVersion` ou `ppRuntime` a la valeur null.|  
  
## <a name="remarks"></a>Notes  
 Cette méthode interagit régulièrement avec les interfaces héritées telles que la [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface et les fonctions héritées comme déconseillées `CorBindTo*` fonctions (voir [déconseillée hébergeant des fonctions CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) dans l’API d’hébergement .NET Framework 2.0). Autrement dit, les runtimes chargés avec l’API héritée sont visibles à la nouvelle API, et les runtimes chargés avec la nouvelle API sont visibles à l’API héritée.  
  
## <a name="requirements"></a>Configuration requise  
 **Plateformes :** Consultez [Configuration requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MetaHost.h  
  
 **Bibliothèque :** Inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions de .NET Framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi

- [ICLRMetaHost, interface](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Interfaces d'hébergement du CLR et coclasses déconseillées](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [Interfaces d'hébergement du CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [Fonction d'hébergement du CLR déconseillées](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Hébergement](../../../../docs/framework/unmanaged-api/hosting/index.md)

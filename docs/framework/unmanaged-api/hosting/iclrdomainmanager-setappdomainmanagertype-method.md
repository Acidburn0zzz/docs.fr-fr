---
title: ICLRDomainManager::SetAppDomainManagerType, méthode
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea10f9b7d23d8ca6a94d05cac6e586b434c000d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435541"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType, méthode
Spécifie le type, dérivé de la <xref:System.AppDomainManager?displayProperty=nameWithType> classe, le Gestionnaire de domaine d’application qui servira à initialiser le domaine d’application par défaut.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `wszAppDomainManagerAssembly`  
 [in] Le nom complet de l’assembly qui contient le type de gestionnaire de domaine application ; par exemple : « AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3 ».  
  
 `wszAppDomainManagerType`  
 [in] Nom du type de gestionnaire de domaine, y compris l’espace de noms.  
  
 `dwInitializeDomainFlags`  
 [in] Une combinaison de [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) valeurs d’énumération qui fournissent des informations sur le Gestionnaire de domaine d’application.  
  
## <a name="return-value"></a>Valeur de retour  
 Cette méthode retourne les HRESULT spécifiques suivants ainsi que les erreurs HRESULT indiquant l'échec de la méthode.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|La commande s'est correctement terminée.|  
|HOST_E_CLRNOTAVAILABLE|Le common language runtime (CLR) n’a pas été chargé dans un processus ou le CLR est dans un état dans lequel il ne peut pas exécuter du code managé ou traiter l’appel avec succès.|  
  
## <a name="remarks"></a>Notes  
 Actuellement, la seule valeur définie pour `dwInitializeDomainFlags` est `eInitializeNewDomainFlags_NoSecurityChanges`, qui indique le common language runtime (CLR) que le Gestionnaire de domaine d’application ne modifiera pas de paramètres de sécurité pendant l’exécution de la <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> (méthode). Cela permet au CLR optimiser le chargement des assemblys qui ont l’attribut conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribut (APTCA). Si la fermeture transitive de ce jeu d’assemblys est importante, cela peut entraîner une amélioration significative du temps de démarrage.  
  
> [!IMPORTANT]
>  Si l’hôte spécifie `eInitializeNewDomainFlags_NoSecurityChanges` pour le Gestionnaire de domaine d’application, un <xref:System.InvalidOperationException> est levée si une tentative est faite pour modifier la sécurité du domaine d’application.  
  
 Appel de la [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)méthode équivaut à appeler la méthode `ICLRDomainManager::SetAppDomainManagerType` avec `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** MetaHost.h  
  
 **Bibliothèque :** inclus en tant que ressource dans MSCorEE.dll  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Hébergement](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRDomainManager, interface](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [EInitializeNewDomainFlags, énumération](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)

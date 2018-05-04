---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c25ea1fc32c93e7eb57ef8ed06d6f786ae0a670e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicetokenresolvergt"></a>&lt;serviceTokenResolver&gt;
Inscrit le résolveur de jeton de service qui est utilisé par les gestionnaires de la collection du Gestionnaire de jetons. Le programme de résolution de jeton de service permet de résoudre le jeton de chiffrement sur les jetons et les messages entrant.  
  
 \<system.identityModel>  
\<identityConfiguration >  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<serviceTokenResolver >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Attribut|Description|  
|---------------|-----------------|  
|type|Spécifie le type du programme de résolution de jeton de service. Soit le <xref:System.IdentityModel.Selectors.SecurityTokenResolver> ou un type qui dérive de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe. Pour plus d’informations sur la façon de spécifier le `type` d’attribut, consultez [références de Type personnalisé]. Obligatoire.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Fournit des gestionnaires de jetons de configuration pour une collection de sécurité.|  
  
## <a name="remarks"></a>Notes  
 Le programme de résolution de jeton de service peut être utilisé pour résoudre le jeton de chiffrement sur les jetons et les messages entrant. Il est utilisé pour récupérer la clé doit être utilisée pour déchiffrer les jetons entrants. Vous devez spécifier le `type` attribut. Le type spécifié peut être <xref:System.IdentityModel.Selectors.SecurityTokenResolver> ou un type personnalisé qui dérive de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.  
  
 Certains gestionnaires de jetons permettent de spécifier les paramètres de résolution de jeton de service dans la configuration. Paramètres de gestionnaires de jetons individuels remplacent celles spécifiées dans la collection de gestionnaire de jetons de sécurité.  
  
> [!NOTE]
>  En spécifiant le `<serviceTokenResolver>` élément comme un élément enfant de le [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) l’élément a été déconseillée, mais est toujours prise en charge pour la compatibilité descendante. Paramètres de la `<securityTokenHandlerConfiguration>` élément remplacent celles sur le `<identityConfiguration>` élément.  
  
## <a name="example"></a>Exemple  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```

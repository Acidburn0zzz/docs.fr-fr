---
title: Schéma des paramètres web
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 461043dbb57043c5c18ea703d45f8b3ae487d271
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47401483"
---
# <a name="web-settings-schema"></a>Schéma des paramètres web
Les paramètres web spécifient les paramètres d’UC et d’ASP.NET au niveau de l’exécution qui s’appliquent au comportement à l’échelle des processus géré par la couche d’hébergement ASP.NET. Ces paramètres se distinguent des paramètres de type de domaine d’application spécifiés dans le fichier Web.config d’une application ASP.NET.  
  
 Les paramètres web sont contenus dans les fichiers Aspnet.config, qui se trouvent dans les dossiers d’installation du .NET Framework, qui varient en fonction des versions. Par exemple, le fichier Aspnet.config pour [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] se trouve dans le dossier suivant :  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 Les paramètres web ne sont utilisés dans aucun autre des fichiers de configuration, tels que le fichier machine.config, le fichier racine Web.config ou les fichiers Web.config au niveau de l’application.  
  
 [\<configuration>, élément](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.web>, élément (paramètres web)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [\<applicationPool >, élément (paramètres Web)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Contient les informations utilisées par la couche d’hébergement ASP.NET.|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Spécifie les paramètres d’UC et d’ASP.NET au niveau de l’exécution qui s’appliquent au comportement à l’échelle des processus géré par la couche d’hébergement ASP.NET.|  
  
## <a name="see-also"></a>Voir aussi  
 [Schéma des fichiers de configuration](../../../../../docs/framework/configure-apps/file-schema/index.md)

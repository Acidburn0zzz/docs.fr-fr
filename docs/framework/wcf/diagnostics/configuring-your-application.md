---
title: Configuration de votre application
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 922b9c5c53e04719f3ed48d0ff6386f21bf83e99
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="configuring-your-application"></a>Configuration de votre application
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilise le système de configuration .NET et vous permet de configurer des services à la fois au niveau de l'ordinateur et au niveau de l'application.  
  
 Les paramètres de configuration définis par [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se trouvent dans le groupe de sections `<system.serviceModel>`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] la configuration d'un service [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consultez les rubriques suivantes :  
  
-   [Configuration des services](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Les paramètres de configuration définis par l'application sont définis dans le groupe de sections `<appSettings>`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] paramètres de l’application dans les fichiers de configuration .NET, consultez [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Utilisation de l'Éditeur de configuration  
 Le [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [l’outil Éditeur de Configuration (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) permet aux administrateurs et aux développeurs créer et modifier les paramètres de configuration pour [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services à l’aide d’une interface utilisateur graphique. Cet outil vous permet de gérer les paramètres de liaison, comportement, service et diagnostic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sans modifier directement les fichiers de configuration XML.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Modification des fichiers de configuration dans Visual Studio  
 Pour modifier le fichier de configuration d’un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] , avec le bouton droit sur dans le service de projet dans Visual Studio **l’Explorateur de solutions** et choisissez la **modifier la configuration WCF** élément de menu contextuel. Cette opération lance le [l’outil Éditeur de Configuration (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Si vous modifiez le fichier de configuration d’un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] projet de Service Web dans Visual Studio en cliquant dans **l’Explorateur de solutions**, notez que le **modifier la configuration WCF** élément de menu contextuel est manquant. Pour résoudre ce problème, cliquez sur le **outils** menu, puis choisissez **éditeur de configuration de Service WCF**. Après cela, vous pouvez cliquez sur un fichier de configuration et utiliser le **modifier la configuration WCF** élément de menu contextuel.  
  
## <a name="see-also"></a>Voir aussi  
 [Outil Éditeur de configuration (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Configuration des services](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)

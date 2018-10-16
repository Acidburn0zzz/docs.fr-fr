---
title: Résolution des problèmes généraux liés à .NET Native
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45a053d2aefa8a295e0e8d52818472647e4ef834
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347584"
---
# <a name="net-native-general-troubleshooting"></a>Résolution des problèmes généraux liés à .NET Native
Cette rubrique explique comment résoudre les problèmes que vous pouvez rencontrer pendant le développement d'applications avec [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
-   **Problème :** La fenêtre de sortie de la génération n’est pas mise à jour correctement.  
  
     **Résolution :** La fenêtre de sortie de la génération n’est mise à jour qu’une fois la génération terminée. La génération pouvant prendre plusieurs minutes, les mises à jour peuvent mettre du temps à apparaître.  
  
-   **Problème :** La durée de génération de la version commerciale de votre application pour ARM a augmenté.  
  
     **Résolution :** Quand vous déployez une application sur votre appareil ARM, l’infrastructure [!INCLUDE[net_native](../../../includes/net-native-md.md)] est appelée. Cette compilation effectue un grand nombre d'optimisations tout en garantissant que la sémantique non statique telle que la réflexion continue de fonctionner. En outre, la partie du .NET Framework que l'application utilise est liée de manière statique pour optimiser les performances et doit être compilée en code natif également. C'est pourquoi la compilation prend plus de temps.  
  
     Toutefois, les temps de compilation ne dépassent pas de plus d'une minute la compilation standard de la plupart des applications sur un ordinateur de développement ordinaire.  En règle générale, la seule génération d'images natives pour le .NET Framework sur un ordinateur de développement standard prend plusieurs minutes.  Même avec le .NET Framework et toutes les optimisations visant à améliorer le code généré, la génération des applications dure généralement une ou deux minutes.  
  
     Nous allons continuer à travailler sur l'amélioration des performances de la compilation en nous penchant sur la compilation multithread et sur d'autres optimisations.  
  
-   **Problème :** Vous ne savez pas si votre application a été compilée à l’aide de [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
     **Résolution :** Si le compilateur [!INCLUDE[net_native](../../../includes/net-native-md.md)] est appelé, les délais de génération sont plus longs et le Gestionnaire de tâches affiche divers processus de composant [!INCLUDE[net_native](../../../includes/net-native-md.md)], comme ILC.exe et nutc_driver.exe.  
  
     Une fois que vous avez correctement généré votre projet avec [!INCLUDE[net_native](../../../includes/net-native-md.md)], la sortie se trouve sous obj\\*config*\ *arch*\\*nom_projet*.ilc\out.  Le contenu du package natif final se trouve sous bin\\*arch*\\*config*\AppX. Il se trouve sous \bin\\*arch*\\*config*\AppX si vous avez déployé l’application.  
  
-   **Problème :** Votre application .NET Native lève des exceptions runtime (généralement des exceptions [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) ou [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)) qu’elle n’a pas levées lors de la compilation sans .NET Native.  
  
     **Résolution :** Les exceptions sont levées, car .NET Native n’a pas fourni les métadonnées ou le code d’implémentation qui est normalement disponible via la réflexion. (Pour plus d’informations, consultez [.NET Native et compilation](../../../docs/framework/net-native/net-native-and-compilation.md).) Pour éliminer l’exception, vous devez ajouter une entrée à votre [fichier de directives d’exécution (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) afin que la chaîne d’outils .NET natif puisse rendre les métadonnées ou le code d’implémentation disponibles lors de l’exécution. Deux utilitaires de résolution des problèmes sont disponibles, qui vont générer l'entrée nécessaire pour effectuer des ajouts à votre fichier de directives d'exécution :  
  
    -   l’ [utilitaire de résolution des problèmes MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) pour les types ;  
  
    -   l’ [utilitaire de résolution des problèmes MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) pour les méthodes.  
  
     Pour plus d’informations, consultez [Réflexion et .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Migration de votre application du Windows Store vers .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)

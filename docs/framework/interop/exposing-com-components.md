---
title: Exposition de composants COM au .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c082ec115370ba60839d88e5af7df3585a8f8455
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="exposing-com-components-to-the-net-framework"></a>Exposition de composants COM au .NET Framework
Cette section résume le processus nécessaire pour exposer un composant COM existant à du code managé. Pour plus d’informations sur l’écriture de serveurs COM qui s’intègrent étroitement au .NET Framework, consultez [Considérations de design pour l’interopérabilité](https://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689(v=vs.100)).
  
 Les composants COM existants sont des ressources importantes dans le code managé, en tant qu’applications métier de couche intermédiaire ou en tant que fonctionnalités isolées. Un composant idéal a un assembly PIA et se conforme étroitement aux normes de programmation imposées par COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Pour exposer des composants COM au .NET Framework  
  
1.  [Importation d’une bibliothèque de types sous la forme d’un assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     Le common language runtime nécessite des métadonnées pour tous les types, y compris les types COM. Il existe plusieurs manières d’obtenir un assembly contenant des types COM importés en tant que métadonnées.  
  
2.  [Création de types COM dans du code managé](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     Vous pouvez inspecter des types COM, activer des instances et appeler des méthodes sur l’objet COM de la même façon que vous le feriez pour n’importe quel type managé.  
  
3.  [Compilation d’un projet d’interopérabilité](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     Le [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] fournit des compilateurs pour plusieurs langages conformes à la Common Language Specification (CLS), notamment [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# et C++.  
  
4.  [Déploiement d’une application d’interopérabilité](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     La meilleure façon de déployer des applications d’interopérabilité est de le faire en tant qu’assemblys signés [avec nom fort](../../../docs/framework/app-domains/strong-named-assemblies.md) dans le Global Assembly Cache.  
  
## <a name="see-also"></a>Voir aussi  
 [Interopération avec du code non managé](../../../docs/framework/interop/index.md)  
 [Considérations de design pour l’interopérabilité](http://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689)  
 [Exemple COM Interop : client .NET et serveur COM](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)  
 [Indépendance du langage et composants indépendants du langage](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [Gacutil.exe (outil Global Assembly Cache)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)

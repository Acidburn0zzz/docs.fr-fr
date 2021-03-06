---
title: Configuration d'un environnement de profilage
ms.date: 03/30/2017
helpviewer_keywords:
- environment variables, profiling API
- profiling API [.NET Framework], setting up environment
- COR_PROFILER environment variable
- Windows Service applications, profiling
- profiling API [.NET Framework], Windows Service applications
- COR_ENABLE_PROFILING environment variable
- profiling API [.NET Framework], enabling
ms.assetid: fefca07f-7555-4e77-be86-3c542e928312
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfa11083fad7a3ccc6a208f5f0e4b68e9e1bc18c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098180"
---
# <a name="setting-up-a-profiling-environment"></a>Configuration d'un environnement de profilage
> [!NOTE]
>  Des modifications substantielles ont été apportées au profilage dans le [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
 Quand un processus managé (application ou service) démarre, il charge le Common Language Runtime (CLR). Quand le CLR est initialisé, il évalue les deux variables environnementales suivantes afin de déterminer si le processus doit se connecter à un profileur :  
  
-   COR_ENABLE_PROFILING : Le CLR se connecte à un profileur uniquement si cette variable d’environnement existe et est définie sur 1.  
  
-   COR_PROFILER : Si le COR_ENABLE_PROFILING vérifier les passes, le CLR se connecte au profileur qui a ce CLSID ou ProgID, lequel doit avoir été précédemment stockée dans le Registre. La variable d'environnement COR_PROFILER est définie en tant que chaîne, comme indiqué dans les deux exemples suivants.  
  
    ```  
    set COR_PROFILER={32E2F4DA-1BEA-47ea-88F9-C5DAF691C94A}  
    set COR_PROFILER="MyProfiler"  
    ```  
  
 Pour profiler une application CLR, vous devez définir les variables d'environnement COR_ENABLE_PROFILING et COR_PROFILER avant d'exécuter l'application. Vous devez également vous assurer que la DLL du profileur est enregistrée.  
  
> [!NOTE]
>  À partir du [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], les profileurs ne doivent pas être enregistrés.  
  
> [!NOTE]
>  Pour utiliser des profileurs du .NET Framework versions 2.0, 3.0 et 3.5 dans le [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] et versions ultérieures, vous devez définir la variable d’environnement COMPLUS_ProfAPI_ProfilerCompatibilitySetting.  
  
## <a name="environment-variable-scope"></a>Étendue de la variable d'environnement  
 La manière dont vous définissez les variables d'environnement COR_ENABLE_PROFILING et COR_PROFILER déterminent leur champ d'influence. Vous pouvez définir ces variables de l'une des manières suivantes :  
  
-   Si vous définissez les variables un [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) appel, elles s’appliquent uniquement à l’application en cours d’exécution en temps. (Elles s'appliquent également aux autres applications démarrées par l'application qui héritent de l'environnement.)  
  
-   Si vous définissez les variables dans une fenêtre d'invite de commandes, elles s'appliquent à toutes les applications démarrées à partir de cette fenêtre.  
  
-   Si vous définissez les variables au niveau de l'utilisateur, elles s'appliquent à toutes les applications que vous démarrez avec l'Explorateur de fichiers. Une fenêtre d'invite de commandes que vous ouvrez après avoir défini les variables présente ces paramètres d'environnement à l'instar de toute application que vous démarrez à partir de cette fenêtre. Pour définir les variables d’environnement au niveau utilisateur, cliquez sur **poste de travail**, cliquez sur **propriétés**, cliquez sur le **avancé** sous l’onglet **environnement Variables**et ajoutez les variables à la **variables utilisateur** liste.  
  
-   Si vous définissez les variables au niveau de l'ordinateur, elles s'appliquent à toutes les applications démarrées sur cet ordinateur. Une fenêtre d'invite de commandes que vous ouvrez sur cet ordinateur présente ces paramètres d'environnement à l'instar de toute application que vous démarrez à partir de cette fenêtre. Cela signifie que chaque processus managé sur cet ordinateur démarre avec votre profileur. Pour définir les variables d’environnement au niveau de l’ordinateur, avec le bouton droit **poste de travail**, cliquez sur **propriétés**, cliquez sur le **avancé** sous l’onglet **environnement Variables**, ajoutez les variables à la **variables système** liste, puis redémarrez votre ordinateur. Après le redémarrage, les variables sont disponibles à l'échelle du système.  
  
 Si vous profilez un service Windows, vous devez redémarrer votre ordinateur après avoir défini les variables d'environnement et inscrit la DLL du profileur. Pour plus d’informations sur ces considérations, consultez la section [profilage d’un Service Windows](#windows_service).  
  
## <a name="additional-considerations"></a>Considérations supplémentaires  
  
-   La classe du profileur implémente le [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) et [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces. Dans le .NET Framework version 2.0, un profileur doit implémenter `ICorProfilerCallback2`. Dans ce cas, `ICorProfilerCallback2` ne sera pas chargé.  
  
-   Un seul profileur peut profiler un processus à la fois dans un environnement donné. Vous pouvez inscrire deux profileurs différents dans des environnements différents, mais chacun doit profiler des processus distincts. Le profileur doit être implémenté en tant que DLL de serveur COM in-process, mappée dans le même espace d'adressage que le processus en cours de profilage. Cela signifie que le profileur s'exécute in-process. Le .NET Framework ne prend pas en charge un autre type de serveur COM. Par exemple, si un profileur souhaite surveiller des applications à partir d'un ordinateur distant, il doit implémenter des agents collecteurs sur chaque ordinateur. Ces agents traitent les résultats par lots et les communiquent à l’ordinateur de collection de données central.  
  
-   Étant donné que le profileur est un objet COM instancié in-process, chaque application profilée possède sa propre copie du profileur. Par conséquent, une instance de profileur particulière n'a pas à gérer les données de plusieurs applications. Toutefois, vous devrez ajouter une logique au code de journalisation du profileur pour éviter le remplacement du fichier journal d'autres applications profilées.  
  
## <a name="initializing-the-profiler"></a>Initialisation du profileur  
 Quand les deux vérifications de variables d'environnement réussissent, le CLR crée une instance du profileur d'une manière similaire à la fonction `CoCreateInstance` COM. Le profileur n'est pas chargé via un appel direct à `CoCreateInstance`. Par conséquent, un appel à `CoInitialize`, qui requiert la définition du modèle de thread, est évité. Le CLR appelle ensuite la [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) méthode dans le profileur. La signature de cette méthode est la suivante.  
  
```  
HRESULT Initialize(IUnknown *pICorProfilerInfoUnk)  
```  
  
 Le profileur doit interroger `pICorProfilerInfoUnk` pour un [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) ou [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) pointeur d’interface et l’enregistrer afin qu’il puisse demander plus d’informations ultérieurement pendant le profilage.  
  
## <a name="setting-event-notifications"></a>Définition de notifications d'événements  
 Le profileur appelle ensuite la [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) méthode pour indiquer quelles catégories de notifications l’intéressent. Par exemple, si le profileur s’intéresse uniquement aux notifications d’entrée et de sortie de fonction, ainsi qu’aux notifications de garbage collection, il spécifie ce qui suit.  
  
```  
ICorProfilerInfo* pInfo;  
pICorProfilerInfoUnk->QueryInterface(IID_ICorProfilerInfo, (void**)&pInfo);  
pInfo->SetEventMask(COR_PRF_MONITOR_ENTERLEAVE | COR_PRF_MONITOR_GC)  
```  
  
 En définissant le masque des notifications de cette manière, le profileur peut limiter les notifications qu'il reçoit. Cette approche permet à l'utilisateur de générer un profileur simple ou à but spécifique. Elle réduit également le temps processeur qui serait gaspillé en envoyant des notifications qui ne seraient qu'ignorées par le profileur.  
  
 Certains événements de profileur sont immuables. Cela signifie que, dès que ces événements sont définis dans le rappel `ICorProfilerCallback::Initialize`, ils ne peuvent pas être désactivés et aucun nouvel événement ne peut être activé. Toute tentative de modification d'un événement immuable entraîne le retour d'un HRESULT d'échec par `ICorProfilerInfo::SetEventMask`.  
  
<a name="windows_service"></a>   
## <a name="profiling-a-windows-service"></a>Profilage d'un service Windows  
 Le profilage d'un service Windows s'apparente au profilage d'une application du Common Language Runtime. Les deux opérations de profilage sont activées via des variables d'environnement. Étant donné qu'un service Windows démarre au démarrage du système d'exploitation, les variables d'environnement décrites précédemment dans cette rubrique doivent déjà être présentes et définies sur les valeurs requises avant le démarrage du système. En outre, la DLL de profilage doit déjà être enregistrée sur le système.  
  
 Après avoir défini les variables d'environnement COR_ENABLE_PROFILING et COR_PROFILER, puis inscrit la DLL du profileur, vous devez redémarrer l'ordinateur cible pour que le service Windows puisse détecter ces modifications.  
  
 Notez que ces modifications activent le profilage à l'échelle du système. Pour empêcher le profilage de chaque application managée qui s'exécute par la suite, vous devez supprimer les variables d'environnement système après le redémarrage de l'ordinateur cible.  
  
 Cette technique entraîne également le profilage de chaque processus CLR. Le profileur doit ajouter la logique pour son [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) rappel pour déterminer si le processus en cours d’intérêt. Si ce n'est pas le cas, le profileur peut faire échouer le rappel sans exécuter l'initialisation.  
  
## <a name="see-also"></a>Voir aussi

- [Vue d'ensemble du profilage](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)

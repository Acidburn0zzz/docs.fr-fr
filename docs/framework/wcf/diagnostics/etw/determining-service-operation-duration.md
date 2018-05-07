---
title: Détermination de la durée d'une opération de service
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: a7615a4574210ad6e9b5eee2e5d5855365768854
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="determining-service-operation-duration"></a>Détermination de la durée d'une opération de service
Si le traçage analytique est activé dans une application Windows Communication Foundation (WCF), la durée d’exécution d’une opération de service peut facilement être déterminée en examinant le journal des événements.  Cette rubrique montre comment déterminer la durée d'exécution d'une opération de service.  
  
### <a name="determining-service-operation-execution-duration"></a>Détermination de la durée d'exécution d'une opération de service  
  
1.  Ouvrez l’Observateur d’événements en cliquant sur **Démarrer**, **exécuter**et en entrant `eventvwr.exe`.  
  
2.  Si vous n’avez pas activé le traçage analytique, développez **journaux des Applications et Services**, **Microsoft**, **Windows**, **serveur d’applications-Applications** . Sélectionnez **vue**, **afficher d’analyse et les journaux de débogage**. Avec le bouton droit **analyse** et sélectionnez **activer le journal**. Laissez l'Observateur d'événements ouvert afin que les traces soient visibles après l'exécution de l'opération de service.  
  
3.  Ouvrez ensuite une application [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] qui inclut un projet de service et un projet client qui interagit avec ce service.  Vous pouvez créer une telle application en suivant le [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Si vous avez le [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] exemples installés, vous pouvez ouvrir le [mise en route](../../../../../docs/framework/wcf/samples/getting-started-sample.md), qui contient le projet terminé, créé dans le didacticiel.  
  
4.  Exécutez l’application serveur en appuyant sur **F5**. Exécutez l’application cliente en cliquant sur le **Client** projet et en sélectionnant **déboguer**, **démarrer une nouvelle Instance**.  
  
5.  Dans l'Observateur d'événements, actualisez le journal Analyse et triez les événements par ID d'événement.  Recherchez les événements dont l’ID d’événement [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Ces événements affichent les opérations terminées et leur durée.  L'événement suivant affiche la durée d'une opération d'ajout.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```

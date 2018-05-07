---
title: Conception et implémentation d'activités personnalisées
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 2ed80b5cbb27c6647053ee9b8f4cd2bedb0c6cde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="designing-and-implementing-custom-activities"></a>Conception et implémentation d'activités personnalisées
Dans [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)], les activités personnalisées sont créées soit en assemblant des activités fournies par le système dans des activités composites, soit en créant de nouveaux types qui dérivent des objets <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, ou <xref:System.Activities.NativeActivity>. Cette section décrit la procédure de création des activités personnalisées avec l'une ou l'autre de ces méthodes.  
  
> [!IMPORTANT]
>  Les activités personnalisées s'affichent par défaut dans le concepteur de workflow comme un rectangle simple avec le nom d'activité. Pour fournir une représentation visuelle personnalisée de votre activité dans le concepteur de workflow, vous devez également créer un concepteur personnalisé. Pour plus d’informations, consultez [à l’aide de concepteurs d’activités personnalisés et les modèles](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).  
  
## <a name="in-this-section"></a>Dans cette section  
 [Options de création d’activités](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 Traite des styles de création disponibles dans [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].  
  
 [Utilisation d’une activité personnalisée](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 Décrit comment ajouter une activité personnalisée à un projet de workflow.  
  
  [Création d’activités asynchrones](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 Décrit comment créer des activités asynchrones.  
  
 [Configuration de la validation d’activité](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 Décrit comment utiliser la validation d’activité pour identifier et signaler des erreurs dans la configuration d’une activité, avant son exécution.  
  
 [Création d’une activité en cours d’exécution](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 Explique comment créer des activités au moment de l'exécution en utilisant <xref:System.Activities.DynamicActivity>.  
  
 [Propriétés d’exécution de workflow](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 Décrit comment utiliser les propriétés d'exécution de workflow pour ajouter des propriétés spécifiques au contexte à l'environnement d'une activité.  
  
 [Utilisation de délégués d’activité](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 Explique comment créer et utiliser des activités qui contiennent des délégués d'activité.  
  
 [Localisation d’activité](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 Décrit comment utiliser la localisation des ressources de type chaîne dans les activités.  
  
 [Utilisation d’extensions d’activité](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 Décrit comment créer et utiliser des extensions d’activité.  
  
 [Consommation de flux OData à partir d’un workflow](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 Décrit plusieurs méthodes pour appeler un service de données WCF à partir d'un workflow.  
  
 [Portée et visibilité de la définition de l’activité](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 Décrit les options et les règles pour définir la portée des données et la visibilité des membres pour les activités.

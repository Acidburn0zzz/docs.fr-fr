---
title: 'Procédure : créer un service de workflow avec des activités de messagerie'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: f5bb8df5936be1890bf744300daa7ccb68e341e3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337771"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a>Procédure : créer un service de workflow avec des activités de messagerie
Cette rubrique décrit comment créer un service de workflow simple, à l'aide d'activités de messagerie. Elle est consacrée à la mécanique de création d'un service de workflow, simplement constitué d'activités de messagerie. Dans un service réel, le workflow contient de nombreuses autres activités. Le service implémente une opération nommée Echo, qui prend une chaîne et la retourne à l'appelant. Cette rubrique est la première d'une série de deux. La rubrique suivante [How To : Accéder à un Service à partir d’une Application de Workflow](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) explique comment créer une application de flux de travail qui peut appeler le service créé dans cette rubrique.  
  
### <a name="to-create-a-workflow-service-project"></a>Pour créer un projet de service de workflow  
  
1. Démarrez Visual Studio 2012.  
  
2. Cliquez sur le **fichier** menu, sélectionnez **New**, puis **projet** pour afficher le **boîte de dialogue Nouveau projet**. Sélectionnez **Workflow** dans la liste des modèles installés et **Application de Service de Workflow WCF** dans la liste des types de projets. Nommez le projet `MyWFService` et utilisez l’emplacement par défaut comme indiqué dans l’illustration suivante.  
  
     Cliquez sur le **OK** bouton pour fermer la **boîte de dialogue Nouveau projet**.  
  
3. Lorsque le projet est créé, le fichier Service1.xamlx s'ouvre dans le concepteur, comme indiqué dans l'illustration suivante.  
  
     ![Capture d’écran montre le fichier Service1.xamlx ouvert dans le concepteur.](./media/how-to-create-a-workflow-service-with-messaging-activities/default-workflow-service.jpg)  
  
     Avec le bouton droit de l’activité intitulée **Service séquentiel** et sélectionnez **supprimer**.  
  
### <a name="to-implement-the-workflow-service"></a>Pour implémenter le service de workflow  
  
1. Sélectionnez le **boîte à outils** onglet sur le côté gauche de l’écran pour afficher la boîte à outils et cliquez sur la punaise pour garder la fenêtre ouverte. Développez le **Messaging** section de la boîte à outils pour afficher les activités de messagerie et les modèles d’activité messagerie comme indiqué dans l’illustration suivante.  
  
     ![Capture d’écran montrant la boîte à outils avec section messagerie développé.](./media/how-to-create-a-workflow-service-with-messaging-activities/toolbox-messaging-section.jpg)  
  
2. Faites glisser et déposez un **ReceiveAndSendReply** modèle vers le Concepteur de flux de travail. Cette opération crée un <xref:System.Activities.Statements.Sequence> activité avec un **réception** activité suivie par un <xref:System.ServiceModel.Activities.SendReply> activité, comme indiqué dans l’illustration suivante.  
  
     ![Capture d’écran montre le modèle ReceiveAndSendReply.](./media/how-to-create-a-workflow-service-with-messaging-activities/receiveandsendreply-template.jpg)  
  
     Remarque : l'activité <xref:System.ServiceModel.Activities.SendReply> possède une propriété <xref:System.ServiceModel.Activities.SendReply.Request%2A> qui est définie sur `Receive`, le nom de l'activité <xref:System.ServiceModel.Activities.Receive> à laquelle répond l'activité <xref:System.ServiceModel.Activities.SendReply>.  
  
3. Dans le <xref:System.ServiceModel.Activities.Receive> type d’activité `Echo` dans la zone de texte intitulée **NomOpération**. Cela définit le nom de l'opération que le service implémente.  
  
     ![Capture d’écran montrant où spécifier le nom de l’opération.](./media/how-to-create-a-workflow-service-with-messaging-activities/define-operation-name.jpg)  
  
4. Avec le <xref:System.ServiceModel.Activities.Receive> activité sélectionnée, ouvrez la fenêtre Propriétés si ce n’est pas déjà ouvert en cliquant sur le **vue** menu et en sélectionnant **fenêtre Propriétés**. Dans le **fenêtre Propriétés** défiler vers le bas jusqu'à ce que vous voyiez **CanCreateInstance** et cliquez sur la case à cocher comme illustré dans l’illustration suivante. Ce paramètre active l'hôte de service de workflow pour créer une nouvelle instance du service (si requis) lorsqu'un message est reçu.  
  
     ![Capture d’écran montrant la propriété CanCreateInstance.](./media/how-to-create-a-workflow-service-with-messaging-activities/cancreateinstance-property.jpg)  
  
5. Sélectionnez le <xref:System.Activities.Statements.Sequence> activité et cliquez sur le **Variables** bouton dans le coin inférieur gauche du concepteur. Cela affiche l'éditeur de variables. Cliquez sur le **créer une Variable** lien permettant d’ajouter une variable pour stocker la chaîne envoyée à l’opération. Nommez la variable `msg` et définissez son **Variable** tapez en chaîne, comme indiqué dans l’illustration suivante.  
  
     ![Capture d’écran qui montre comment ajouter une variable.](./media/how-to-create-a-workflow-service-with-messaging-activities/add-variable-msg-string.jpg)  
  
     Cliquez sur le **Variables** bouton Nouveau pour fermer l’éditeur de variables.  
  
6. Cliquez sur le **définir...** lien dans le **contenu** zone de texte dans le <xref:System.ServiceModel.Activities.Receive> activité pour afficher le **définition du contenu** boîte de dialogue. Sélectionnez le **paramètres** case d’option, cliquez sur le **ajouter un nouveau paramètre** lien, tapez `inMsg` dans le **nom** zone de texte, sélectionnez **chaîne**dans les **Type** déroulante de la zone de liste et le type `msg` dans le **affecter à** zone de texte, comme indiqué dans l’illustration suivante.  
  
     ![Capture d’écran qui illustre l’ajout de paramètres de contenu.](./media/how-to-create-a-workflow-service-with-messaging-activities/adding-parameters-content.jpg)  
  
     Cela spécifie que l'activité Receive reçoit le paramètre de chaîne et que les données sont liées à la variable `msg`. Cliquez sur **OK** pour fermer la **définition du contenu** boîte de dialogue.  
  
7. Cliquez sur le **définir...**  lien dans le **contenu** zone le <xref:System.ServiceModel.Activities.SendReply> activité pour afficher le **définition du contenu** boîte de dialogue. Sélectionnez le **paramètres** case d’option, cliquez sur le **ajouter un nouveau paramètre** lien, tapez `outMsg` dans le **nom** zone de texte, sélectionnez **chaîne**dans les **Type** zone de liste déroulante, et `msg` dans le **valeur** zone de texte, comme indiqué dans l’illustration suivante.  
  
     ![Capture d’écran qui montre comment ajouter le paramètre outMsg.](./media/how-to-create-a-workflow-service-with-messaging-activities/outmsg-parameters-content.jpg)  
  
     Cela spécifie que l'activité <xref:System.ServiceModel.Activities.SendReply> envoie un message ou un type de contrat de message et que les données sont liées à la variable `msg`. Comme il s'agit d'une activité <xref:System.ServiceModel.Activities.SendReply>, cela signifie que les données dans `msg` sont utilisées pour remplir le message que l'activité renvoie au client. Cliquez sur **OK** pour fermer la **définition du contenu** boîte de dialogue.  
  
8. Enregistrez et générez la solution en cliquant sur le **Build** menu et en sélectionnant **générer la Solution**.  
  
## <a name="configure-the-workflow-service-project"></a>Configurer le projet du service de workflow  
 Le service de workflow est terminé. Cette section explique comment configurer la solution de service de workflow pour en faciliter l'hébergement et l'exécution. Cette solution utilise le serveur de développement ASP.NET pour héberger le service.  
  
#### <a name="to-set-project-start-up-options"></a>Pour définir les options de démarrage du projet  
  
1. Dans le **l’Explorateur de solutions**, avec le bouton droit **MyWFService** et sélectionnez **propriétés** pour afficher le **propriétés du projet** boîte de dialogue.  
  
2. Sélectionnez le **Web** onglet et sélectionnez **Page spécifique** sous **Action de démarrage** et type `Service1.xamlx` dans la zone de texte, comme indiqué dans l’illustration suivante.  
  
     ![Capture d’écran qui affiche la boîte de dialogue de propriétés de projet.](./media/how-to-create-a-workflow-service-with-messaging-activities/project-properties-dialog.jpg)  
  
     Cela héberge le service défini dans Service1.xamlx dans le serveur de développement ASP.NET.  
  
3. Appuyez sur Ctrl + F5 pour lancer le service. L'icône du serveur de développement ASP.NET s'affiche dans la partie inférieure droite du Bureau, comme le montre l'image suivante.  
  
     ![Capture d’écran montrant l’icône serveur de développement ASP.NET.](./media/how-to-create-a-workflow-service-with-messaging-activities/asp-net-dev-server-icon.jpg)  
  
     De plus, Internet Explorer affiche la page d'aide du service WCF pour le service.  
  
     ![Capture d’écran montrant la Page d’aide WCF Service.](./media/how-to-create-a-workflow-service-with-messaging-activities/wcf-service-help-page.jpg)  
  
4. Passez à la [Comment : Accéder à un Service à partir d’une Application de Workflow](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) rubrique pour créer un client de workflow qui appelle ce service.  
  
## <a name="see-also"></a>Voir aussi

- [Services de workflow](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Vue d'ensemble de l'hébergement de services de workflow](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)
- [Activités de messagerie](../../../../docs/framework/wcf/feature-details/messaging-activities.md)

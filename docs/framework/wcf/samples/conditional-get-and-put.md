---
title: GET et PUT conditionnelle
ms.date: 03/30/2017
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
ms.openlocfilehash: 29819f89327128cdd71cc89eb8d14126522dc2df
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262502"
---
# <a name="conditional-get-and-put"></a>GET et PUT conditionnelle
Cet exemple montre comment utiliser les nouvelles API de récupération et mise à jour conditionnelles du modèle de programmation REST WCF. Étant donné que la récupération conditionnelle et mise à jour sont plus appropriés pour orientés ressources et services REST, cet exemple étend la [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) exemple. Cet exemple se concentre sur l’ajout de prise en charge de récupération conditionnelle et de mise à jour le [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) exemple utilisant les nouvelles API introduites dans [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
## <a name="demonstrates"></a>Démonstrations  
 Récupération et mise à jour conditionnelles  
  
## <a name="discussion"></a>Discussion  
 Le service WCF de cet exemple expose une collection de clients d’une manière orientée ressources/REST. Pour obtenir une description détaillée de l’implémentation de service, consultez le [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) exemple.  
  
 Cet exemple ajoute récupération conditionnelle et les fonctionnalités de mise à jour pour le [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) exemple. La récupération et la mise à jour conditionnelles utilisent des étiquettes d’entité HTTP, ainsi que les en-têtes HTTP If-None-Match et If-Match pour vérifier si les clients disposent ou non de l’entité la plus récente pour une ressource donnée. Toutefois, l'implémentation du code visant à analyser correctement les en-têtes HTTP If-None-Match et If-Match peut être fastidieuse et susceptible d'engendrer des erreurs. Par conséquent, les méthodes <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> et <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> ont été ajoutées au <xref:System.ServiceModel.Web.IncomingWebRequestContext>, accessible à l'aide de l'instance actuelle du <xref:System.ServiceModel.Web.WebOperationContext>. De plus, la méthode `SetETag` a été ajoutée au <xref:System.ServiceModel.Web.OutgoingWebRequestContext> afin de faciliter le retour de balises d'entité valides.  
  
 La méthode <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> est conçue pour être utilisée avec des opérations [WebGet]. Elle prend la balise d'entité actuelle de la ressource donnée comme paramètre `entityTag`, qui peut être de type `string`, `int`, `long` ou `Guid`. La méthode <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> vérifie la balise d'entité par rapport à l'en-tête HTTP If-None-Match de la requête. Si la balise d'entité est présente dans l'en-tête HTTP If-None-Match, une exception <xref:System.ServiceModel.Web.WebFaultException> est levée, accompagnée du code d'état Non modifié (304) ; sinon, la méthode est retournée. Le mécanisme de récupération conditionnelle permet au client d'indiquer au serveur qu'il a cette entité et de n'envoyer l'entité actuelle que si le client ne l'a pas encore. Un exemple d'utilisation de la méthode <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> peut être vu dans les opérations `GetCustomer` et `GetCustomers` du service. Il est important de noter que les appels à <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> peuvent ne pas être retournés. Les développeurs doivent implémenter l'opération de sorte que la réussite de la requête soit connue avant que l'appel à <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> ne soit exécuté, afin qu'en l'absence de l'appel à <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, le service envoie une réponse avec un code d'état de réussite.  
  
 La méthode <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> est similaire à la méthode <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>. Elle prend également l’étiquette d’entité actuelle de la ressource donnée. Toutefois, il est conçu pour être utilisé avec les opérations [WebInvoke] dans laquelle la méthode a la valeur « PUT » ou « Supprimer ». La méthode <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> vérifie la balise d'entité par rapport à l'en-tête HTTP If-Match de la requête. Si la balise d'entité n'est pas présente dans l'en-tête HTTP If-Match, une exception <xref:System.ServiceModel.Web.WebFaultException> est levée, accompagnée du code d'état Échec de la condition préalable (412). Le mécanisme de mise à jour conditionnelle permet au client d'indiquer au serveur qu'il a cette entité pour la ressource et de n'autoriser le client à modifier la ressource que si l'entité dont il dispose est à jour. Un exemple d'utilisation de la méthode <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> peut être vu dans les opérations `UpdateCustomer` et `DeleteCustomer` du service. Tout comme pour <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, il est important de noter que les appels à <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> peuvent ne pas être retournés. Les développeurs doivent implémenter l'opération de sorte que la réussite de la requête soit connue avant que l'appel à <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> ne soit exécuté, afin qu'en l'absence de l'appel à <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>, le service réponde avec un code d'état de réussite.  
  
 L'exemple est constitué d'un service auto-hébergé et d'un client qui s'exécute dans une application console. Lorsque l'application console s'exécute, le client adresse des requêtes au service et affiche les informations pertinentes des réponses dans la fenêtre de console.  
  
#### <a name="to-run-the-sample"></a>Pour exécuter l'exemple  
  
1.  Ouvrez la solution de l'exemple Conditional Get and Put. Pour que l'exemple fonctionne correctement, vous devez exécuter [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] en tant qu'administrateur. Cela en double-cliquant sur le [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icône et en choisissant **exécuter en tant qu’administrateur** dans le menu contextuel.  
  
2.  Appuyez sur CTRL+MAJ+B pour générer la solution, puis appuyez sur CTRL+F5 pour exécuter le projet d'application de console. Si vous exécutez ce projet avec le débogage activé (en ayant appuyé sur F5 au lieu de CTRL+F5), le débogueur s'arrête lorsqu'une exception est levée par la vérification GET et PUT conditionnelle. Dans ce cas, appuyez sur F5 pour reprendre l'exécution de l'exemple.  
  
3.  La fenêtre de console apparaît et fournit l'URI du service en cours d'exécution, ainsi que l'URI de sa page d'aide HTML.  
  
4.  Lorsque l'exemple s'exécute, le client envoie des requêtes au service et affiche les réponses dans la fenêtre de console.  
  
5.  Appuyez sur une touche quelconque pour arrêter l'exemple.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`

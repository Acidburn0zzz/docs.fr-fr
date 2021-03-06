---
title: AJAX Service Without Configuration
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: f5ebc952fcc6c2ca4c7272a90dc1929d4b4a0eae
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331609"
---
# <a name="ajax-service-without-configuration"></a>AJAX Service Without Configuration
Cet exemple montre comment utiliser Windows Communication Foundation (WCF) pour créer un service ASP.NET Asynchronous JavaScript and XML (AJAX) base (un service auquel vous pouvez accéder à l’aide de code JavaScript à partir d’un client de navigateur Web) sans utiliser de configuration Paramètres. Le service utilise une syntaxe spéciale dans le fichier .svc pour activer automatiquement un point de terminaison AJAX.  
  
 Prise en charge d’AJAX dans WCF est optimisé pour une utilisation avec ASP.NET AJAX via le `ScriptManager` contrôle. Pour obtenir un exemple d’utilisation de WCF avec ASP.NET AJAX, consultez le [exemples Ajax](ajax.md).  
  
> [!NOTE]
>  La procédure d'installation ainsi que les instructions de génération relatives à cet exemple figurent à la fin de cette rubrique.  
  
 Cet exemple est basé sur le service AJAX Service utilisant HTTP POST. Comme décrit dans la [base AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) exemple, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> est utilisé pour héberger le service.  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> ajoute automatiquement un <xref:System.ServiceModel.Description.WebScriptEndpoint> au service. Si aucune modification de configuration ne doit être apportée au point de terminaison, la section `<system.ServiceModel>` peut être supprimée complètement du fichier Web.config pour le service. Le fichier Web.config contient des paramètres ASP.NET, qui sont utilisés par ConfigFreeClientPage.aspx. Si ce n'était pas le cas, l'intégralité du fichier Web.config pourrait être supprimée.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Pour configurer, générer et exécuter l'exemple  
  
1. Assurez-vous d’avoir suivi les instructions d’installation dans [procédure d’installation unique pour les exemples Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Générez la solution configfreeajaxservice.sln tel que décrit dans [génération des exemples Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Accédez à `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (n’ouvrez pas ConfigFreeClientPage.aspx dans le navigateur à partir du répertoire de projet).  
  
> [!NOTE]
>  Avant d’exécuter cet exemple, assurez-vous que l’authentification anonyme et que l’authentification Windows ne sont pas toutes deux activées dans le dossier ServiceModelSamples des services IIS. Si tel est le cas, désactivez l'authentification Windows. Une fois que vous avez exécuté l'exemple, activez l'authentification Windows et réexécutez « iisreset ».  
  
## <a name="see-also"></a>Voir aussi

- [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md)

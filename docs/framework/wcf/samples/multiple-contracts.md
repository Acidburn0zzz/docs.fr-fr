---
title: Multiple Contracts
ms.date: 03/30/2017
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
ms.openlocfilehash: acced4bfc79571c78e868b31b0a4db6cfbdea76a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295560"
---
# <a name="multiple-contracts"></a>Multiple Contracts
L'exemple Multiples Contracts montre comment implémenter plusieurs contrats sur un service et comment configurer des points de terminaison pour communiquer avec chacun des contrats implémentés. Cet exemple est basé sur le [mise en route](../../../../docs/framework/wcf/samples/getting-started-sample.md). Le service a été modifié afin de définir deux contrats, le contrat `ICalculator` et le contrat `ICalculatorSession`.  
  
> [!NOTE]
>  La procédure d'installation ainsi que les instructions de génération relatives à cet exemple figurent à la fin de cette rubrique.  
  
 La classe de service implémente à la fois les contrats `ICalculator` et `ICalculatorSession`. Vu que l'un des contrats requiert une session, le service utilise le mode d'instance <xref:System.ServiceModel.InstanceContextMode.PerSession> pour maintenir l'état sur la durée de vie de la session.  
  
 La configuration du service a été modifiée afin de définir deux points de terminaison et exposer chaque contrat. Le point de terminaison `ICalculator` est exposé à l'adresse de base à l'aide d'une `basicHttpBinding`. Le point de terminaison `ICalculatorSession` est exposé à l'adresse/la session de base à l'aide d'une `wsHttpBinding` avec l'attribut `bindingConfiguration` ayant la valeur `BindingWithSession`, comme le montre l'exemple de configuration suivant.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"   
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
```  
  
 Le code client généré inclut maintenant une classe de client pour le contrat `ICalculator` d'origine et pour le nouveau contrat `ICalculatorSession`. La configuration et le code client ont été modifiés pour communiquer avec chaque contrat au point de terminaison de service approprié.  
  
 Le client est une application console Windows (.exe). Le service est hébergé par les services IIS (Internet Information Services).  
  
 La fenêtre de console cliente affiche les opérations envoyées à chacun des points de terminaison, d'abord le point de terminaison de base, puis le point de terminaison sécurisé.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Pour configurer, générer et exécuter l'exemple  
  
1. Vérifiez que vous avez effectué la [procédure d’installation unique pour les exemples Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Pour générer l’édition C# ou Visual Basic .NET de la solution, conformez-vous aux instructions figurant dans [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Pour exécuter l’exemple dans une configuration unique ou plusieurs ordinateurs, suivez les instructions de [en cours d’exécution les exemples Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  

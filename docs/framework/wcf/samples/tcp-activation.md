---
title: TCP Activation
ms.date: 03/30/2017
ms.assetid: bf8c215c-0228-4f4f-85c2-e33794ec09a7
ms.openlocfilehash: 065c4706d0a52414c4abed85044ce06ad3efe35c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374919"
---
# <a name="tcp-activation"></a>TCP Activation

Cet exemple illustre l'hébergement d'un service utilisant les services d'activation des processus Windows (WAS, Windows Process Activation Services) afin d'activer un service qui communique à l'aide du protocole net.tcp. Cet exemple est basé sur le [mise en route](../../../../docs/framework/wcf/samples/getting-started-sample.md).

> [!NOTE]
> La procédure d'installation ainsi que les instructions de génération relatives à cet exemple figurent à la fin de cette rubrique.

> [!IMPORTANT]
> Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\TCPActivation`

L'exemple se compose d'un programme de console client (.exe) et d'une bibliothèque de service (.dll) hébergée dans un processus de traitement activé par le service WAS. L'activité du client est affichée dans la fenêtre de console.

Le service implémente un contrat qui définit un modèle de communication demande-réponse. Le contrat est défini par l'interface `ICalculator`, laquelle expose des opérations mathématiques (addition, soustraction, multiplication et division), tel qu'illustré dans l'exemple de code suivant :

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

L'implémentation de service calcule, puis retourne le résultat approprié :

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

Dans la version de liaison net.tcp utilisée par l'exemple, le partage de port TCP est activé et la sécurité est désactivée. Si vous souhaitez utiliser une liaison TCP sécurisée, modifiez le mode de sécurité du serveur en fonction du paramètre souhaité, puis exécutez de nouveau l'outil Svcutil.exe sur le client afin de générer un fichier de configuration à jour pour ce dernier.

L'exemple suivant contient la configuration du service :

```xml
<system.serviceModel>

    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: net.tcp://localhost/servicemodelsamples/service.svc  -->
        <endpoint binding="netTcpBinding" bindingConfiguration="PortSharingBinding"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.tcp://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexTcpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netTcpBinding>
        <binding name="PortSharingBinding" portSharingEnabled="true">
          <security mode="None" />
        </binding>
      </netTcpBinding>
    </bindings>

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

Le point de terminaison du client est configuré tel qu'illustré dans l'exemple de code suivant :

```xml
<system.serviceModel>
    <bindings>
        <netTcpBinding>
          <binding name="NetTcpBinding_ICalculator">
            <security mode="None"/>
          </binding>
        </netTcpBinding>
    </bindings>
    <client>
        <endpoint address="net.tcp://localhost/servicemodelsamples/service.svc"
            binding="netTcpBinding" bindingConfiguration="NetTcpBinding_ICalculator"
            contract="Microsoft.ServiceModel.Samples.ICalculator" name="NetTcpBinding_ICalculator" />
    </client>
</system.serviceModel>
```

Lorsque vous exécutez l'exemple, les demandes et réponses d'opération s'affichent dans la fenêtre de console du client. Appuyez sur Entrée dans la fenêtre du client pour l'arrêter.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Pour configurer, générer et exécuter l'exemple

1. Vérifiez que [!INCLUDE[iisver](../../../../includes/iisver-md.md)] est installé. [!INCLUDE[iisver](../../../../includes/iisver-md.md)] est requis pour l'activation du service WAS.

2. Vérifiez que vous avez effectué la [procédure d’installation unique pour les exemples Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

    En outre, vous devez installer les composants d’activation non-HTTP de WCF :

    1. Dans le menu **Démarrer**, cliquez sur **Panneau de configuration**.

    2. Sélectionnez **programmes et fonctionnalités**.

    3. Cliquez sur **activer ou désactiver les composants de Windows**.

    4. Développez le **Microsoft .NET Framework 3.0** nœud et vérifiez la **Activation Non-HTTP de Windows Communication Foundation** fonctionnalité.

3. Configurez le servie WAS afin d'assurer la prise en charge de l'activation TCP.

    Pour des raisons pratiques, les deux étapes suivantes sont implémentées dans le fichier de commandes AddNetTcpSiteBinding.cmd se trouvant dans le répertoire de l'exemple.

    1. Pour assurer la prise en charge de l'activation de net.tcp, le site Web par défaut doit d'abord être lié à un port net.tcp. Vous pouvez utiliser Appcmd.exe, installé avec les outils de gestion des services IIS 7.0, à cette fin. Sous un compte d'administrateur, exécutez la commande suivante à partir d'une invite de commandes :

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!TIP]
        > Cette commande est une ligne unique de texte. Cette commande ajoute une liaison de site net.tcp au site Web par défaut qui écoute sur le port TCP 808, quel que soit le nom d'hôte.

    2. Bien que toutes les applications d'un site partagent la même liaison net.tcp, chacune d'elle peut activer de manière individuelle la prise en charge net.pipe. Afin d'activer le net.tcp pour l'application /servicemodelsamples, exécutez la commande suivante à partir d'une invite de commandes, sous un compte d'administrateur :

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.tcp
        ```

        > [!NOTE]
        > Cette commande est une ligne unique de texte. Cette commande active l’application accessible à l’aide de deux `http://localhost/servicemodelsamples` et `net.tcp://localhost/servicemodelsamples`.

4. Pour générer l’édition C# ou Visual Basic .NET de la solution, conformez-vous aux instructions figurant dans [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

5. Pour exécuter l’exemple dans une configuration unique ou plusieurs ordinateurs, suivez les instructions de [en cours d’exécution les exemples Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

    Supprimez la liaison de site net.tcp que vous avez ajoutée dans le cadre de cet exemple.

    Pour des raisons pratiques, les deux étapes suivantes sont implémentées dans le fichier de commandes RemoveNetTcpSiteBinding.cmd situé dans le répertoire de l'exemple.

    1. Supprimez le protocole net.tcp de la liste des protocoles activés en exécutant la commande suivante à partir d'une invite de commandes en tant qu'administrateur :

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > Cette commande doit être entrée comme une ligne unique de texte.

    2. Supprimez la liaison de site net.tcp en exécutant la commande suivante à partir d'une invite de commandes en tant qu'administrateur :

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > Cette commande doit être tapée comme une ligne unique de texte.

## <a name="see-also"></a>Voir aussi

- [Hébergement AppFabric et exemples de persistance](https://go.microsoft.com/fwlink/?LinkId=193961)

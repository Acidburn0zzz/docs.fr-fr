---
title: 'Procédure : héberger un service WCF dans un service Windows managé'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: c63b249cf16100f0b18d622fdecd7cd375df83d8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297757"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a>Procédure : héberger un service WCF dans un service Windows managé

Cette rubrique décrit les étapes de base requises pour créer un service Windows Communication Foundation (WCF) qui est hébergé par un Service Windows. Le scénario est activé par le service Windows managé qui héberge l’option est un service WCF de longs hébergé en dehors d’Internet Information Services (IIS) dans un environnement sécurisé qui n’est pas activé de message. La durée de vie du service est contrôlée par le système d'exploitation. Cette option d'hébergement est disponible dans toutes les versions de Windows.

Les services Windows peuvent être gérés avec Microsoft.ManagementConsole.SnapIn dans MMC (Microsoft Management Console) et peuvent être configurés pour démarrer automatiquement lorsque le système démarre. Cette option d’hébergement consiste à enregistrer le domaine d’application (AppDomain) qui héberge un service WCF en tant qu’un service Windows managé afin que la durée de vie du processus du service est contrôlée par le Gestionnaire de contrôle de services (SCM) pour les services de Windows.

Le code du service inclut l'implémentation du contrat de service, d'une classe de service Windows et d'une classe Installer. La classe d’implémentation, `CalculatorService`, est un service WCF. Le `CalculatorWindowsService` est un service Windows. Pour prétendre au titre de service Windows, la classe hérite de la `ServiceBase` et implémente les méthodes `OnStart` et `OnStop`. Dans la méthode `OnStart`, un objet <xref:System.ServiceModel.ServiceHost> est créé pour le type `CalculatorService` et est ouvert. Dans la méthode `OnStop`, le service est arrêté et éliminé. L'hôte est également chargé de fournir une adresse de base à l'hôte de service, qui a été configuré dans les paramètres d'application. La classe Installer, qui hérite de <xref:System.Configuration.Install.Installer>, permet à l'outil Installutil.exe d'installer le programme comme un service Windows.

## <a name="construct-the-service-and-provide-the-hosting-code"></a>Construction du service et ajout du code d'hébergement

1. Créer un nouveau Visual Studio **application Console** projet appelé **Service**.

2. Renommez Program.cs en Service.cs.

3. Modifier l’espace de noms `Microsoft.ServiceModel.Samples`.

4. Ajoutez des références aux assemblys suivants :

    - System.ServiceModel.dll

    - System.ServiceProcess.dll

    - System.Configuration.Install.dll

5. Ajoutez les instructions using suivantes à Service.cs.

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. Définissez le contrat de service `ICalculator`, tel qu'indiqué dans le code suivant.

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. Implémentez le contrat de service dans une classe appelée `CalculatorService`, tel qu'indiqué dans le code suivant.

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. Créez une classe appelée `CalculatorWindowsService` qui hérite de la classe <xref:System.ServiceProcess.ServiceBase>. Ajoutez une variable locale appelée `serviceHost` pour faire référence à l'instance <xref:System.ServiceModel.ServiceHost>. Définir le `Main` méthode qui appelle `ServiceBase.Run(new CalculatorWindowsService)`

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. Substituez la méthode <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> en créant et en ouvrant une nouvelle instance <xref:System.ServiceModel.ServiceHost>, comme illustré dans le code suivant.

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. Substituez la méthode <xref:System.ServiceProcess.ServiceBase.OnStop%2A> fermant <xref:System.ServiceModel.ServiceHost>, comme illustré dans le code suivant.

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. Créez une classe appelée `ProjectInstaller` qui hérite de <xref:System.Configuration.Install.Installer> et qui est marquée avec <xref:System.ComponentModel.RunInstallerAttribute> défini avec la valeur `true`. Cela permet au service Windows d'être installé par l'outil Installutil.exe.

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. Supprimez la classe `Service` qui a été générée lors de la création du projet.

13. Ajoutez un fichier de configuration d'application au projet. Remplacez le contenu du fichier par le fichier XML de configuration suivant.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.serviceModel>    <services>
          <!-- This section is optional with the new configuration model
               introduced in .NET Framework 4. -->
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"
                   behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
            <endpoint address=""
                      binding="wsHttpBinding"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />
          </service>
        </services>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceMetadata httpGetEnabled="true"/>
              <serviceDebug includeExceptionDetailInFaults="False"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>
      </system.serviceModel>
    </configuration>
    ```

     Cliquez avec le bouton droit sur le fichier App.config dans le **l’Explorateur de solutions** et sélectionnez **propriétés**. Sous **Copy to Output Directory** sélectionnez **Copier si plus récent**.

     L'exemple spécifie explicitement les points de terminaison dans le fichier de configuration. Si vous n'ajoutez pas de points de terminaison au service, le runtime ajoute les points de terminaison par défaut. Dans cet exemple, étant donné que le service a un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> défini sur la valeur `true`, la publication des métadonnées est également activée pour votre service. Pour plus d’informations sur les points de terminaison, les liaisons et les comportements par défaut, consultez [Configuration simplifiée](../../../../docs/framework/wcf/simplified-configuration.md) et [Configuration simplifiée pour les services WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

## <a name="install-and-run-the-service"></a>Démarrez et exécutez le service.

1. Générez la solution pour créer l'exécutable `Service.exe`.

2. Ouvrez l’invite de commandes développeur pour Visual Studio et accédez au répertoire du projet. Pour installer le service Windows, tapez `installutil bin\service.exe` à l'invite de commandes.

     Tapez `services.msc` à l'invite de commandes pour accéder au Gestionnaire de contrôle des services (SCM). Le service Windows doit apparaître dans les services comme « WCFWindowsServiceSample ». Le service WCF peut répondre aux clients uniquement si le service Windows est en cours d’exécution. Pour démarrer le service, faites un clic droit dans le SCM et sélectionnez « Start » ou type **net start WCFWindowsServiceSample** à l’invite de commandes.

3. Si vous apportez des modifications au service, vous devez d'abord l'arrêter et le désinstaller. Pour arrêter le service, cliquez sur le service dans le GCL et sélectionnez « Arrêter » ou **stop net de type WCFWindowsServiceSample** à l’invite de commandes. Notez que si vous arrêtez le service Windows puis exécutez un client, une exception <xref:System.ServiceModel.EndpointNotFoundException> se produit lorsqu'un client tente d'accéder au service. Pour désinstaller le type de service Windows **installutil /u bin\service.exe** à l’invite de commandes.

## <a name="example"></a>Exemple

Voici une liste complète du code utilisé dans cette rubrique :

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

Comme pour l'option d'auto-hébergement, l'environnement d'hébergement du service Windows requiert que le code d'hébergement soit écrit dans le cadre de l'application. Le service est implémenté en tant qu'application console et contient son propre code d'hébergement. Dans d'autres environnements d'hébergement, tels que le service d'activation des processus Windows (WAS) dans les services IIS (Internet Information Services), il n'est pas nécessaire que les développeurs écrivent le code d'hébergement.

## <a name="see-also"></a>Voir aussi

- [Configuration simplifiée](../../../../docs/framework/wcf/simplified-configuration.md)
- [Hébergement dans une application managée](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)
- [Hébergement de services](../../../../docs/framework/wcf/hosting-services.md)
- [Fonctionnalités d’hébergement de Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)
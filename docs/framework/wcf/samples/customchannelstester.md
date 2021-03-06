---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: 7402ac9ccc0e5e1777fa77f339d7605e1d306e13
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312668"
---
# <a name="customchannelstester"></a>CustomChannelsTester
`CustomChannelsTester` est un outil utilisé pour tester vos implémentations de canal personnalisées sur un jeu de contrats de service prédéfinis. Vous pouvez sélectionner le jeu de contrats de service et le transmettre à l'outil à l'aide d'un fichier XML. L'outil génère ensuite le service et le client qui effectue vos implémentations de canal personnalisées pendant l'échange de messages.  
  
### <a name="to-build-the-tool"></a>Pour générer l'outil  
  
1. Pour générer la solution, suivez les instructions de [génération des exemples Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. La génération de la solution crée trois fichiers : CustomChannelsTester.exe, TestSpec.xml et SampleRun.cmd. CustomChannelsTester.exe, TestSpec.xml et SampleRun.cmd. Le fichier SampleRun.cmd comprend un exemple de ligne de commande qui montre comment utiliser cet outil pour tester le [Transport : UDP](../../../../docs/framework/wcf/samples/transport-udp.md) exemple.  
  
### <a name="to-run-the-tool"></a>Pour exécuter l'outil  
  
-   À l'invite de commandes, tapez la commande suivante :  
  
    ```  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     L'utilisation de l'option `/binding` est obligatoire.  
  
     `/dll` est requis si « binding » n’est pas une liaison fournie par le système fournie par Windows Communication Foundation (WCF).  
  
     `/testspec` est facultatif.  
  
     Cela crée le serveur et les clients basés sur les caractéristiques de test et la liaison.  
  
     Exécute le client et le serveur, et retourne les résultats.  
  
     Voici l'exemple XML pour la description des caractéristiques de test (testspec.xml) :  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the CLient. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  

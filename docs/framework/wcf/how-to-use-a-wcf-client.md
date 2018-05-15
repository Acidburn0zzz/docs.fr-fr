---
title: 'Comment : utiliser un client Windows Communication Foundation'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 79431588e27b02a40d5898929f1bdf644c8a79cd
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="3706f-102">Comment : utiliser un client Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="3706f-102">How to: Use a Windows Communication Foundation Client</span></span>
<span data-ttu-id="3706f-103">Il s’agit de la dernière des six tâches requises pour créer une application Windows Communication Foundation (WCF) de base.</span><span class="sxs-lookup"><span data-stu-id="3706f-103">This is the last of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="3706f-104">Pour une vue d’ensemble des six tâches, consultez la [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) rubrique.</span><span class="sxs-lookup"><span data-stu-id="3706f-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="3706f-105">Une fois qu’un proxy de Windows Communication Foundation (WCF) a été créé et configuré, une instance du client peut être créée et l’application cliente peut être compilée et utilisée pour communiquer avec le service WCF.</span><span class="sxs-lookup"><span data-stu-id="3706f-105">Once a Windows Communication Foundation (WCF) proxy has been created and configured, a client instance can be created and the client application can be compiled and used to communicate with the WCF service.</span></span> <span data-ttu-id="3706f-106">Cette rubrique décrit les procédures pour l’instanciation et à l’aide d’un client WCF.</span><span class="sxs-lookup"><span data-stu-id="3706f-106">This topic describes procedures for instantiating and using a WCF client.</span></span> <span data-ttu-id="3706f-107">Cette procédure accomplit trois tâches :</span><span class="sxs-lookup"><span data-stu-id="3706f-107">This procedure does three things:</span></span>  
  
1.  <span data-ttu-id="3706f-108">Instancie un client WCF.</span><span class="sxs-lookup"><span data-stu-id="3706f-108">Instantiates a WCF client.</span></span>  
  
2.  <span data-ttu-id="3706f-109">Appelle les opérations de service à partir du proxy généré.</span><span class="sxs-lookup"><span data-stu-id="3706f-109">Calls the service operations from the generated proxy.</span></span>  
  
3.  <span data-ttu-id="3706f-110">Ferme le client une fois que l'appel de l'opération est terminé.</span><span class="sxs-lookup"><span data-stu-id="3706f-110">Closes the client once the operation call is completed.</span></span>  
  
### <a name="to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="3706f-111">Pour utiliser un client Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="3706f-111">To use a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="3706f-112">Ouvrez le fichier Program.cs ou Program.vb du projet GettingStartedClient et remplacez le code existant par le code suivant :</span><span class="sxs-lookup"><span data-stu-id="3706f-112">Open the Program.cs or Program.vb file from the GettingStartedClient project and replace the existing code with the following code:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using GettingStartedClient.ServiceReference1;  
  
    namespace GettingStartedClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                //Step 1: Create an instance of the WCF proxy.  
                CalculatorClient client = new CalculatorClient();  
  
                // Step 2: Call the service operations.  
                // Call the Add service operation.  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Subtract service operation.  
                value1 = 145.00D;  
                value2 = 76.54D;  
                result = client.Subtract(value1, value2);  
                Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Multiply service operation.  
                value1 = 9.00D;  
                value2 = 81.25D;  
                result = client.Multiply(value1, value2);  
                Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Divide service operation.  
                value1 = 22.00D;  
                value2 = 7.00D;  
                result = client.Divide(value1, value2);  
                Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
                //Step 3: Closing the client gracefully closes the connection and cleans up resources.  
                client.Close();  
            }  
        }  
    }  
    ```  
  
    ```  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.Text  
    Imports System.ServiceModel  
    Imports GettingStartedClientVB2.ServiceReference1  
  
    Module Module1  
  
        Sub Main()  
            ' Step 1: Create an instance of the WCF proxy  
            Dim Client As New CalculatorClient()  
  
            'Step 2: Call the service operations.  
            'Call the Add service operation.  
            Dim value1 As Double = 100D  
            Dim value2 As Double = 15.99D  
            Dim result As Double = Client.Add(value1, value2)  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Subtract service operation.  
            value1 = 145D  
            value2 = 76.54D  
            result = Client.Subtract(value1, value2)  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Multiply service operation.  
            value1 = 9D  
            value2 = 81.25D  
            result = Client.Multiply(value1, value2)  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Divide service operation.  
            value1 = 22D  
            value2 = 7D  
            result = Client.Divide(value1, value2)  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)  
  
            ' Step 3: Closing the client gracefully closes the connection and cleans up resources.  
            Client.Close()  
  
            Console.WriteLine()  
            Console.WriteLine("Press <ENTER> to terminate client.")  
            Console.ReadLine()  
  
        End Sub  
  
    End Module  
    ```  
  
     <span data-ttu-id="3706f-113">Notez l'utilisation ou importez l'instruction qui importe le GettingStartedClient.ServiceReference1.</span><span class="sxs-lookup"><span data-stu-id="3706f-113">Notice the using or imports statement that imports the GettingStartedClient.ServiceReference1.</span></span> <span data-ttu-id="3706f-114">Cette opération importe le code généré par Ajouter une référence de service dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3706f-114">This imports the code generated by Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="3706f-115">Le code instancie le proxy WCF, puis appelle chacune des opérations de service exposées par le service de calculatrice, ferme le proxy et se termine.</span><span class="sxs-lookup"><span data-stu-id="3706f-115">The code instantiates the WCF proxy and then calls each of the service operations exposed by the calculator service, closes the proxy and terminates.</span></span>  
  
 <span data-ttu-id="3706f-116">Vous avez maintenant terminé le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="3706f-116">You have now completed the tutorial.</span></span> <span data-ttu-id="3706f-117">Vous avez défini un contrat de service, implémenté le contrat de service, généré un proxy WCF, configuré une application cliente WCF, puis utilisé le proxy pour appeler des opérations de service.</span><span class="sxs-lookup"><span data-stu-id="3706f-117">You defined a service contract, implemented the service contract, generated a WCF proxy, configured a WCF client application, and then used the proxy to call service operations.</span></span> <span data-ttu-id="3706f-118">Pour tester l'application, exécutez d'abord GettingStartedHost pour démarrer le service, puis exécutez GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="3706f-118">To test out the application first run GettingStartedHost to start the service and then run GettingStartedClient.</span></span> <span data-ttu-id="3706f-119">La sortie de GettingStartedHost doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="3706f-119">The output from GettingStartedHost should look like this:</span></span>  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 <span data-ttu-id="3706f-120">La sortie de GettingStartedClient doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="3706f-120">The output from GettingStartedClient should look like this:</span></span>  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a><span data-ttu-id="3706f-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3706f-121">See Also</span></span>  
 [<span data-ttu-id="3706f-122">Génération de clients</span><span class="sxs-lookup"><span data-stu-id="3706f-122">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 [<span data-ttu-id="3706f-123">Guide pratique pour créer un client</span><span class="sxs-lookup"><span data-stu-id="3706f-123">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="3706f-124">Didacticiel Bien démarrer</span><span class="sxs-lookup"><span data-stu-id="3706f-124">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="3706f-125">Programmation WCF de base</span><span class="sxs-lookup"><span data-stu-id="3706f-125">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="3706f-126">Guide pratique pour créer un contrat duplex</span><span class="sxs-lookup"><span data-stu-id="3706f-126">How to: Create a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="3706f-127">Guide pratique pour accéder aux services ayant un contrat duplex</span><span class="sxs-lookup"><span data-stu-id="3706f-127">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="3706f-128">Prise en main</span><span class="sxs-lookup"><span data-stu-id="3706f-128">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="3706f-129">Auto-hébergement</span><span class="sxs-lookup"><span data-stu-id="3706f-129">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)

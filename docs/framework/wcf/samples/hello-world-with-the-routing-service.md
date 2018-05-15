---
title: Hello World avec le service de routage
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 881636097cf342de09164804c6df6acfbcd97c45
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="2a516-102">Hello World avec le service de routage</span><span class="sxs-lookup"><span data-stu-id="2a516-102">Hello World with the Routing Service</span></span>
<span data-ttu-id="2a516-103">Cet exemple montre comment le Service de routage de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2a516-103">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="2a516-104">Le Service de routage est un composant WCF qui facilite l’inclusion d’un routeur basé sur le contenu dans votre application.</span><span class="sxs-lookup"><span data-stu-id="2a516-104">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="2a516-105">Cet exemple adapte l’exemple de calculatrice WCF standard afin de communiquer avec le Service de routage.</span><span class="sxs-lookup"><span data-stu-id="2a516-105">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="2a516-106">Dans cet exemple, le client Calculator est configuré pour envoyer des messages à un point de terminaison exposé par le routeur.</span><span class="sxs-lookup"><span data-stu-id="2a516-106">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="2a516-107">Le service de routage (Routing Service) est configuré de façon à accepter tous les messages qui lui sont envoyés et les transférer à un point de terminaison qui correspond au service Calculator.</span><span class="sxs-lookup"><span data-stu-id="2a516-107">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="2a516-108">Les messages envoyés à partir du client sont donc reçus par le routeur et reroutés au véritable service Calculator.</span><span class="sxs-lookup"><span data-stu-id="2a516-108">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="2a516-109">Les messages du service Calculator sont renvoyés au routeur, qui à son tour les retransmet au client Calculator.</span><span class="sxs-lookup"><span data-stu-id="2a516-109">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="2a516-110">Pour utiliser cet exemple</span><span class="sxs-lookup"><span data-stu-id="2a516-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="2a516-111">À l'aide de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], ouvrez HelloRoutingService.sln.</span><span class="sxs-lookup"><span data-stu-id="2a516-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open HelloRoutingService.sln.</span></span>  
  
2.  <span data-ttu-id="2a516-112">Appuyez sur F5 ou CTRL+MAJ+B.</span><span class="sxs-lookup"><span data-stu-id="2a516-112">Press F5 or CTRL+SHIFT+B.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a516-113">Si vous appuyez sur F5, le client Calculator démarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="2a516-113">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="2a516-114">Si vous appuyez sur CTRL+MAJ+B (génération), vous devez démarrer vous-même les applications suivantes.</span><span class="sxs-lookup"><span data-stu-id="2a516-114">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>  
    >   
    >  1.  <span data-ttu-id="2a516-115">Client Calculator (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="2a516-115">Calculator client (./CalculatorClient/bin/client.exe</span></span>  
    > 2.  <span data-ttu-id="2a516-116">Service Calculator (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="2a516-116">Calculator service (./CalculatorService/bin/service.exe)</span></span>  
    > 3.  <span data-ttu-id="2a516-117">Routing service (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="2a516-117">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>  
  
3.  <span data-ttu-id="2a516-118">Appuyez sur ENTRÉE pour démarrer le client.</span><span class="sxs-lookup"><span data-stu-id="2a516-118">Press ENTER to start the client.</span></span>  
  
     <span data-ttu-id="2a516-119">Vous devez voir la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="2a516-119">You should see the following output:</span></span>  
  
     <span data-ttu-id="2a516-120">Add(100,15.99) = 115.99</span><span class="sxs-lookup"><span data-stu-id="2a516-120">Add(100,15.99) = 115.99</span></span>  
  
     <span data-ttu-id="2a516-121">Subtract(145,76.54) = 68.46</span><span class="sxs-lookup"><span data-stu-id="2a516-121">Subtract(145,76.54) = 68.46</span></span>  
  
     <span data-ttu-id="2a516-122">Multiply(9,81.25) = 731.25</span><span class="sxs-lookup"><span data-stu-id="2a516-122">Multiply(9,81.25) = 731.25</span></span>  
  
     <span data-ttu-id="2a516-123">Divide(22,7) = 3.14285714285714</span><span class="sxs-lookup"><span data-stu-id="2a516-123">Divide(22,7) = 3.14285714285714</span></span>  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="2a516-124">Configurable au moyen d'un code ou d'un fichier App.config</span><span class="sxs-lookup"><span data-stu-id="2a516-124">Configurable via Code or App.Config</span></span>  
 <span data-ttu-id="2a516-125">L'exemple est fourni en étant configuré de façon à utiliser un fichier App.config pour définir le comportement du routeur.</span><span class="sxs-lookup"><span data-stu-id="2a516-125">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="2a516-126">Vous pouvez également renommer le fichier App.config afin qu'il ne soit pas reconnu et supprimer les marques de commentaire de l'appel de méthode à ConfigureRouterViaCode().</span><span class="sxs-lookup"><span data-stu-id="2a516-126">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="2a516-127">Quelle que soit la méthode employée, le comportement de routeur obtenu est le même.</span><span class="sxs-lookup"><span data-stu-id="2a516-127">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="2a516-128">Scénario</span><span class="sxs-lookup"><span data-stu-id="2a516-128">Scenario</span></span>  
 <span data-ttu-id="2a516-129">Cet exemple illustre l'utilisation du routeur en tant que pompe de messages de base.</span><span class="sxs-lookup"><span data-stu-id="2a516-129">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="2a516-130">Le service de routage fait office de nœud de proxy transparent configuré pour passer les messages directement à un ensemble préconfiguré de points de terminaison de destination.</span><span class="sxs-lookup"><span data-stu-id="2a516-130">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="2a516-131">Scénario réel</span><span class="sxs-lookup"><span data-stu-id="2a516-131">Real World Scenario</span></span>  
 <span data-ttu-id="2a516-132">Contoso souhaite augmenter la flexibilité en matière d'affectation de noms, d'adressage, de configuration et de sécurité de ses services.</span><span class="sxs-lookup"><span data-stu-id="2a516-132">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="2a516-133">Pour ce faire, la société place une pompe de messages de base devant ses services, qui fera office de point de terminaison face au public.</span><span class="sxs-lookup"><span data-stu-id="2a516-133">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="2a516-134">Cela lui permet de renforcer la sécurité devant ses véritables services et de simplifier l'implémentation de solutions à montée en puissance parallèle ou du contrôle des versions du service à une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="2a516-134">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a516-135">Les exemples peuvent déjà être installés sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2a516-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2a516-136">Recherchez le répertoire (par défaut) suivant avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="2a516-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a516-137">Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples Windows Workflow Foundation (WF) pour .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples.</span><span class="sxs-lookup"><span data-stu-id="2a516-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a516-138">Cet exemple se trouve dans le répertoire suivant.</span><span class="sxs-lookup"><span data-stu-id="2a516-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="2a516-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a516-139">See Also</span></span>  
 [<span data-ttu-id="2a516-140">Hébergement de AppFabric et exemples de persistance</span><span class="sxs-lookup"><span data-stu-id="2a516-140">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)

---
title: Reconfiguration dynamique
ms.date: 03/30/2017
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
ms.openlocfilehash: a147a1d6cf61001832661376363ecc850ecad309
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537460"
---
# <a name="dynamic-reconfiguration"></a><span data-ttu-id="09612-102">Reconfiguration dynamique</span><span class="sxs-lookup"><span data-stu-id="09612-102">Dynamic Reconfiguration</span></span>
<span data-ttu-id="09612-103">Cet exemple montre le service de routage de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="09612-103">This sample demonstrates the Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="09612-104">Le service de routage est un composant WCF qui facilite l’inclusion d’un routeur basé sur le contenu dans votre application.</span><span class="sxs-lookup"><span data-stu-id="09612-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="09612-105">Cet exemple adapte l’exemple de calculatrice WCF standard afin de communiquer avec le service de routage.</span><span class="sxs-lookup"><span data-stu-id="09612-105">This sample adapts the standard WCF Calculator Sample to communicate using the routing service.</span></span> <span data-ttu-id="09612-106">Il montre comment le service de routage peut être reconfiguré dynamiquement pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="09612-106">This sample shows how the routing service can be dynamically reconfigured during runtime.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="09612-107">Les exemples peuvent déjà être installés sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="09612-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="09612-108">Recherchez le répertoire (par défaut) suivant avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="09612-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="09612-109">Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples.</span><span class="sxs-lookup"><span data-stu-id="09612-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="09612-110">Cet exemple se trouve dans le répertoire suivant.</span><span class="sxs-lookup"><span data-stu-id="09612-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="09612-111">Détails de l'exemple</span><span class="sxs-lookup"><span data-stu-id="09612-111">Sample Details</span></span>  
 <span data-ttu-id="09612-112">Pour reconfigurer dynamiquement le service de routage (Routing Service) pendant l'exécution, cet exemple déclenche toutes les cinq secondes un minuteur qui crée un objet <xref:System.ServiceModel.Routing.RoutingConfiguration> et l'applique.</span><span class="sxs-lookup"><span data-stu-id="09612-112">To dynamically reconfigure the routing service during runtime, this sample fires a timer every five seconds that creates a new <xref:System.ServiceModel.Routing.RoutingConfiguration> object and applies it.</span></span> <span data-ttu-id="09612-113">Cette configuration fait référence au point de terminaison soit Regular Calculator, soit Rounding Calculator.</span><span class="sxs-lookup"><span data-stu-id="09612-113">This configuration references either the regular Calculator endpoint or the Rounding Calculator endpoint.</span></span> <span data-ttu-id="09612-114">Les messages retournés à l'application Calculator Client proviennent de l'un ou l'autre de ces services, selon le service de routage configuré pour assurer le routage à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="09612-114">The Calculator Client application has its messages returned from one service or the other, depending on which one the routing service is configured to route to at that time.</span></span>  
  
 <span data-ttu-id="09612-115">Il est fait appel à la capacité de reconfiguration dynamique du service de routage via un comportement personnalisé.</span><span class="sxs-lookup"><span data-stu-id="09612-115">The routing service’s capabilitiy for dynamic reconfiguration through a custom behavior is used.</span></span> <span data-ttu-id="09612-116">Ce comportement personnalisé joint une extension de service contenant un simple minuteur de thread qui se déclenche toutes les cinq secondes, ce qui aboutit à un rappel à la méthode `UpdateRules`.</span><span class="sxs-lookup"><span data-stu-id="09612-116">This custom behavior attaches a service extension, which contains a simple thread timer that fires every five seconds, which results in a callback to the `UpdateRules` method.</span></span> <span data-ttu-id="09612-117">Ce rappel crée et applique la nouvelle configuration de routage.</span><span class="sxs-lookup"><span data-stu-id="09612-117">This callback creates and applies the new routing configuration.</span></span> <span data-ttu-id="09612-118">Dans un déploiement réel, ce rappel interviendrait probablement suite à un autre type d'événement, comme une notification d'événements SQL ou une annonce WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="09612-118">In an actual deployment, this callback would likely be accomplished as a result of some other type of event, such as a SQL-Event notification, or a WS-Discovery announcement.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="09612-119">Pour utiliser cet exemple</span><span class="sxs-lookup"><span data-stu-id="09612-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="09612-120">À l'aide de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], ouvrez DynamicReconfiguration.sln.</span><span class="sxs-lookup"><span data-stu-id="09612-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open DynamicReconfiguration.sln.</span></span>  
  
2.  <span data-ttu-id="09612-121">Pour ouvrir **l’Explorateur de solutions**, sélectionnez **l’Explorateur de solutions** à partir de la **vue** menu.</span><span class="sxs-lookup"><span data-stu-id="09612-121">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="09612-122">Appuyez sur **F5** ou **CTRL + MAJ + B** dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="09612-122">Press **F5** or **CTRL+SHIFT+B** in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="09612-123">Si vous souhaitez lancer automatiquement les projets nécessaires lorsque vous appuyez sur **F5**, avec le bouton droit de la solution et sélectionnez **propriétés**.</span><span class="sxs-lookup"><span data-stu-id="09612-123">If you would like to auto-launch the necessary projects when you press **F5**, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="09612-124">Sélectionnez le **projet de démarrage** nœud sous **propriétés communes** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="09612-124">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="09612-125">Sélectionnez le **plusieurs projets de démarrage** case d’option et tous les projets d’avoir défini la **Démarrer** action.</span><span class="sxs-lookup"><span data-stu-id="09612-125">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="09612-126">Si vous générez le projet avec **CTRL + MAJ + B**, vous devez démarrer les applications suivantes :</span><span class="sxs-lookup"><span data-stu-id="09612-126">If you build the project with **CTRL+SHIFT+B**, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="09612-127">Client Calculator (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="09612-127">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="09612-128">Service Calculator (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="09612-128">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="09612-129">Service Rounding Calculator (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="09612-129">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="09612-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="09612-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="09612-131">Dans la fenêtre de console du client Calculator, appuyez sur ENTRÉE pour démarrer le client et appeler les opérations du service Calculator.</span><span class="sxs-lookup"><span data-stu-id="09612-131">In the console window of the Calculator Client, press ENTER to start the client and to call the Calculator service operations.</span></span>  
  
     <span data-ttu-id="09612-132">Le service de routage route dynamiquement des messages en alternant entre Rounding Calculator et Regular Calculator, étant donné que la configuration du routage change de configuration de façon dynamique toutes les cinq secondes.</span><span class="sxs-lookup"><span data-stu-id="09612-132">The routing service routes messages to the Rounding Calculator and to the regular Calculator alternately as the routing configuration changes dynamically every five seconds.</span></span> <span data-ttu-id="09612-133">Les sorties fournies dans la fenêtre de console du client diffèrent donc en fonction du point de terminaison auquel le service de routage envoie les messages.</span><span class="sxs-lookup"><span data-stu-id="09612-133">Depending on which endpoint the routing service is configured to send messages to there are different outputs in the client console window.</span></span>  
  
5.  <span data-ttu-id="09612-134">Appuyez sur ENTRÉE à plusieurs reprises pendant plus de cinq secondes et observez la modification dans les résultats du service.</span><span class="sxs-lookup"><span data-stu-id="09612-134">Continue pressing ENTER repeatedly over more than five seconds and observe the change in the results from the service.</span></span>  
  
    1.  <span data-ttu-id="09612-135">Voici la sortie retournée si le service de routage est configuré pour router les messages vers le service Rounding Calculator.</span><span class="sxs-lookup"><span data-stu-id="09612-135">The following is the output returned if the Router Service is configured to route messages to the Rounding Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="09612-136">Voici la sortie retournée si le service de routage est configuré pour router les messages vers le service Regular Calculator.</span><span class="sxs-lookup"><span data-stu-id="09612-136">The following is the output returned if the routing service is configured to route messages to the regular Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  <span data-ttu-id="09612-137">Le service Calculator et le service Rounding Calculator génèrent également un journal des opérations appelé dans leur fenêtre de console.</span><span class="sxs-lookup"><span data-stu-id="09612-137">The Calculator Service and the Rounding Calculator Service also print out a log of the operations invoked to their respective console windows.</span></span>  
  
7.  <span data-ttu-id="09612-138">Dans la fenêtre de console client, tapez « quit » et appuyez sur ENTRÉE pour quitter.</span><span class="sxs-lookup"><span data-stu-id="09612-138">In the client console window, type "quit" and press ENTER to exit.</span></span>  
  
8.  <span data-ttu-id="09612-139">Appuyez sur ENTRÉE dans les fenêtres de console des services pour les arrêter.</span><span class="sxs-lookup"><span data-stu-id="09612-139">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="09612-140">Scénario</span><span class="sxs-lookup"><span data-stu-id="09612-140">Scenario</span></span>  
 <span data-ttu-id="09612-141">Cet exemple illustre l'utilisation du routeur en tant que routeur basé sur le contenu qui autorise l'exposition via un même point de terminaison de plusieurs types ou implémentations de services.</span><span class="sxs-lookup"><span data-stu-id="09612-141">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="09612-142">Scénario réel</span><span class="sxs-lookup"><span data-stu-id="09612-142">Real World Scenario</span></span>  
 <span data-ttu-id="09612-143">Contoso souhaite virtualiser tous ses services afin de n'exposer publiquement qu'un seul point de terminaison via lequel donner accès à différents types de services.</span><span class="sxs-lookup"><span data-stu-id="09612-143">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="09612-144">Dans ce cas, la société utilise les fonctions de routage basé sur le contenu du service de routage afin de déterminer l'endroit où doivent être envoyées les demandes entrantes.</span><span class="sxs-lookup"><span data-stu-id="09612-144">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09612-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09612-145">See Also</span></span>  
 [<span data-ttu-id="09612-146">Hébergement AppFabric et exemples de persistance</span><span class="sxs-lookup"><span data-stu-id="09612-146">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)

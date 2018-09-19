---
title: Exemple de point de terminaison de gestion de workflow
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: 3d99cbef20895381f5e40ee939e1d94a409f1391
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2018
ms.locfileid: "45998530"
---
# <a name="workflow-management-endpoint-sample"></a><span data-ttu-id="fd835-102">Exemple de point de terminaison de gestion de workflow</span><span class="sxs-lookup"><span data-stu-id="fd835-102">Workflow Management Endpoint Sample</span></span>
<span data-ttu-id="fd835-103">Cet exemple montre comment un point de terminaison de contrôle de workflow peut être utilisé pour créer et exécuter des workflows à la fois localement et à distance.</span><span class="sxs-lookup"><span data-stu-id="fd835-103">This sample shows how a workflow control endpoint can be used to create and run workflows both locally and remotely.</span></span> <span data-ttu-id="fd835-104">Il montre comment héberger un point de terminaison de contrôle et écrire des clients qui appellent le point de terminaison de contrôle pour créer et exécuter l'instance d'un workflow.</span><span class="sxs-lookup"><span data-stu-id="fd835-104">The sample demonstrates how to host a control endpoint and write clients that call the control endpoint to create and run the instance of a workflow.</span></span> <span data-ttu-id="fd835-105">Le workflow n'est pas un service.</span><span class="sxs-lookup"><span data-stu-id="fd835-105">The workflow is not a service.</span></span>  
  
 <span data-ttu-id="fd835-106">Du côté service de l'exemple ,un workflow est hébergé avec WorkflowServiceHost et un WorkflowControlEndpoint est ajouté afin que les clients puissent exécuter des opérations de contrôle (Suspendre, Démarrer, etc.).</span><span class="sxs-lookup"><span data-stu-id="fd835-106">On the service side of the sample a workflow is hosted with WorkflowServiceHost and a WorkflowControlEndpoint is added so that clients can perform control operations (Suspend, Start, etc).</span></span> <span data-ttu-id="fd835-107">Un CreationEndpoint défini par l'utilisateur est également ajouté pour permettre la création du workflow.</span><span class="sxs-lookup"><span data-stu-id="fd835-107">A user-defined CreationEndpoint is also added to allow the workflow to be created.</span></span> <span data-ttu-id="fd835-108">Le service utilise ensuite ces points de terminaison pour démarrer le workflow dans un état suspendu, puis pour reprendre le workflow.</span><span class="sxs-lookup"><span data-stu-id="fd835-108">The service then uses these endpoints to start the workflow in a suspended state and then resume the workflow.</span></span> <span data-ttu-id="fd835-109">Le client exécute les mêmes opérations mais à partir du code client.</span><span class="sxs-lookup"><span data-stu-id="fd835-109">The client performs the same operations but from the client code.</span></span> <span data-ttu-id="fd835-110">Pour plus d’informations sur ces interfaces, consultez [point de terminaison de contrôle de flux de travail](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) et [Comment : héberger un workflow sans service dans IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="fd835-110">For more information about these interfaces see, [Workflow Control Endpoint](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) and [How to: Host a non-service workflow in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="fd835-111">Pour exécuter l'exemple</span><span class="sxs-lookup"><span data-stu-id="fd835-111">To run the sample</span></span>  
  
1.  <span data-ttu-id="fd835-112">Exécutez [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="fd835-112">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="fd835-113">Ouvrez la solution ManagementEndpoint.sln dans [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd835-113">Open the ManagementEndpoint.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="fd835-114">Pour générer la solution, appuyez sur CTRL + MAJ + B ou sélectionnez **générer la Solution** à partir de la **Build** menu.</span><span class="sxs-lookup"><span data-stu-id="fd835-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
4.  <span data-ttu-id="fd835-115">Démarrez l'application ManagementEndpoint.exe.</span><span class="sxs-lookup"><span data-stu-id="fd835-115">Start the ManagementEndpoint.exe application.</span></span>  
  
5.  <span data-ttu-id="fd835-116">Démarrez l'application Client.exe.</span><span class="sxs-lookup"><span data-stu-id="fd835-116">Start the Client.exe application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fd835-117">Les exemples peuvent déjà être installés sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fd835-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fd835-118">Recherchez le répertoire (par défaut) suivant avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="fd835-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fd835-119">Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples.</span><span class="sxs-lookup"><span data-stu-id="fd835-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fd835-120">Cet exemple se trouve dans le répertoire suivant.</span><span class="sxs-lookup"><span data-stu-id="fd835-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`
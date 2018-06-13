---
title: Envoi et gestion des erreurs
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 6796b4daccd88adc3bd006f454ce96ca155fbcb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516124"
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="c421b-102">Envoi et gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="c421b-102">Sending and Handling Faults</span></span>
<span data-ttu-id="c421b-103">Cet exemple montre comment utiliser les activités de messagerie <xref:System.ServiceModel.Activities.SendReply> et <xref:System.ServiceModel.Activities.ReceiveReply> pour envoyer et recevoir des erreurs attendues et inattendues.</span><span class="sxs-lookup"><span data-stu-id="c421b-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="c421b-104">Dans ce scénario, la première demande du client génère une erreur attendue qui a été incluse dans sa collection <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>.</span><span class="sxs-lookup"><span data-stu-id="c421b-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="c421b-105">Les demandes suivantes du client entrainent la réception d'erreurs inattendues, avant que la dernière demande réussisse.</span><span class="sxs-lookup"><span data-stu-id="c421b-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="c421b-106">Pour utiliser cet exemple</span><span class="sxs-lookup"><span data-stu-id="c421b-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="c421b-107">Ouvrez [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] avec des autorisations élevées, en cliquant sur le [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icône et en sélectionnant **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="c421b-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c421b-108">Ouvrez le fichier solution Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="c421b-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="c421b-109">Pour générer la solution, appuyez sur Ctrl+Maj+B.</span><span class="sxs-lookup"><span data-stu-id="c421b-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="c421b-110">Exécutez le projet de service.</span><span class="sxs-lookup"><span data-stu-id="c421b-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="c421b-111">Dans **l’Explorateur de solutions**, avec le bouton droit le `FaultService` de projet et sélectionnez **définir comme projet de démarrage**.</span><span class="sxs-lookup"><span data-stu-id="c421b-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="c421b-112">Appuyez sur CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="c421b-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="c421b-113">Ouvrir une autre copie de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] avec des autorisations élevées, en cliquant sur le [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icône et en sélectionnant **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="c421b-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="c421b-114">Ouvrez le fichier solution Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="c421b-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="c421b-115">Exécutez le projet client.</span><span class="sxs-lookup"><span data-stu-id="c421b-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="c421b-116">Dans **l’Explorateur de solutions**, avec le bouton droit le `FaultClient` de projet et sélectionnez **définir comme projet de démarrage**.</span><span class="sxs-lookup"><span data-stu-id="c421b-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="c421b-117">Appuyez sur CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="c421b-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c421b-118">Les exemples peuvent déjà être installés sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c421b-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c421b-119">Recherchez le répertoire (par défaut) suivant avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="c421b-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c421b-120">Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples Windows Workflow Foundation (WF) pour .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples.</span><span class="sxs-lookup"><span data-stu-id="c421b-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c421b-121">Cet exemple se trouve dans le répertoire suivant.</span><span class="sxs-lookup"><span data-stu-id="c421b-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`
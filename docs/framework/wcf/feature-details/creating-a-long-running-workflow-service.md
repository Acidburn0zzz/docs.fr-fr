---
title: Création d'un service de workflow de longue durée
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1cd7cc70c50ac2aa56d8cca55037769aa0b6a64a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2018
---
# <a name="creating-a-long-running-workflow-service"></a><span data-ttu-id="a0b66-102">Création d'un service de workflow de longue durée</span><span class="sxs-lookup"><span data-stu-id="a0b66-102">Creating a Long-running Workflow Service</span></span>
<span data-ttu-id="a0b66-103">Cette rubrique décrit comment créer un service de workflow de longue durée.</span><span class="sxs-lookup"><span data-stu-id="a0b66-103">This topic describes how to create a long-running workflow service.</span></span> <span data-ttu-id="a0b66-104">Les services de workflow de longue durée peuvent s'exécuter sur de longues périodes.</span><span class="sxs-lookup"><span data-stu-id="a0b66-104">Long running workflow services may run for long periods of time.</span></span> <span data-ttu-id="a0b66-105">À un certain stade, le workflow peut devenir inactif en attendant des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="a0b66-105">At some point the workflow may go idle waiting for some additional information.</span></span> <span data-ttu-id="a0b66-106">Lorsque cela se produit, le workflow est rendu persistant dans une base de données SQL et supprimé de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="a0b66-106">When this occurs the workflow is persisted to a SQL database and is removed from memory.</span></span> <span data-ttu-id="a0b66-107">Une fois que les informations supplémentaires sont disponibles, l'instance de workflow est à nouveau chargée dans la mémoire et continue de s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="a0b66-107">When the additional information becomes available the workflow instance is loaded back into memory and continues executing.</span></span>  <span data-ttu-id="a0b66-108">Dans ce scénario, vous implémentez un système de commande très simplifié.</span><span class="sxs-lookup"><span data-stu-id="a0b66-108">In this scenario you are implementing a very simplified ordering system.</span></span>  <span data-ttu-id="a0b66-109">Le client envoie un message initial au service de workflow pour commencer la commande.</span><span class="sxs-lookup"><span data-stu-id="a0b66-109">The client sends an initial message to the workflow service to start the order.</span></span> <span data-ttu-id="a0b66-110">Un ID de commande est retourné au client.</span><span class="sxs-lookup"><span data-stu-id="a0b66-110">It returns an order ID to the client.</span></span> <span data-ttu-id="a0b66-111">À ce stade, le service de workflow attend un autre message du client, passe à l'état inactif et est rendu persistant dans une base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a0b66-111">At this point the workflow service is waiting for another message from the client and goes into the idle state and is persisted to a SQL Server database.</span></span>  <span data-ttu-id="a0b66-112">Lorsque le client envoie le message suivant pour commander un article, le service de workflow est à nouveau chargé dans la mémoire et termine le traitement de la commande.</span><span class="sxs-lookup"><span data-stu-id="a0b66-112">When the client sends the next message to order an item, the workflow service is loaded back into memory and finishes processing the order.</span></span> <span data-ttu-id="a0b66-113">Dans l'exemple de code, il retourne une chaîne indiquant que l'article a été ajouté à la commande.</span><span class="sxs-lookup"><span data-stu-id="a0b66-113">In the code sample it returns a string stating the item has been added to the order.</span></span> <span data-ttu-id="a0b66-114">L'exemple de code n'est pas censé refléter une application réelle de la technologie mais plutôt un exemple simple illustrant des services de workflow de longue durée.</span><span class="sxs-lookup"><span data-stu-id="a0b66-114">The code sample is not meant to be a real world application of the technology, but rather a simple sample that illustrates long running workflow services.</span></span> <span data-ttu-id="a0b66-115">Cette rubrique suppose que vous savez déjà créer des projets et des solutions [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0b66-115">This topic assumes you know how to create [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] projects and solutions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a0b66-116">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a0b66-116">Prerequisites</span></span>  
 <span data-ttu-id="a0b66-117">Les logiciels suivants doivent être installés pour suivre cette procédure pas à pas :</span><span class="sxs-lookup"><span data-stu-id="a0b66-117">You must have the following software installed to use this walkthrough:</span></span>  
  
1.  <span data-ttu-id="a0b66-118">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="a0b66-118">Microsoft SQL Server 2008</span></span>  
  
2.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
3.  <span data-ttu-id="a0b66-119">Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0b66-119">Microsoft  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span></span>  
  
4.  <span data-ttu-id="a0b66-120">Vous êtes familiarisé avec WCF et [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] et vous savez déjà créer des projets et des solutions.</span><span class="sxs-lookup"><span data-stu-id="a0b66-120">You are familiar with WCF and [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and know how to create projects/solutions.</span></span>  
  
### <a name="to-setup-the-sql-database"></a><span data-ttu-id="a0b66-121">Pour configurer la base de données SQL</span><span class="sxs-lookup"><span data-stu-id="a0b66-121">To Setup the SQL Database</span></span>  
  
1.  <span data-ttu-id="a0b66-122">Pour que les instances du service de workflow soient persistantes, Microsoft SQL Server doit être installé et vous devez configurer une base de données pour stocker les instances de workflow persistantes.</span><span class="sxs-lookup"><span data-stu-id="a0b66-122">In order for workflow service instances to be persisted you must have Microsoft SQL Server installed and you must configure a database to store the persisted workflow instances.</span></span> <span data-ttu-id="a0b66-123">Exécutez Microsoft SQL Management Studio en cliquant sur le **Démarrer** bouton, en sélectionnant **tous les programmes**, **Microsoft SQL Server 2008**, et **Microsoft SQL Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="a0b66-123">Run Microsoft SQL Management Studio by clicking the **Start** button, selecting **All Programs**, **Microsoft SQL Server 2008**, and **Microsoft SQL Management Studio**.</span></span>  
  
2.  <span data-ttu-id="a0b66-124">Cliquez sur le **Connect** bouton pour ouvrir une session sur l’instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0b66-124">Click the **Connect** button to log on to the SQL Server instance</span></span>  
  
3.  <span data-ttu-id="a0b66-125">Bouton droit sur **bases de données** dans l’arborescence et sélectionnez **nouvelle base de données...**</span><span class="sxs-lookup"><span data-stu-id="a0b66-125">Right click **Databases** in the tree view and select **New Database..**</span></span> <span data-ttu-id="a0b66-126">Pour créer une nouvelle base de données appelée `SQLPersistenceStore`.</span><span class="sxs-lookup"><span data-stu-id="a0b66-126">to create a new database called `SQLPersistenceStore`.</span></span>  
  
4.  <span data-ttu-id="a0b66-127">Exécutez le fichier de script SqlWorkflowInstanceStoreSchema.sql situé dans le répertoire C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en dans la base de données SQLPersistenceStore pour configurer les schémas de base de données requis.</span><span class="sxs-lookup"><span data-stu-id="a0b66-127">Run the SqlWorkflowInstanceStoreSchema.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database schemas.</span></span>  
  
5.  <span data-ttu-id="a0b66-128">Exécutez le fichier de script SqlWorkflowInstanceStoreLogic.sql situé dans le répertoire C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en dans la base de données SQLPersistenceStore pour configurer la logique de base de données requise.</span><span class="sxs-lookup"><span data-stu-id="a0b66-128">Run the SqlWorkflowInstanceStoreLogic.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database logic.</span></span>  
  
### <a name="to-create-the-web-hosted-workflow-service"></a><span data-ttu-id="a0b66-129">Pour créer le service de workflow hébergé sur le Web</span><span class="sxs-lookup"><span data-stu-id="a0b66-129">To Create the Web Hosted Workflow Service</span></span>  
  
1.  <span data-ttu-id="a0b66-130">Créez une solution [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] vide et nommez-la `OrderProcessing`.</span><span class="sxs-lookup"><span data-stu-id="a0b66-130">Create an empty [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] solution, name it `OrderProcessing`.</span></span>  
  
2.  <span data-ttu-id="a0b66-131">Ajoutez à la solution un nouveau projet d'application de service de workflow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nommé `OrderService`.</span><span class="sxs-lookup"><span data-stu-id="a0b66-131">Add a new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Workflow Service Application project called `OrderService` to the solution.</span></span>  
  
3.  <span data-ttu-id="a0b66-132">Dans la boîte de dialogue Propriétés du projet, sélectionnez le **Web** onglet.</span><span class="sxs-lookup"><span data-stu-id="a0b66-132">In the project properties dialog, select the **Web** tab.</span></span>  
  
    1.  <span data-ttu-id="a0b66-133">Sous **Action de démarrage** sélectionnez **Page spécifique** et spécifiez `Service1.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="a0b66-133">Under **Start Action** select **Specific Page** and specify `Service1.xamlx`.</span></span>  
  
         <span data-ttu-id="a0b66-134">![Propriétés du projet Web Workflow Service](../../../../docs/framework/wcf/feature-details/media/startaction.png "StartAction")</span><span class="sxs-lookup"><span data-stu-id="a0b66-134">![Workflow Service Project Web Properties](../../../../docs/framework/wcf/feature-details/media/startaction.png "StartAction")</span></span>  
  
    2.  <span data-ttu-id="a0b66-135">Sous **serveurs** sélectionnez **serveur Web IIS Local d’utilisation**.</span><span class="sxs-lookup"><span data-stu-id="a0b66-135">Under **Servers** select **Use Local IIS Web server**.</span></span>  
  
         <span data-ttu-id="a0b66-136">![Paramètres du serveur Web local](../../../../docs/framework/wcf/feature-details/media/uselocalwebserver.png "UseLocalWebServer")</span><span class="sxs-lookup"><span data-stu-id="a0b66-136">![Local Web Server Settings](../../../../docs/framework/wcf/feature-details/media/uselocalwebserver.png "UseLocalWebServer")</span></span>  
  
        > [!WARNING]
        >  <span data-ttu-id="a0b66-137">Vous devez exécuter [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] en mode Administrateur pour effectuer ce paramétrage.</span><span class="sxs-lookup"><span data-stu-id="a0b66-137">You must run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] in administrator mode to make this setting.</span></span>  
  
         <span data-ttu-id="a0b66-138">Ces deux étapes configurent le projet du service de workflow pour qu'il soit hébergé par IIS.</span><span class="sxs-lookup"><span data-stu-id="a0b66-138">These two steps configure the workflow service project to be hosted by IIS.</span></span>  
  
4.  <span data-ttu-id="a0b66-139">Ouvrez `Service1.xamlx` si elle n’est pas déjà ouvert et supprimez les **ReceiveRequest** et **SendResponse** activités.</span><span class="sxs-lookup"><span data-stu-id="a0b66-139">Open `Service1.xamlx` if it is not open already and delete the existing **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
5.  <span data-ttu-id="a0b66-140">Sélectionnez le **Service séquentiel** activité et cliquez sur le **Variables** lier et ajoutez les variables affichées dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-140">Select the **Sequential Service** activity and click the **Variables** link and add the variables shown in the following illustration.</span></span> <span data-ttu-id="a0b66-141">Cette action permet d'ajouter des variables qui seront utilisées ultérieurement dans le service de workflow.</span><span class="sxs-lookup"><span data-stu-id="a0b66-141">Doing this adds some variables that will be used later on in the workflow service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0b66-142">Si CorrelationHandle ne figure pas dans la liste déroulante Type de Variable, sélectionnez **rechercher des types** à partir de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-142">If CorrelationHandle is not in the Variable Type drop-down, select **Browse for types** from the drop-down.</span></span> <span data-ttu-id="a0b66-143">Tapez CorrelationHandle dans la **nom de Type** zone, sélectionnez CorrelationHandle dans la zone de liste et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0b66-143">Type CorrelationHandle in the **Type name** box, select CorrelationHandle from the listbox and click **OK**.</span></span>  
  
     <span data-ttu-id="a0b66-144">![Ajouter des Variables](../../../../docs/framework/wcf/feature-details/media/addvariables.gif "AddVariables")</span><span class="sxs-lookup"><span data-stu-id="a0b66-144">![Add Variables](../../../../docs/framework/wcf/feature-details/media/addvariables.gif "AddVariables")</span></span>  
  
6.  <span data-ttu-id="a0b66-145">Faites glisser et déposez un **ReceiveAndSendReply** modèle d’activité dans le **Service séquentiel** activité.</span><span class="sxs-lookup"><span data-stu-id="a0b66-145">Drag and drop a **ReceiveAndSendReply** activity template into the **Sequential Service** activity.</span></span> <span data-ttu-id="a0b66-146">Cet ensemble d'activités recevra un message d'un client et enverra une réponse en retour.</span><span class="sxs-lookup"><span data-stu-id="a0b66-146">This set of activities will receive a message from a client and send a reply back.</span></span>  
  
    1.  <span data-ttu-id="a0b66-147">Sélectionnez le **réception** activité et le jeu de propriétés des mise en surbrillance dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-147">Select the **Receive** activity and set the properties highlighted in the following illustration.</span></span>  
  
         <span data-ttu-id="a0b66-148">![Jeu de propriétés de l’activité de réception](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties.png "SetReceiveProperties")</span><span class="sxs-lookup"><span data-stu-id="a0b66-148">![Set Receive Activity Properties](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties.png "SetReceiveProperties")</span></span>  
  
         <span data-ttu-id="a0b66-149">La propriété DisplayName définit le nom affiché pour l'activité Receive dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="a0b66-149">The DisplayName property sets the name displayed for the Receive activity in the designer.</span></span> <span data-ttu-id="a0b66-150">Les propriétés ServiceContractName et OperationName spécifient le nom du contrat de service et de l'opération implémentés par l'activité Receive.</span><span class="sxs-lookup"><span data-stu-id="a0b66-150">The ServiceContractName and OperationName properties specify the name of the service contract and operation that are implemented by the Receive activity.</span></span> <span data-ttu-id="a0b66-151">Pour plus d’informations sur l’utilisation des contrats dans les services de flux de travail, consultez [à l’aide de contrats dans le Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="a0b66-151">For more information about how contracts are used in Workflow services see [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  
  
    2.  <span data-ttu-id="a0b66-152">Cliquez sur le **définir...**  lien dans le **ReceiveStartOrder** activité et définissez les propriétés affichées dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-152">Click the **Define...** link in the **ReceiveStartOrder** activity and set the properties shown in the following illustration.</span></span>  <span data-ttu-id="a0b66-153">Notez que la **paramètres** case d’option est sélectionnée, un paramètre nommé `p_customerName` est lié à la `customerName` variable.</span><span class="sxs-lookup"><span data-stu-id="a0b66-153">Notice that the **Parameters** radio button is selected, a parameter named `p_customerName` is bound to the `customerName` variable.</span></span> <span data-ttu-id="a0b66-154">Cela configure le **réception** activité qui permet de recevoir des données et de lier ces données aux variables locales.</span><span class="sxs-lookup"><span data-stu-id="a0b66-154">This configures the **Receive** activity to receive some data and bind that data to local variables.</span></span>  
  
         <span data-ttu-id="a0b66-155">![Définition des données reçues par l’activité de réception](../../../../docs/framework/wcf/feature-details/media/setreceivecontent.png "SetReceiveContent")</span><span class="sxs-lookup"><span data-stu-id="a0b66-155">![Setting the data received by the Receive activity](../../../../docs/framework/wcf/feature-details/media/setreceivecontent.png "SetReceiveContent")</span></span>  
  
    3.  <span data-ttu-id="a0b66-156">Sélectionnez le **SendReplyToReceive** activité et définissez la propriété en surbrillance indiquée dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-156">Select The **SendReplyToReceive** activity and set the highlighted property shown in the following illustration.</span></span>  
  
         <span data-ttu-id="a0b66-157">![Définition des propriétés de l’activité SendReply](../../../../docs/framework/wcf/feature-details/media/setreplyproperties.png "SetReplyProperties")</span><span class="sxs-lookup"><span data-stu-id="a0b66-157">![Setting the properties of the SendReply activity](../../../../docs/framework/wcf/feature-details/media/setreplyproperties.png "SetReplyProperties")</span></span>  
  
    4.  <span data-ttu-id="a0b66-158">Cliquez sur le **définir...**  lien dans le **SendReplyToStartOrder** activité et définissez les propriétés affichées dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-158">Click the **Define...** link in the **SendReplyToStartOrder** activity and set the properties shown in the following illustration.</span></span> <span data-ttu-id="a0b66-159">Notez que la **paramètres** case d’option est sélectionnée ; un paramètre nommé `p_orderId` est lié à la `orderId` variable.</span><span class="sxs-lookup"><span data-stu-id="a0b66-159">Notice that the **Parameters** radio button is selected; a parameter named `p_orderId` is bound to the `orderId` variable.</span></span> <span data-ttu-id="a0b66-160">Ce paramètre spécifie que l'activité SendReplyToStartOrder retournera une valeur de type String à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="a0b66-160">This setting specifies that the SendReplyToStartOrder activity will return a value of type string to the caller.</span></span>  
  
         <span data-ttu-id="a0b66-161">![Configuration des données de contenu de l’activité SendReply](../../../../docs/framework/wcf/feature-details/media/setreplycontent.png "SetReplyContent")</span><span class="sxs-lookup"><span data-stu-id="a0b66-161">![Configuring the SendReply activity content data](../../../../docs/framework/wcf/feature-details/media/setreplycontent.png "SetReplyContent")</span></span>  
  
    5.  <span data-ttu-id="a0b66-162">Faites glisser et déposez une activité Assign entre les **réception** et **SendReply** activités et définissez les propriétés comme indiqué dans l’illustration suivante :</span><span class="sxs-lookup"><span data-stu-id="a0b66-162">Drag and drop an Assign activity in between the **Receive** and **SendReply** activities and set the properties as shown in the following illustration:</span></span>  
  
         <span data-ttu-id="a0b66-163">![Ajout d’une activité assign](../../../../docs/framework/wcf/feature-details/media/addassign.png "AddAssign")</span><span class="sxs-lookup"><span data-stu-id="a0b66-163">![Adding an assign activity](../../../../docs/framework/wcf/feature-details/media/addassign.png "AddAssign")</span></span>  
  
         <span data-ttu-id="a0b66-164">Cette action permet de créer un nouvel ID de commande et de placer la valeur dans la variable orderId.</span><span class="sxs-lookup"><span data-stu-id="a0b66-164">This creates a new order ID and places the value in the orderId variable.</span></span>  
  
    6.  <span data-ttu-id="a0b66-165">Sélectionnez le **ReplyToStartOrder** activité.</span><span class="sxs-lookup"><span data-stu-id="a0b66-165">Select the **ReplyToStartOrder** activity.</span></span> <span data-ttu-id="a0b66-166">Dans la fenêtre Propriétés, cliquez sur le bouton de sélection **CorrelationInitializers**.</span><span class="sxs-lookup"><span data-stu-id="a0b66-166">In the properties window click the ellipsis button for **CorrelationInitializers**.</span></span> <span data-ttu-id="a0b66-167">Sélectionnez le **ajouter initialiseur** lier, entrez `orderIdHandle` dans la zone de texte initialiseur, sélectionnez l’initialiseur de corrélation de requête pour le type de corrélation et sélectionnez p_orderId sous la zone de liste déroulante des requêtes XPATH.</span><span class="sxs-lookup"><span data-stu-id="a0b66-167">Select the **Add initializer** link, enter `orderIdHandle` in the Initializer text box, select Query correlation initializer for the Correlation type, and select p_orderId under the XPATH Queries dropdown box.</span></span> <span data-ttu-id="a0b66-168">Ces paramètres sont indiqués dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-168">These settings are shown in the following illustration.</span></span> <span data-ttu-id="a0b66-169">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0b66-169">Click **OK**.</span></span>  <span data-ttu-id="a0b66-170">Cette action permet d'initialiser une corrélation entre le client et cette instance du service de workflow.</span><span class="sxs-lookup"><span data-stu-id="a0b66-170">This initializes a correlation between the client and this instance of the workflow service.</span></span> <span data-ttu-id="a0b66-171">Lorsqu'un message contenant cet ID de commande est reçu, il est routé vers cette instance du service de workflow.</span><span class="sxs-lookup"><span data-stu-id="a0b66-171">When a message containing this order ID is received it is routed to this instance of the workflow service.</span></span>  
  
         <span data-ttu-id="a0b66-172">![Ajout d’un initialiseur de corrélation](../../../../docs/framework/wcf/feature-details/media/addcorrelationinitializers.png "AddCorrelationInitializers")</span><span class="sxs-lookup"><span data-stu-id="a0b66-172">![Adding a correlation initializer](../../../../docs/framework/wcf/feature-details/media/addcorrelationinitializers.png "AddCorrelationInitializers")</span></span>  
  
7.  <span data-ttu-id="a0b66-173">Faites glisser une autre **ReceiveAndSendReply** activité à la fin du flux de travail (en dehors de la **séquence** contenant les premières **réception** et  **SendReply** activités).</span><span class="sxs-lookup"><span data-stu-id="a0b66-173">Drag and drop another **ReceiveAndSendReply** activity to the end of the workflow (outside the **Sequence** containing the first **Receive** and **SendReply** activities).</span></span> <span data-ttu-id="a0b66-174">Le second message envoyé par le client sera alors reçu et une réponse sera renvoyée.</span><span class="sxs-lookup"><span data-stu-id="a0b66-174">This will receive the second message sent by the client and respond to it.</span></span>  
  
    1.  <span data-ttu-id="a0b66-175">Sélectionnez le **séquence** contenant récemment ajouté **réception** et **SendReply** activités et cliquez sur le **Variables** bouton.</span><span class="sxs-lookup"><span data-stu-id="a0b66-175">Select the **Sequence** that contains the newly added **Receive** and **SendReply** activities and click the **Variables** button.</span></span> <span data-ttu-id="a0b66-176">Ajoutez la variable mise en surbrillance dans l'illustration suivante :</span><span class="sxs-lookup"><span data-stu-id="a0b66-176">Add the variable highlighted in the following illustration:</span></span>  
  
         <span data-ttu-id="a0b66-177">![Ajout de nouvelles variables](../../../../docs/framework/wcf/feature-details/media/addorderitemidvariable.png "AddOrderItemIdVariable")</span><span class="sxs-lookup"><span data-stu-id="a0b66-177">![Adding new variables](../../../../docs/framework/wcf/feature-details/media/addorderitemidvariable.png "AddOrderItemIdVariable")</span></span>  
  
    2.  <span data-ttu-id="a0b66-178">Sélectionnez le **réception** activité et définissez les propriétés affichées dans l’illustration suivante :</span><span class="sxs-lookup"><span data-stu-id="a0b66-178">Select the **Receive** activity and set the properties shown in the following illustration:</span></span>  
  
         <span data-ttu-id="a0b66-179">![Définir les propriétés d’une activité de réception](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties2.png "SetReceiveProperties2")</span><span class="sxs-lookup"><span data-stu-id="a0b66-179">![Set the Receive acitivity properties](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties2.png "SetReceiveProperties2")</span></span>  
  
    3.  <span data-ttu-id="a0b66-180">Cliquez sur le **définir...**  lien dans le **ReceiveAddItem** activité et ajoutez les paramètres indiqués dans l’illustration suivante : Cela configure l’activité de réception pour accepter deux paramètres, l’ID de commande et l’ID de l’article commandé.</span><span class="sxs-lookup"><span data-stu-id="a0b66-180">Click the **Define...** link in the **ReceiveAddItem** activity and add the parameters shown in the following illustration:This configures the receive activity to accept two parameters, the order ID and the ID of the item being ordered.</span></span>  
  
         <span data-ttu-id="a0b66-181">![En spécifiant les paramètres pour la deuxième reçoivent](../../../../docs/framework/wcf/feature-details/media/addreceive2parameters.png "AddReceive2Parameters")</span><span class="sxs-lookup"><span data-stu-id="a0b66-181">![Specifying parameters for the second receive](../../../../docs/framework/wcf/feature-details/media/addreceive2parameters.png "AddReceive2Parameters")</span></span>  
  
    4.  <span data-ttu-id="a0b66-182">Cliquez sur le **CorrelateOn** points de suspension bouton et entrez `orderIdHandle`.</span><span class="sxs-lookup"><span data-stu-id="a0b66-182">Click the **CorrelateOn** ellipsis button and enter `orderIdHandle`.</span></span> <span data-ttu-id="a0b66-183">Sous **requêtes XPath**, cliquez sur la flèche déroulante et sélectionnez `p_orderId`.</span><span class="sxs-lookup"><span data-stu-id="a0b66-183">Under **XPath Queries**, click the drop down arrow and select `p_orderId`.</span></span> <span data-ttu-id="a0b66-184">Cela permet de configurer la corrélation sur la deuxième activité Receive.</span><span class="sxs-lookup"><span data-stu-id="a0b66-184">This configures the correlation on the second receive activity.</span></span> <span data-ttu-id="a0b66-185">Pour plus d’informations sur la corrélation, consultez [corrélation](../../../../docs/framework/wcf/feature-details/correlation.md).</span><span class="sxs-lookup"><span data-stu-id="a0b66-185">For more information about correlation see [Correlation](../../../../docs/framework/wcf/feature-details/correlation.md).</span></span>  
  
         <span data-ttu-id="a0b66-186">![Définition de la propriété CorrelatesOn](../../../../docs/framework/wcf/feature-details/media/correlateson.png "CorrelatesOn")</span><span class="sxs-lookup"><span data-stu-id="a0b66-186">![Setting the CorrelatesOn property](../../../../docs/framework/wcf/feature-details/media/correlateson.png "CorrelatesOn")</span></span>  
  
    5.  <span data-ttu-id="a0b66-187">Faites glisser et déposez une **si** activité immédiatement après le **ReceiveAddItem** activité.</span><span class="sxs-lookup"><span data-stu-id="a0b66-187">Drag and drop an **If** activity immediately after the **ReceiveAddItem** activity.</span></span> <span data-ttu-id="a0b66-188">Cette activité agit de la même façon qu'une instruction if.</span><span class="sxs-lookup"><span data-stu-id="a0b66-188">This activity acts just like an if statement.</span></span>  
  
        1.  <span data-ttu-id="a0b66-189">Définir le **Condition** propriété `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span><span class="sxs-lookup"><span data-stu-id="a0b66-189">Set the **Condition** property to `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span></span>  
  
        2.  <span data-ttu-id="a0b66-190">Glisser- déposer un **affecter** activité dans le **puis** section et une autre dans le **Else** section définie les propriétés de la **affecter** activités, comme indiqué dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-190">Drag and drop an **Assign** activity in to the **Then** section and another into the **Else** section set the properties of the **Assign** activities as shown in the following illustration.</span></span>  
  
             <span data-ttu-id="a0b66-191">![Assignation du résultat de l’appel de service](../../../../docs/framework/wcf/feature-details/media/resultassign.png "ResultAssign")</span><span class="sxs-lookup"><span data-stu-id="a0b66-191">![Assigning the result of the service call](../../../../docs/framework/wcf/feature-details/media/resultassign.png "ResultAssign")</span></span>  
  
             <span data-ttu-id="a0b66-192">Si la condition est `true` le **puis** section sera exécutée.</span><span class="sxs-lookup"><span data-stu-id="a0b66-192">If the condition is `true` the **Then** section will be executed.</span></span> <span data-ttu-id="a0b66-193">Si la condition est `false` le **Else** section est exécutée.</span><span class="sxs-lookup"><span data-stu-id="a0b66-193">If the condition is `false` the **Else** section is executed.</span></span>  
  
        3.  <span data-ttu-id="a0b66-194">Sélectionnez le **SendReplyToReceive** activité et définissez la **DisplayName** propriété indiquée dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-194">Select the **SendReplyToReceive** activity and set the **DisplayName** property shown in the following illustration.</span></span>  
  
             <span data-ttu-id="a0b66-195">![Définition des propriétés de l’activité SendReply](../../../../docs/framework/wcf/feature-details/media/setreply2properties.png "SetReply2Properties")</span><span class="sxs-lookup"><span data-stu-id="a0b66-195">![Setting the SendReply activity properties](../../../../docs/framework/wcf/feature-details/media/setreply2properties.png "SetReply2Properties")</span></span>  
  
        4.  <span data-ttu-id="a0b66-196">Cliquez sur le **définir...**  lien dans le **SetReplyToAddItem** activité et le configurer comme indiqué dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="a0b66-196">Click the **Define ...** link in the **SetReplyToAddItem** activity and configure it as shown in the following illustration.</span></span> <span data-ttu-id="a0b66-197">Cela configure le **SendReplyToAddItem** activité qui permet de retourner la valeur dans la `orderResult` variable.</span><span class="sxs-lookup"><span data-stu-id="a0b66-197">This configures the **SendReplyToAddItem** activity to return the value in the `orderResult` variable.</span></span>  
  
             <span data-ttu-id="a0b66-198">![Définition de la liaison de données pour l’activité SendReply](../../../../docs/framework/wcf/feature-details/media/replytoadditemcontent.gif "ReplyToAddItemContent")</span><span class="sxs-lookup"><span data-stu-id="a0b66-198">![Setting the data binding for the SendReply activit](../../../../docs/framework/wcf/feature-details/media/replytoadditemcontent.gif "ReplyToAddItemContent")</span></span>  
  
8.  <span data-ttu-id="a0b66-199">Ouvrez le fichier web.config et ajoutez les éléments suivants dans le \<comportement > section pour activer la persistance de workflow.</span><span class="sxs-lookup"><span data-stu-id="a0b66-199">Open the web.config file and add the following elements in the \<behavior> section to enable workflow persistence.</span></span>  
  
    ```xml  
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />  
              <workflowIdle timeToUnload="0"/>  
    ```  
  
    > [!WARNING]
    >  <span data-ttu-id="a0b66-200">Assurez-vous de remplacer le nom de l'hôte et de l'instance SQL Server dans l'extrait de code précédent.</span><span class="sxs-lookup"><span data-stu-id="a0b66-200">Make sure to replace your host and SQL server instance name in the previous code snippet.</span></span>  
  
9. <span data-ttu-id="a0b66-201">Générez la solution.</span><span class="sxs-lookup"><span data-stu-id="a0b66-201">Build the solution.</span></span>  
  
### <a name="to-create-a-client-application-to-call-the-workflow-service"></a><span data-ttu-id="a0b66-202">Pour créer une application cliente pour appeler le service de workflow</span><span class="sxs-lookup"><span data-stu-id="a0b66-202">To Create a Client Application to Call the Workflow Service</span></span>  
  
1.  <span data-ttu-id="a0b66-203">Ajoutez à la solution un nouveau projet d'application console nommé `OrderClient`.</span><span class="sxs-lookup"><span data-stu-id="a0b66-203">Add a new Console application project called `OrderClient` to the solution.</span></span>  
  
2.  <span data-ttu-id="a0b66-204">Ajoutez les références aux assemblys suivantes au projet `OrderClient` :</span><span class="sxs-lookup"><span data-stu-id="a0b66-204">Add references to the following assemblies to the `OrderClient` project</span></span>  
  
    1.  <span data-ttu-id="a0b66-205">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="a0b66-205">System.ServiceModel.dll</span></span>  
  
    2.  <span data-ttu-id="a0b66-206">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="a0b66-206">System.ServiceModel.Activities.dll</span></span>  
  
3.  <span data-ttu-id="a0b66-207">Ajoutez une référence de service au service de workflow et spécifiez `OrderService` comme espace de noms.</span><span class="sxs-lookup"><span data-stu-id="a0b66-207">Add a service reference to the workflow service and specify `OrderService` as the namespace.</span></span>  
  
4.  <span data-ttu-id="a0b66-208">Dans la méthode `Main()` du projet client, ajoutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="a0b66-208">In the `Main()` method of the client project add the following code:</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
       // Send initial message to start the workflow service  
       Console.WriteLine("Sending start message");  
       StartOrderClient startProxy = new StartOrderClient();  
       string orderId = startProxy.StartOrder("Kim Abercrombie");  
  
       // The workflow service is now waiting for the second message to be sent  
       Console.WriteLine("Workflow service is idle...");  
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");  
       Console.ReadLine();  
  
       // Send the second message  
       Console.WriteLine("Sending add item message");  
       AddItemClient addProxy = new AddItemClient();  
       AddItem item = new AddItem();  
       item.p_itemId = "Zune HD";  
       item.p_orderId = orderId;  
  
       string orderResult = addProxy.AddItem(item);  
       Console.WriteLine("Service returned: " + orderResult);  
    }  
    ```  
  
5.  <span data-ttu-id="a0b66-209">Générez la solution et exécutez l'application `OrderClient`.</span><span class="sxs-lookup"><span data-stu-id="a0b66-209">Build the solution and run the `OrderClient` application.</span></span> <span data-ttu-id="a0b66-210">Le client affiche le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="a0b66-210">The client will display the following text:</span></span>  
  
    ```Output  
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...  
    ```  
  
6.  <span data-ttu-id="a0b66-211">Pour vérifier que le service de workflow a été rendue persistante, démarrez SQL Server Management Studio en accédant à la **Démarrer** menu, si vous sélectionnez **tous les programmes**, **deMicrosoftSQLServer2008**, **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="a0b66-211">To verify that the workflow service has been persisted, start the SQL Server Management Studio by going to the **Start** menu, Selecting **All Programs**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.</span></span>  
  
    1.  <span data-ttu-id="a0b66-212">Dans le volet gauche, développez **bases de données**, **SQLPersistenceStore**, **vues** avec le bouton droit sur **System.Activities.DurableInstancing.Instances**  et sélectionnez **sélectionnez 1000 lignes du haut**.</span><span class="sxs-lookup"><span data-stu-id="a0b66-212">In the left hand pane expand, **Databases**, **SQLPersistenceStore**, **Views** and right click **System.Activities.DurableInstancing.Instances** and select **Select Top 1000 Rows**.</span></span> <span data-ttu-id="a0b66-213">Dans le **résultats** volet Vérifiez au moins une instance est listée.</span><span class="sxs-lookup"><span data-stu-id="a0b66-213">In the **Results** pane verify you see at least one instance listed.</span></span> <span data-ttu-id="a0b66-214">D'autres instances d'exécutions précédentes peuvent également être présentes si une exception s'est produite pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="a0b66-214">There may be other instances from prior runs if an exception occurred while running.</span></span> <span data-ttu-id="a0b66-215">Vous pouvez supprimer des lignes existantes en cliquant **System.Activities.DurableInstancing.Instances** et en sélectionnant **modifier les 200 lignes du haut**, en cliquant sur le **Execute** bouton, sélectionner toutes les lignes dans le volet de résultats et **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a0b66-215">You can delete existing rows by right clicking **System.Activities.DurableInstancing.Instances** and selecting **Edit Top 200 rows**, pressing the **Execute** button, selecting all rows in the results pane and selecting **delete**.</span></span>  <span data-ttu-id="a0b66-216">Pour vous assurer que l'instance affichée dans la base de données est bien l'instance créée par votre application, vérifiez que la vue Instances est vide avant d'exécuter le client.</span><span class="sxs-lookup"><span data-stu-id="a0b66-216">To verify the instance displayed in the database is the instance your application created, verify the instances view is empty prior to running the client.</span></span> <span data-ttu-id="a0b66-217">Une fois que le client est en cours d'exécution, réexécutez la requête (Sélectionner les 1000 lignes du haut) et assurez-vous qu'une nouvelle instance a été ajoutée.</span><span class="sxs-lookup"><span data-stu-id="a0b66-217">Once the client is running re-run the query (Select Top 1000 Rows) and verify a new instance has been added.</span></span>  
  
7.  <span data-ttu-id="a0b66-218">Appuyez sur Entrée pour envoyer le message d'ajout d'élément au service de workflow.</span><span class="sxs-lookup"><span data-stu-id="a0b66-218">Press enter to send the add item message to the workflow service.</span></span> <span data-ttu-id="a0b66-219">Le client affiche le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="a0b66-219">The client will display the following text:</span></span>  
  
    ```Output  
    Sending add item messageService returned: Item added to orderPress any key to continue . . .  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a0b66-220">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0b66-220">See Also</span></span>  
 [<span data-ttu-id="a0b66-221">Services de workflow</span><span class="sxs-lookup"><span data-stu-id="a0b66-221">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)

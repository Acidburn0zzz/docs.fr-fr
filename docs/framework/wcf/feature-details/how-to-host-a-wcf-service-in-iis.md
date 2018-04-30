---
title: 'Comment : héberger un service WCF dans IIS'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4699475db18ac84c4379c7bc102d93648060ed3d
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="9eb44-102">Comment : héberger un service WCF dans IIS</span><span class="sxs-lookup"><span data-stu-id="9eb44-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="9eb44-103">Cette rubrique décrit les étapes de base requises pour créer un service [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] hébergé dans les services IIS (Internet Information Services).</span><span class="sxs-lookup"><span data-stu-id="9eb44-103">This topic outlines the basic steps required to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="9eb44-104">Dans cette rubrique, on suppose que vous connaissez IIS et que vous comprenez la manière d'utiliser l'outil d'administration IIS pour créer et gérer des applications IIS.</span><span class="sxs-lookup"><span data-stu-id="9eb44-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="9eb44-105">Pour plus d’informations sur IIS, consultez [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span><span class="sxs-lookup"><span data-stu-id="9eb44-105">For more information about IIS see [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="9eb44-106">Un service [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] exécuté dans l'environnement IIS tire totalement parti des fonctionnalités IIS telles que le recyclage de processus, l'arrêt en cas d'inactivité, le contrôle d'état de processus et l'activation basée sur message.</span><span class="sxs-lookup"><span data-stu-id="9eb44-106">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="9eb44-107">Cette option d'hébergement requiert que les services IIS soient configurés correctement, mais n'exige pas l'écriture d'un code d'hébergement dans le cadre de l'application.</span><span class="sxs-lookup"><span data-stu-id="9eb44-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="9eb44-108">Vous pouvez utiliser l'hébergement IIS uniquement avec un transport HTTP.</span><span class="sxs-lookup"><span data-stu-id="9eb44-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="9eb44-109">Pour plus d’informations sur la façon [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] et [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interagir, consultez [Services WCF et ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="9eb44-109">For more information about how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="9eb44-110">Pour plus d’informations sur la configuration de la sécurité, consultez [sécurité](../../../../docs/framework/wcf/feature-details/security.md).</span><span class="sxs-lookup"><span data-stu-id="9eb44-110">For more information about configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="9eb44-111">Pour la copie de la source de cet exemple, consultez [d’hébergement à l’aide en ligne de Code IIS](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="9eb44-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="9eb44-112">Pour créer un service hébergé par IIS</span><span class="sxs-lookup"><span data-stu-id="9eb44-112">To create a service hosted by IIS</span></span>  
  
1.  <span data-ttu-id="9eb44-113">Vérifiez que les services IIS sont installés et s'exécutent sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9eb44-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="9eb44-114">Pour plus d’informations sur l’installation et configuration d’IIS, consultez [installation et configuration d’IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="9eb44-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2.  <span data-ttu-id="9eb44-115">Créez un dossier pour vos fichiers d'application, appelé « IISHostedCalcService », assurez-vous que [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] a accès au contenu du dossier et utilisez l'outil d'administration IIS pour créer une application IIS située physiquement dans ce répertoire d'application.</span><span class="sxs-lookup"><span data-stu-id="9eb44-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="9eb44-116">Lors de la création d'un alias pour le répertoire de l'application, utilisez « IISHostedCalc ».</span><span class="sxs-lookup"><span data-stu-id="9eb44-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3.  <span data-ttu-id="9eb44-117">Créez un fichier appelé « service.svc » dans le répertoire de l'application.</span><span class="sxs-lookup"><span data-stu-id="9eb44-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="9eb44-118">Modifiez ce fichier en ajoutant le code suivant @ServiceHost élément.</span><span class="sxs-lookup"><span data-stu-id="9eb44-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  <span data-ttu-id="9eb44-119">Créez un sous-répertoire App_Code dans le répertoire de l'application.</span><span class="sxs-lookup"><span data-stu-id="9eb44-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5.  <span data-ttu-id="9eb44-120">Créez un fichier de code nommé Service.cs dans le sous-répertoire App_Code.</span><span class="sxs-lookup"><span data-stu-id="9eb44-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6.  <span data-ttu-id="9eb44-121">Ajoutez les instructions using suivantes en tête du fichier Service.cs.</span><span class="sxs-lookup"><span data-stu-id="9eb44-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  <span data-ttu-id="9eb44-122">Ajoutez la déclaration d'espace de noms suivante à la suite des instructions using.</span><span class="sxs-lookup"><span data-stu-id="9eb44-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  <span data-ttu-id="9eb44-123">Définissez le contrat de service à l'intérieur de la déclaration d'espace de noms, tel qu'indiqué dans le code suivant.</span><span class="sxs-lookup"><span data-stu-id="9eb44-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="9eb44-124">Implémentez le contrat de service après la définition du contrat de service, tel qu'indiqué dans le code suivant.</span><span class="sxs-lookup"><span data-stu-id="9eb44-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="9eb44-125">Créez un fichier nommé « Web.config » dans le répertoire de l'application et ajoutez le code de configuration suivant dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="9eb44-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="9eb44-126">Au moment de l'exécution, l'infrastructure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilise les informations pour construire un point de terminaison avec lequel les applications clientes peuvent communiquer.</span><span class="sxs-lookup"><span data-stu-id="9eb44-126">At runtime, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="9eb44-127">L'exemple spécifie explicitement les points de terminaison dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="9eb44-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="9eb44-128">Si vous n'ajoutez pas de points de terminaison au service, le runtime ajoute les points de terminaison par défaut.</span><span class="sxs-lookup"><span data-stu-id="9eb44-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="9eb44-129">Pour plus d’informations sur les points de terminaison par défaut, les liaisons et comportements voir [Configuration simplifiée](../../../../docs/framework/wcf/simplified-configuration.md) et [simplifié la Configuration des Services WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9eb44-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="9eb44-130">Pour vous assurer que le service est hébergé correctement, ouvrez une instance d'Internet Explorer et naviguez jusqu'à l'URL du service : `http://localhost/IISHostedCalc/Service.svc`</span><span class="sxs-lookup"><span data-stu-id="9eb44-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eb44-131">Exemple</span><span class="sxs-lookup"><span data-stu-id="9eb44-131">Example</span></span>  
 <span data-ttu-id="9eb44-132">L'intégralité du code pour le service de calculatrice hébergé IIS est présentée ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9eb44-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="9eb44-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9eb44-133">See Also</span></span>  
 [<span data-ttu-id="9eb44-134">Hébergement dans les services IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="9eb44-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="9eb44-135">Hébergement de services</span><span class="sxs-lookup"><span data-stu-id="9eb44-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="9eb44-136">Services WCF et ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9eb44-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [<span data-ttu-id="9eb44-137">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9eb44-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
 [<span data-ttu-id="9eb44-138">Fonctionnalités d’hébergement de Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="9eb44-138">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)

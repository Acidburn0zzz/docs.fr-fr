---
title: Comment déployer des applications .NET existantes vers Azure App Service
description: Architecture de Microservices .NET pour les Applications .NET en conteneur | Comment déployer des applications .NET existantes vers Azure App Service
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 74f4d4b1812976d2e2b1581e10134fa57938bffc
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a><span data-ttu-id="6231f-103">Comment déployer des applications .NET existantes vers Azure App Service</span><span class="sxs-lookup"><span data-stu-id="6231f-103">How to deploy existing .NET apps to Azure App Service</span></span> 

<span data-ttu-id="6231f-104">La fonctionnalité d’applications Web du Service d’application Azure est une plateforme de calcul entièrement géré qui est optimisée pour l’hébergement d’applications web et sites Web.</span><span class="sxs-lookup"><span data-stu-id="6231f-104">The Web Apps feature of Azure App Service is a fully managed compute platform that is optimized for hosting websites and web apps.</span></span> <span data-ttu-id="6231f-105">Cette offre PaaS dans Microsoft Azure vous permet de vous concentrer sur votre logique métier, tandis que Azure prend en charge l’infrastructure pour exécuter et de faire évoluer vos applications.</span><span class="sxs-lookup"><span data-stu-id="6231f-105">This PaaS offering in Microsoft Azure lets you focus on your business logic, while Azure takes care of the infrastructure to run and scale your apps.</span></span>

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a><span data-ttu-id="6231f-106">Valider des sites et de migrer vers le Service d’application avec l’Assistant de Migration Azure App Service</span><span class="sxs-lookup"><span data-stu-id="6231f-106">Validate sites and migrate to App Service with Azure App Service Migration Assistant</span></span>

<span data-ttu-id="6231f-107">Lorsque vous créez une nouvelle application dans Visual Studio, généralement déplacement de l’application au Service d’application est simple.</span><span class="sxs-lookup"><span data-stu-id="6231f-107">When you create a new application in Visual Studio, moving the app to App Service usually is straightforward.</span></span> <span data-ttu-id="6231f-108">Toutefois, si vous envisagez de migrer une application existante vers le Service d’applications, vous devez d’abord déterminer si toutes vos dépendances d’application sont compatibles avec le Service d’applications.</span><span class="sxs-lookup"><span data-stu-id="6231f-108">However, if you are planning to migrate an existing application to App Service, first you need to evaluate whether all your application's dependencies are compatible with App Service.</span></span> <span data-ttu-id="6231f-109">Cela inclut les dépendances, telles que le serveur du système d’exploitation et tout logiciel tiers est installé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="6231f-109">This includes dependencies like server OS and any third-party software that's installed on the server.</span></span>

<span data-ttu-id="6231f-110">Vous pouvez utiliser [Assistant de Migration Azure App Service](https://www.migratetoazure.net/) pour analyser des sites et les migrer à partir de serveurs web Windows et Linux pour le Service d’applications.</span><span class="sxs-lookup"><span data-stu-id="6231f-110">You can use [Azure App Service Migration Assistant](https://www.migratetoazure.net/) to analyze sites and then migrate them from Windows and Linux web servers to App Service.</span></span> <span data-ttu-id="6231f-111">Dans le cadre de la migration, l’outil crée des applications web et bases de données sur Azure en fonction des besoins, publie du contenu et publie votre base de données.</span><span class="sxs-lookup"><span data-stu-id="6231f-111">As part of the migration, the tool creates web apps and databases on Azure as needed, publishes content, and publishes your database.</span></span>

<span data-ttu-id="6231f-112">Azure App Service Assistant de Migration prend en charge la migration à partir d’IIS qui s’exécute sur Windows Server pour le cloud.</span><span class="sxs-lookup"><span data-stu-id="6231f-112">Azure App Service Migration Assistant supports migrating from IIS running on Windows Server to the cloud.</span></span> <span data-ttu-id="6231f-113">Service d’applications prend en charge Windows Server 2003 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="6231f-113">App Service supports Windows Server 2003 and later versions.</span></span>

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> <span data-ttu-id="6231f-114">**Figure 4-5.**</span><span class="sxs-lookup"><span data-stu-id="6231f-114">**Figure 4-5.**</span></span> <span data-ttu-id="6231f-115">À l’aide de l’Assistant de Migration du Service d’applications Azure</span><span class="sxs-lookup"><span data-stu-id="6231f-115">Using Azure App Service Migration Assistant</span></span>

<span data-ttu-id="6231f-116">Assistant de Migration App Service est un outil qui se déplace de vos sites Web à partir de vos serveurs web vers le cloud Azure.</span><span class="sxs-lookup"><span data-stu-id="6231f-116">App Service Migration Assistant is a tool that moves your websites from your web servers to the Azure cloud.</span></span>

<span data-ttu-id="6231f-117">Une fois un site Web est migré vers le Service d’applications, le site a tout ce dont il a besoin pour exécuter efficacement et en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="6231f-117">After a website is migrated to App Service, the site has everything it needs to run safely and efficiently.</span></span> <span data-ttu-id="6231f-118">Les sites sont définies et s’exécuter automatiquement dans le service de PaaS Azure cloud (Service d’application).</span><span class="sxs-lookup"><span data-stu-id="6231f-118">Sites are set up and run automatically in the Azure cloud PaaS service (App Service).</span></span>

<span data-ttu-id="6231f-119">L’outil de migration du Service d’applications peut analyser vos sites Web et créer des rapports sur leur compatibilité pour le déplacement vers le Service d’applications.</span><span class="sxs-lookup"><span data-stu-id="6231f-119">The App Service migration tool can analyze your websites and report on their compatibility for moving to App Service.</span></span> <span data-ttu-id="6231f-120">Si vous êtes satisfait de l’analyse, vous pouvez laisser l’Assistant Migration de Service application migrer le contenu, les données et les paramètres pour vous.</span><span class="sxs-lookup"><span data-stu-id="6231f-120">If you're happy with the analysis, you can let App Service Migration Assistant migrate content, data, and settings for you.</span></span> <span data-ttu-id="6231f-121">Si un site n’est pas assez compatible, l’outil de migration vous indique ce que vous deviez ajuster pour qu’il fonctionne.</span><span class="sxs-lookup"><span data-stu-id="6231f-121">If a site is not quite compatible, the migration tool tells you what you need to adjust to make it work.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="6231f-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6231f-122">Additional resources</span></span>

- <span data-ttu-id="6231f-123">**Assistant de Migration du Service d’applications Azure**</span><span class="sxs-lookup"><span data-stu-id="6231f-123">**Azure App Service Migration Assistant**</span></span>

    [https://www.migratetoazure.net/](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
<span data-ttu-id="6231f-124">[Précédent](what-about-cloud-optimized-applications.md)
[Suivant](deploy-existing-net-apps-as-windows-containers.md)</span><span class="sxs-lookup"><span data-stu-id="6231f-124">[Previous](what-about-cloud-optimized-applications.md)
[Next](deploy-existing-net-apps-as-windows-containers.md)</span></span>

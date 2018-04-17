---
title: À l’aide de Visual Studio Tools pour Docker (Visual Studio sous Windows)
description: Cycle de vie des applications Docker en conteneur avec la plateforme et les outils Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cbd4dea32b98e79e85302aa5d4a5c97b1b0fa556
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="00d84-103">À l’aide de Visual Studio Tools pour Docker (Visual Studio sous Windows)</span><span class="sxs-lookup"><span data-stu-id="00d84-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="00d84-104">Le flux de travail de développement lors de l’utilisation de Visual Studio Tools pour Docker est semblable au workflow lors de l’utilisation de Code Visual Studio et Docker CLI (en fait, il est basé sur le même CLI Docker), mais il est plus facile de commencer, simplifie le processus et fournit une plus grande la productivité lors de la build, exécuter et composer des tâches.</span><span class="sxs-lookup"><span data-stu-id="00d84-104">The developer workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI (in fact, it is based on the same Docker CLI), but it is easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="00d84-105">Il est également en mesure d’exécuter et déboguer vos conteneurs via des actions simples comme F5 et Ctrl + F5 dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="00d84-105">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="00d84-106">De plus, avec Visual 2017 Studio, en plus de pouvoir exécuter et déboguer un seul conteneur, vous également pouvez exécuter et déboguer un groupe de conteneurs (une solution dans son intégralité) en même temps si elles sont définies dans le même fichier docker-compose.yml au niveau de la solution.</span><span class="sxs-lookup"><span data-stu-id="00d84-106">Even more, with Visual Studio 2017, in addition to being able to run and debug a single container, you also can run and debug a group of containers (a whole solution) at the same time if they are defined in the same docker-compose.yml file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="00d84-107">Configuration de votre environnement local</span><span class="sxs-lookup"><span data-stu-id="00d84-107">Configuring your local environment</span></span>

<span data-ttu-id="00d84-108">Avec les versions plus récentes de Docker pour Windows, il est plus facile que jamais à développer des applications de Docker, car le programme d’installation est simple, comme expliqué dans les références suivantes.</span><span class="sxs-lookup"><span data-stu-id="00d84-108">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="00d84-109">**Plus d’informations :** pour en savoir plus sur l’installation de Docker pour Windows, accédez à <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="00d84-109">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="00d84-110">Si vous utilisez Visual Studio 2015, vous devez disposer de mise à jour 3 ou une version ultérieure ainsi que Visual Studio Tools pour Docker.</span><span class="sxs-lookup"><span data-stu-id="00d84-110">If you're using Visual Studio 2015, you must have Update 3 or a later version plus the Visual Studio Tools for Docker.</span></span>

<span data-ttu-id="00d84-111">**Plus d’informations :** pour obtenir des instructions sur l’installation de Visual Studio, accédez à [ https://www.visualstudio.com/\ produits/vs-2015-produit-éditions](https://www.visualstudio.com/products/vs-2015-product-editions).</span><span class="sxs-lookup"><span data-stu-id="00d84-111">**More info:** For instructions on installing Visual Studio, go to [https://www.visualstudio.com/\ products/vs-2015-product-editions](https://www.visualstudio.com/products/vs-2015-product-editions).</span></span>

<span data-ttu-id="00d84-112">Pour plus d’informations sur l’installation de Visual Studio Tools pour Docker, accédez à <http://aka.ms/vstoolsfordocker> et <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span><span class="sxs-lookup"><span data-stu-id="00d84-112">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span></span>

<span data-ttu-id="00d84-113">Si vous utilisez Visual Studio 2017, prise en charge Docker est déjà inclus.</span><span class="sxs-lookup"><span data-stu-id="00d84-113">If you're using Visual Studio 2017, Docker support is already included.</span></span>

## <a name="using-docker-tools-in-visual-studio-2015"></a><span data-ttu-id="00d84-114">À l’aide d’outils Docker dans Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="00d84-114">Using Docker Tools in Visual Studio 2015</span></span>

<span data-ttu-id="00d84-115">Visual Studio Tools pour Docker fournit un moyen cohérent de développer et valider localement vos conteneurs Docker pour Linux dans un hôte Linux Docker ou ordinateurs virtuels ou vos conteneurs Windows directement sur Windows.</span><span class="sxs-lookup"><span data-stu-id="00d84-115">The Visual Studio Tools for Docker provides a consistent way to develop and validate locally your Docker containers for Linux in a Linux Docker host or VM, or your Windows Containers directly on Windows.</span></span>

<span data-ttu-id="00d84-116">Si vous utilisez un seul conteneur, la première chose que vous devez commencer consiste à activer la prise en charge Docker dans votre projet .NET Core.</span><span class="sxs-lookup"><span data-stu-id="00d84-116">If you're using a single container, the first thing you need to begin is to turn on Docker support into your .NET Core project.</span></span> <span data-ttu-id="00d84-117">Pour ce faire, cliquez sur votre fichier projet, comme indiqué dans la Figure 4-25.</span><span class="sxs-lookup"><span data-stu-id="00d84-117">To do this, right-click your project file, as shown in Figure 4-25.</span></span>

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

<span data-ttu-id="00d84-118">Figure 4-25 : activation de la prise en charge de Docker pour votre projet Visual Studio</span><span class="sxs-lookup"><span data-stu-id="00d84-118">Figure 4-25: Turning on Docker support for your Visual Studio project</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="00d84-119">À l’aide d’outils Docker dans Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="00d84-119">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="00d84-120">Lorsque vous ajoutez la prise en charge de Docker pour un projet de service dans votre solution (voir Figure 4-26), Visual Studio est ajout pas simplement d’un fichier DockerFile à votre projet, il est également Ajout d’une section de service de votre solution docker-compose.yml fichiers (ou créer les fichiers si elles n’est pas existe).</span><span class="sxs-lookup"><span data-stu-id="00d84-120">When you add Docker support to a service project in your solution (see Figure 4-26), Visual Studio is not just adding a DockerFile file to your project, it also is adding a service section in your solution's docker-compose.yml files (or creating the files if they didn't exist).</span></span> <span data-ttu-id="00d84-121">Il s’agit d’un moyen simple de commencer la composition de votre solution multicontainer ; Vous pouvez ensuite ouvrir les fichiers compose.yml de docker et les mettre à jour avec des fonctionnalités supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="00d84-121">It's an easy way to begin composing your multicontainer solution; you then can open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image32.png)

<span data-ttu-id="00d84-122">Figure 4-26 : activer la prise en charge de la Solution de Docker dans un projet Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="00d84-122">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

<span data-ttu-id="00d84-123">Cette action ajoute non seulement le fichier DockerFile à votre projet, il ajoute également les lignes de la configuration requise de code pour un compose.yml de docker globales définies au niveau de la solution.</span><span class="sxs-lookup"><span data-stu-id="00d84-123">This action not only adds the DockerFile to your project, it also adds the required configuration lines of code to a global docker-compose.yml set at the solution level.</span></span>

<span data-ttu-id="00d84-124">Vous également pourrez activer la prise en charge de Docker lors de la création d’un projet ASP.NET Core dans Visual Studio 2017, comme indiqué dans la Figure 4-27.</span><span class="sxs-lookup"><span data-stu-id="00d84-124">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![](./media/image33.png)

<span data-ttu-id="00d84-125">Figure 4-27 : activation sur la prise en charge Docker lors de la création d’un projet</span><span class="sxs-lookup"><span data-stu-id="00d84-125">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="00d84-126">Après avoir ajouté la prise en charge Docker à votre solution dans Visual Studio, apparaît également une nouvelle arborescence de nœuds dans l’Explorateur de solutions avec les fichiers ajoutés docker-compose.yml, comme illustré dans la Figure 4-28.</span><span class="sxs-lookup"><span data-stu-id="00d84-126">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in Solution Explorer with the added docker-compose.yml files, as depicted in Figure 4-28.</span></span>

![](./media/image34.PNG)

<span data-ttu-id="00d84-127">Figure 4-28 : les fichiers compose.yml de docker s’affichent maintenant dans l’Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="00d84-127">Figure 4-28: docker-compose.yml files now display in Solution Explorer</span></span>

<span data-ttu-id="00d84-128">Vous pouvez déployer un multicontainer docker à l’aide d’un fichier unique docker-compose.yml lorsque vous exécutez-composer ; Toutefois, Visual Studio ajoute un groupe d’éléments, donc vous pouvez remplacer les valeurs en fonction de l’environnement (de développement et de production) et l’exécution du type (release et debug).</span><span class="sxs-lookup"><span data-stu-id="00d84-128">You could deploy a multicontainer application by using a single docker-compose.yml file when you run docker-compose up; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="00d84-129">Cette fonctionnalité est expliquée mieux dans les chapitres.</span><span class="sxs-lookup"><span data-stu-id="00d84-129">This capability will be better explained in later chapters.</span></span>

<span data-ttu-id="00d84-130">**Plus d’informations :** pour plus d’informations sur la mise en œuvre des services et l’utilisation de Visual Studio Tools pour Docker, lisez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="00d84-130">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="00d84-131">Générer, déboguer, mettre à jour et actualiser des applications dans un conteneur Docker local : [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="00d84-131">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="00d84-132">Déployer un conteneur ASP.NET sur un hôte Docker distant : [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="00d84-132">Deploy an ASP.NET container to a remote Docker host: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="00d84-133">[Précédente] (docker-applications-interne-boucle-workflow.md) [suivant] (set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="00d84-133">[Previous] (docker-apps-inner-loop-workflow.md) [Next] (set-up-windows-containers-with-powershell.md)</span></span>

---
title: Déploiement d’applications .NET Core avec les outils CLI
description: Apprendre à déployer des applications .NET Core avec les outils de l’interface de ligne de commande (CLI)
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.openlocfilehash: 7b009068422686442ebff83b9400c365f34a3154
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244749"
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="c2378-103">Déploiement d’applications .NET Core avec les outils de l’interface de ligne de commande (CLI)</span><span class="sxs-lookup"><span data-stu-id="c2378-103">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="c2378-104">Pour déployer une application .NET Core, vous pouvez soit effectuer un *déploiement dépendant du framework* (qui inclut vos binaires d’application, mais qui dépend de la présence de .NET Core sur le système cible), soit effectuer un *déploiement autonome* (qui inclut votre application et les binaires .NET Core).</span><span class="sxs-lookup"><span data-stu-id="c2378-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="c2378-105">Pour obtenir une vue d’ensemble, consultez [Déploiement d’applications .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="c2378-105">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="c2378-106">Les sections suivantes montrent comment utiliser les [outils de l’interface de ligne de commande .NET Core](../tools/index.md) pour créer les genres de déploiements suivants :</span><span class="sxs-lookup"><span data-stu-id="c2378-106">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="c2378-107">Déploiement dépendant du framework</span><span class="sxs-lookup"><span data-stu-id="c2378-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="c2378-108">Déploiement dépendant du framework avec des dépendances tierces</span><span class="sxs-lookup"><span data-stu-id="c2378-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="c2378-109">Déploiement autonome</span><span class="sxs-lookup"><span data-stu-id="c2378-109">Self-contained deployment</span></span>
- <span data-ttu-id="c2378-110">Déploiement autonome avec des dépendances tierces</span><span class="sxs-lookup"><span data-stu-id="c2378-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="c2378-111">Si vous travaillez à partir de la ligne de commande, vous pouvez utiliser l’éditeur de programme de votre choix.</span><span class="sxs-lookup"><span data-stu-id="c2378-111">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="c2378-112">Si vous utilisez [Visual Studio Code](https://code.visualstudio.com) comme éditeur de programme, vous pouvez ouvrir une console de commande dans votre environnement Visual Studio Code en sélectionnant **Afficher** > **Terminal intégré**.</span><span class="sxs-lookup"><span data-stu-id="c2378-112">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="c2378-113">Déploiement dépendant du framework</span><span class="sxs-lookup"><span data-stu-id="c2378-113">Framework-dependent deployment</span></span>

<span data-ttu-id="c2378-114">Le déploiement d’un déploiement dépendant du framework sans dépendances tierces implique simplement la génération, le test et la publication de l’application.</span><span class="sxs-lookup"><span data-stu-id="c2378-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="c2378-115">Un exemple simple écrit en C# illustre le processus.</span><span class="sxs-lookup"><span data-stu-id="c2378-115">A simple example written in C# illustrates the process.</span></span> 

1. <span data-ttu-id="c2378-116">Créez un répertoire de projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-116">Create a project directory.</span></span>

   <span data-ttu-id="c2378-117">Créez un répertoire pour votre projet et définissez-le comme répertoire actif.</span><span class="sxs-lookup"><span data-stu-id="c2378-117">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="c2378-118">créer le projet ;</span><span class="sxs-lookup"><span data-stu-id="c2378-118">Create the project.</span></span>

   <span data-ttu-id="c2378-119">À partir de la ligne de commande, tapez [dotnet new console](../tools/dotnet-new.md) pour créer un projet de console C# dans ce répertoire.</span><span class="sxs-lookup"><span data-stu-id="c2378-119">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="c2378-120">Ajoutez le code source de l’application.</span><span class="sxs-lookup"><span data-stu-id="c2378-120">Add the application's source code.</span></span>

   <span data-ttu-id="c2378-121">Ouvrez le fichier *Program.cs* dans votre éditeur et remplacez le code généré automatiquement par le code suivant.</span><span class="sxs-lookup"><span data-stu-id="c2378-121">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="c2378-122">Il invite l’utilisateur à entrer du texte et affiche les différents mots entrés.</span><span class="sxs-lookup"><span data-stu-id="c2378-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="c2378-123">Il utilise l’expression régulière `\w+` pour séparer les mots dans le texte d’entrée.</span><span class="sxs-lookup"><span data-stu-id="c2378-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="c2378-124">Mettez à jour les dépendances et les outils du projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-124">Update the project's dependencies and tools.</span></span>
 
   <span data-ttu-id="c2378-125">Exécutez la commande [dotnet restore](../tools/dotnet-restore.md) ([voir la remarque](#dotnet-restore-note)) pour restaurer les dépendances spécifiées dans votre projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-125">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="c2378-126">Créez une build Debug de votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="c2378-127">Utilisez la commande [dotnet build](../tools/dotnet-build.md) pour générer votre application ou [dotnet run](../tools/dotnet-run.md) pour générer et exécuter l’application.</span><span class="sxs-lookup"><span data-stu-id="c2378-127">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="c2378-128">Déployez votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-128">Deploy your app.</span></span>

   <span data-ttu-id="c2378-129">Après avoir débogué et testé le programme, créez le déploiement à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c2378-129">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp1.1 -c Release
      ```
   <span data-ttu-id="c2378-130">Ceci crée une version de publication (au lieu d’une version Debug) de votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-130">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="c2378-131">Les fichiers résultants sont placés dans un répertoire nommé *publish* qui se trouve dans un sous-répertoire du répertoire *bin* de votre projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-131">The resulting files are placed in a directory named *publish*      that's in a subdirectory of your project's *bin* directory.</span></span>

   <span data-ttu-id="c2378-132">En même temps que les fichiers de votre application, le processus de publication produit un fichier de base de données du programme (.pdb) qui contient des informations de débogage sur votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-132">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="c2378-133">Le fichier est surtout utile pour le débogage d’exceptions.</span><span class="sxs-lookup"><span data-stu-id="c2378-133">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="c2378-134">Vous pouvez choisir de ne pas le distribuer avec les fichiers de votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-134">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="c2378-135">Vous devez toutefois l’enregistrer au cas où vous souhaiteriez déboguer la build Release de votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-135">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

   <span data-ttu-id="c2378-136">Vous pouvez déployer l’ensemble complet des fichiers d’application de la façon qui vous convient.</span><span class="sxs-lookup"><span data-stu-id="c2378-136">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="c2378-137">Par exemple, vous pouvez les empaqueter dans un fichier Zip, utiliser une simple commande `copy` ou les déployer avec n’importe quel package d’installation de votre choix.</span><span class="sxs-lookup"><span data-stu-id="c2378-137">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

1. <span data-ttu-id="c2378-138">Exécuter votre application</span><span class="sxs-lookup"><span data-stu-id="c2378-138">Run your app</span></span>

   <span data-ttu-id="c2378-139">Une fois l’installation terminée, les utilisateurs peuvent exécuter votre application en utilisant la commande `dotnet` suivie du nom de l’application. Par exemple : `dotnet fdd.dll`.</span><span class="sxs-lookup"><span data-stu-id="c2378-139">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

   <span data-ttu-id="c2378-140">Outre les binaires de l’application, votre programme d’installation doit également regrouper le programme d’installation du framework partagé ou vérifier qu’il est bien installé comme prérequis de l’installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="c2378-140">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="c2378-141">L’installation du framework partagé nécessite un accès Administrateur/racine.</span><span class="sxs-lookup"><span data-stu-id="c2378-141">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="c2378-142">Déploiement dépendant du framework avec des dépendances tierces</span><span class="sxs-lookup"><span data-stu-id="c2378-142">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="c2378-143">Pour exécuter un déploiement dépendant du framework avec une ou plusieurs dépendances tierces, ces dépendances doivent être accessibles à votre projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-143">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="c2378-144">Avant de pouvoir exécuter la commande `dotnet restore` ([voir la remarque](#dotnet-restore-note)), vous devez effectuer les deux étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c2378-144">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="c2378-145">Ajoutez les références aux bibliothèques tierces exigées à la section `<ItemGroup>` de votre fichier *csproj*.</span><span class="sxs-lookup"><span data-stu-id="c2378-145">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="c2378-146">La section `<ItemGroup>` suivante contient une dépendance à [Json.NET](http://www.newtonsoft.com/json) comme bibliothèque tierce :</span><span class="sxs-lookup"><span data-stu-id="c2378-146">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="c2378-147">Si vous ne l’avez pas encore fait, téléchargez le package NuGet contenant les dépendances tierces.</span><span class="sxs-lookup"><span data-stu-id="c2378-147">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="c2378-148">Pour télécharger le package, exécutez la commande `dotnet restore` ([voir la remarque](#dotnet-restore-note)) après avoir ajouté la dépendance.</span><span class="sxs-lookup"><span data-stu-id="c2378-148">To download the package, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="c2378-149">Comme la dépendance est résolue à partir du cache NuGet local au moment de la publication, elle doit être disponible sur votre système.</span><span class="sxs-lookup"><span data-stu-id="c2378-149">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="c2378-150">Notez qu’un déploiement dépendant du framework avec des dépendances tierces n’est portable que dans la mesure de la portabilité de ses dépendances tierces.</span><span class="sxs-lookup"><span data-stu-id="c2378-150">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="c2378-151">Par exemple, si une bibliothèque tierce prend uniquement en charge macOS, l’application n’est pas portable sur des systèmes Windows.</span><span class="sxs-lookup"><span data-stu-id="c2378-151">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="c2378-152">Cela se produit si la dépendance tierce elle-même dépend du code natif.</span><span class="sxs-lookup"><span data-stu-id="c2378-152">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="c2378-153">Un [serveur Kestrel](/aspnet/core/fundamentals/servers/kestrel) constitue un bon exemple, car il nécessite une dépendance native à [libuv](https://github.com/libuv/libuv).</span><span class="sxs-lookup"><span data-stu-id="c2378-153">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="c2378-154">Quand un déploiement dépendant du framework est créé pour une application avec ce type de dépendance tierce, le résultat publié contient un dossier pour chaque [identificateur de runtime](../rid-catalog.md) pris en charge par la dépendance native (et qui existe dans le package NuGet).</span><span class="sxs-lookup"><span data-stu-id="c2378-154">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="simpleSelf"></a> <span data-ttu-id="c2378-155">Déploiement autonome sans dépendances tierces</span><span class="sxs-lookup"><span data-stu-id="c2378-155">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="c2378-156">L’exécution d’un déploiement autonome sans dépendances tierces implique la création du projet, la modification du fichier *csproj*, la génération, le test et la publication de l’application.</span><span class="sxs-lookup"><span data-stu-id="c2378-156">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="c2378-157">Un exemple simple écrit en C# illustre le processus.</span><span class="sxs-lookup"><span data-stu-id="c2378-157">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="c2378-158">L’exemple montre comment créer un déploiement autonome à l’aide de l’[utilitaire dotnet](../tools/dotnet.md) à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="c2378-158">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="c2378-159">Créez un répertoire pour le projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-159">Create a directory for the project.</span></span>

   <span data-ttu-id="c2378-160">Créez un répertoire pour votre projet et définissez-le comme répertoire actif.</span><span class="sxs-lookup"><span data-stu-id="c2378-160">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="c2378-161">créer le projet ;</span><span class="sxs-lookup"><span data-stu-id="c2378-161">Create the project.</span></span>

   <span data-ttu-id="c2378-162">À partir de la ligne de commande, tapez [dotnet new console](../tools/dotnet-new.md) pour créer un projet de console C# dans ce répertoire.</span><span class="sxs-lookup"><span data-stu-id="c2378-162">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="c2378-163">Ajoutez le code source de l’application.</span><span class="sxs-lookup"><span data-stu-id="c2378-163">Add the application's source code.</span></span>

   <span data-ttu-id="c2378-164">Ouvrez le fichier *Program.cs* dans votre éditeur et remplacez le code généré automatiquement par le code suivant.</span><span class="sxs-lookup"><span data-stu-id="c2378-164">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="c2378-165">Il invite l’utilisateur à entrer du texte et affiche les différents mots entrés.</span><span class="sxs-lookup"><span data-stu-id="c2378-165">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="c2378-166">Il utilise l’expression régulière `\w+` pour séparer les mots dans le texte d’entrée.</span><span class="sxs-lookup"><span data-stu-id="c2378-166">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. <span data-ttu-id="c2378-167">Définissez les plateformes ciblées par votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-167">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="c2378-168">Créez une balise `<RuntimeIdentifiers>` dans la section `<PropertyGroup>` de votre fichier *csproj* qui définit les plateformes ciblées par votre application, puis spécifiez l’identificateur de runtime de chaque plateforme ciblée.</span><span class="sxs-lookup"><span data-stu-id="c2378-168">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="c2378-169">Notez que vous devez également ajouter un point-virgule pour séparer les identificateurs de runtime.</span><span class="sxs-lookup"><span data-stu-id="c2378-169">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="c2378-170">Consultez [Catalogue des identificateurs de runtime](../rid-catalog.md) pour obtenir une liste des identificateurs de runtime.</span><span class="sxs-lookup"><span data-stu-id="c2378-170">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span> 

   <span data-ttu-id="c2378-171">Par exemple, la section `<PropertyGroup>` suivante indique que l’application s’exécute sur les systèmes d’exploitation Windows 10 64 bits et sur le système d’exploitation OS X 64 bits version 10.11.</span><span class="sxs-lookup"><span data-stu-id="c2378-171">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="c2378-172">Notez que l’élément `<RuntimeIdentifiers>` peut apparaître dans n’importe quelle section `<PropertyGroup>` de votre fichier *csproj*.</span><span class="sxs-lookup"><span data-stu-id="c2378-172">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="c2378-173">Un exemple complet de fichier *csproj* figure plus loin dans cette section.</span><span class="sxs-lookup"><span data-stu-id="c2378-173">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="c2378-174">Mettez à jour les dépendances et les outils du projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-174">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="c2378-175">Exécutez la commande [dotnet restore](../tools/dotnet-restore.md) ([voir la remarque](#dotnet-restore-note)) pour restaurer les dépendances spécifiées dans votre projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-175">Run the [dotnet restore](../tools/dotnet-restore.md) ([see note](#dotnet-restore-note)) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="c2378-176">Créez une build Debug de votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-176">Create a Debug build of your app.</span></span>

   <span data-ttu-id="c2378-177">À partir de la ligne de commande, utilisez la commande [dotnet build](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="c2378-177">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="c2378-178">Après avoir débogué et testé le programme, créez les fichiers à déployer avec votre application pour chaque plateforme ciblée.</span><span class="sxs-lookup"><span data-stu-id="c2378-178">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="c2378-179">Utilisez la commande `dotnet publish` pour les deux plateformes cibles comme suit :</span><span class="sxs-lookup"><span data-stu-id="c2378-179">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="c2378-180">Ceci crée une version de publication (au lieu d’une version Debug) de votre application pour chaque plateforme cible.</span><span class="sxs-lookup"><span data-stu-id="c2378-180">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="c2378-181">Les fichiers résultants sont placés dans un sous-répertoire nommé *publish* qui se trouve dans un sous-répertoire du sous-répertoire *.\bin\Release\netcoreapp1.1\<identificateur_runtime>* de votre projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-181">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp1.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="c2378-182">Notez que chaque sous-répertoire contient l’ensemble complet des fichiers (les fichiers de votre application et tous les fichiers .NET Core) nécessaires pour lancer votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-182">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="c2378-183">En même temps que les fichiers de votre application, le processus de publication produit un fichier de base de données du programme (.pdb) qui contient des informations de débogage sur votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-183">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="c2378-184">Le fichier est surtout utile pour le débogage d’exceptions.</span><span class="sxs-lookup"><span data-stu-id="c2378-184">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="c2378-185">Vous pouvez choisir de ne pas l’empaqueter avec les fichiers de votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-185">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="c2378-186">Vous devez toutefois l’enregistrer au cas où vous souhaiteriez déboguer la build Release de votre application.</span><span class="sxs-lookup"><span data-stu-id="c2378-186">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="c2378-187">Déployez les fichiers publiés de la façon qui vous convient.</span><span class="sxs-lookup"><span data-stu-id="c2378-187">Deploy the published files in any way you like.</span></span> <span data-ttu-id="c2378-188">Par exemple, vous pouvez les empaqueter dans un fichier Zip, utiliser une simple commande `copy` ou les déployer avec n’importe quel package d’installation de votre choix.</span><span class="sxs-lookup"><span data-stu-id="c2378-188">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="c2378-189">Voici le fichier *csproj* complet pour ce projet.</span><span class="sxs-lookup"><span data-stu-id="c2378-189">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="c2378-190">Déploiement autonome avec des dépendances tierces</span><span class="sxs-lookup"><span data-stu-id="c2378-190">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="c2378-191">L’exécution d’un déploiement autonome avec une ou plusieurs dépendances tierces implique l’ajout des dépendances.</span><span class="sxs-lookup"><span data-stu-id="c2378-191">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="c2378-192">Avant de pouvoir exécuter la commande `dotnet restore` ([voir la remarque](#dotnet-restore-note)), vous devez effectuer les deux étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c2378-192">Two additional steps are required before you can run the `dotnet restore` ([see note](#dotnet-restore-note)) command:</span></span>

1. <span data-ttu-id="c2378-193">Ajoutez les références aux bibliothèques tierces à la section `<ItemGroup>` de votre fichier *csproj*.</span><span class="sxs-lookup"><span data-stu-id="c2378-193">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="c2378-194">La section `<ItemGroup>` suivante utilise Json.NET comme bibliothèque tierce.</span><span class="sxs-lookup"><span data-stu-id="c2378-194">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="c2378-195">Si vous ne l’avez pas encore fait, téléchargez le package NuGet contenant les dépendances tierces sur votre système.</span><span class="sxs-lookup"><span data-stu-id="c2378-195">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="c2378-196">Pour rendre la dépendance disponible pour votre application, exécutez la commande `dotnet restore` ([voir la remarque](#dotnet-restore-note)) après l’ajout de la dépendance.</span><span class="sxs-lookup"><span data-stu-id="c2378-196">To make the dependency available to your app, execute the `dotnet restore` ([see note](#dotnet-restore-note)) command after adding the dependency.</span></span> <span data-ttu-id="c2378-197">Comme la dépendance est résolue à partir du cache NuGet local au moment de la publication, elle doit être disponible sur votre système.</span><span class="sxs-lookup"><span data-stu-id="c2378-197">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="c2378-198">Voici le fichier *csproj* complet pour ce projet :</span><span class="sxs-lookup"><span data-stu-id="c2378-198">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="c2378-199">Quand vous déployez votre application, toutes les dépendances tierces utilisées dans votre application sont également incluses avec vos fichiers d’application.</span><span class="sxs-lookup"><span data-stu-id="c2378-199">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="c2378-200">Il n’est pas nécessaire que les bibliothèques tierces soient déjà présentes sur le système sur lequel l’application s’exécute.</span><span class="sxs-lookup"><span data-stu-id="c2378-200">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="c2378-201">Notez que vous pouvez déployer un déploiement autonome avec une bibliothèque tierce seulement sur des plateformes prises en charge par cette bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="c2378-201">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="c2378-202">Cela revient à avoir des dépendances tierces avec des dépendances natives dans un déploiement dépendant du framework, où les dépendances natives doivent être compatibles avec la plateforme sur laquelle l’application est déployée.</span><span class="sxs-lookup"><span data-stu-id="c2378-202">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

# <a name="see-also"></a><span data-ttu-id="c2378-203">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c2378-203">See also</span></span>

<span data-ttu-id="c2378-204">[Déploiement d’applications .NET Core](index.md) </span><span class="sxs-lookup"><span data-stu-id="c2378-204">[.NET Core Application Deployment](index.md) </span></span>  
[<span data-ttu-id="c2378-205">Catalogue d’identificateurs de runtime (RID) .NET Core</span><span class="sxs-lookup"><span data-stu-id="c2378-205">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)   


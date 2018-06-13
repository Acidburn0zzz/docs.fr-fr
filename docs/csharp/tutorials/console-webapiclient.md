---
title: Crée un client REST à l’aide de .NET Core
description: Ce didacticiel vous présente un certain nombre de fonctionnalités de .NET Core et du langage C#.
ms.date: 03/06/2017
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: bc3c23b277b233efba9f32cc49b29ac905f3abc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357619"
---
# <a name="rest-client"></a><span data-ttu-id="4c29b-103">Client REST</span><span class="sxs-lookup"><span data-stu-id="4c29b-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="4c29b-104">Introduction</span><span class="sxs-lookup"><span data-stu-id="4c29b-104">Introduction</span></span>
<span data-ttu-id="4c29b-105">Ce didacticiel vous présente un certain nombre de fonctionnalités de .NET Core et du langage C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="4c29b-106">Vous apprendrez à :</span><span class="sxs-lookup"><span data-stu-id="4c29b-106">You’ll learn:</span></span>
*   <span data-ttu-id="4c29b-107">Principes de base de l’interface de ligne de commande (CLI) de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c29b-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="4c29b-108">Une présentation des fonctionnalités du langage C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-108">An overview of C# Language features.</span></span>
*   <span data-ttu-id="4c29b-109">Gestion des dépendances avec NuGet</span><span class="sxs-lookup"><span data-stu-id="4c29b-109">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="4c29b-110">Communications HTTP</span><span class="sxs-lookup"><span data-stu-id="4c29b-110">HTTP Communications</span></span>
*   <span data-ttu-id="4c29b-111">Traitement des informations JSON</span><span class="sxs-lookup"><span data-stu-id="4c29b-111">Processing JSON information</span></span>
*   <span data-ttu-id="4c29b-112">Gestion de la configuration avec les attributs.</span><span class="sxs-lookup"><span data-stu-id="4c29b-112">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="4c29b-113">Vous allez générer une application qui émet des requêtes HTTP vers un service REST sur GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c29b-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="4c29b-114">Vous lirez des informations au format JSON et convertirez ce paquet JSON en objets C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="4c29b-115">Enfin, vous verrez comment travailler avec les objets C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="4c29b-116">Il existe un grand nombre de fonctionnalités dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="4c29b-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="4c29b-117">Nous allons les construire une par une.</span><span class="sxs-lookup"><span data-stu-id="4c29b-117">Let’s build them one by one.</span></span>

<span data-ttu-id="4c29b-118">Si vous préférez utiliser l’[exemple final](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) pour cette rubrique, vous pouvez le télécharger.</span><span class="sxs-lookup"><span data-stu-id="4c29b-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="4c29b-119">Pour obtenir des instructions de téléchargement, consultez [Exemples et didacticiels](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="4c29b-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c29b-120">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4c29b-120">Prerequisites</span></span>
<span data-ttu-id="4c29b-121">Vous devez configurer votre ordinateur pour exécuter .NET core.</span><span class="sxs-lookup"><span data-stu-id="4c29b-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="4c29b-122">Vous trouverez les instructions d’installation sur la page de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="4c29b-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="4c29b-123">Vous pouvez exécuter cette application sur Windows, Linux, Mac OS ou dans un conteneur Docker.</span><span class="sxs-lookup"><span data-stu-id="4c29b-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="4c29b-124">Vous devez installer l’éditeur de code de votre choix.</span><span class="sxs-lookup"><span data-stu-id="4c29b-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="4c29b-125">Les descriptions ci-dessous utilisent [Visual Studio Code](https://code.visualstudio.com/), qui est un éditeur de plateforme open source, multiplateforme.</span><span class="sxs-lookup"><span data-stu-id="4c29b-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="4c29b-126">Cependant, vous pouvez utiliser les outils avec lesquels vous êtes le plus à l’aise.</span><span class="sxs-lookup"><span data-stu-id="4c29b-126">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="4c29b-127">Création de l’application</span><span class="sxs-lookup"><span data-stu-id="4c29b-127">Create the Application</span></span>
<span data-ttu-id="4c29b-128">La première étape consiste à créer une nouvelle application.</span><span class="sxs-lookup"><span data-stu-id="4c29b-128">The first step is to create a new application.</span></span> <span data-ttu-id="4c29b-129">Ouvrez une invite de commandes et créez un nouveau répertoire pour votre application.</span><span class="sxs-lookup"><span data-stu-id="4c29b-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="4c29b-130">Réglez-le comme répertoire actuel.</span><span class="sxs-lookup"><span data-stu-id="4c29b-130">Make that the current directory.</span></span> <span data-ttu-id="4c29b-131">Saisissez la commande `dotnet new console` à l’invite.</span><span class="sxs-lookup"><span data-stu-id="4c29b-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="4c29b-132">Elle crée les fichiers de démarrage d’une application « Hello World » de base.</span><span class="sxs-lookup"><span data-stu-id="4c29b-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="4c29b-133">Avant d’apporter des modifications, examinons les étapes nécessaires pour exécuter l’application simple Hello World.</span><span class="sxs-lookup"><span data-stu-id="4c29b-133">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="4c29b-134">Après avoir créé l’application, tapez `dotnet restore` ([voir note](#dotnet-restore-note)) à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="4c29b-134">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="4c29b-135">Cette commande exécute le processus de restauration de package NuGet.</span><span class="sxs-lookup"><span data-stu-id="4c29b-135">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="4c29b-136">NuGet est un gestionnaire de packages .NET.</span><span class="sxs-lookup"><span data-stu-id="4c29b-136">NuGet is a .NET package manager.</span></span> <span data-ttu-id="4c29b-137">Cette commande télécharge les dépendances manquantes pour votre projet.</span><span class="sxs-lookup"><span data-stu-id="4c29b-137">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="4c29b-138">Comme il s’agit d’un nouveau projet, aucune des dépendances n’est en place, donc la première exécution téléchargera le framework .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c29b-138">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="4c29b-139">Après cette étape initiale, vous devez exécuter `dotnet restore` ([voir note](#dotnet-restore-note)) lorsque vous ajoutez de nouveaux packages dépendants ou mettez à jour les versions de vos dépendances.</span><span class="sxs-lookup"><span data-stu-id="4c29b-139">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="4c29b-140">Après la restauration des packages, vous exécutez `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="4c29b-141">Cela exécute le moteur de génération et crée votre application.</span><span class="sxs-lookup"><span data-stu-id="4c29b-141">This executes the build engine and creates your application.</span></span> <span data-ttu-id="4c29b-142">Enfin, vous exécutez `dotnet run` pour lancer votre application.</span><span class="sxs-lookup"><span data-stu-id="4c29b-142">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="4c29b-143">Ajout de nouvelles dépendances</span><span class="sxs-lookup"><span data-stu-id="4c29b-143">Adding New Dependencies</span></span>
<span data-ttu-id="4c29b-144">Un des objectifs de conception clés de .NET Core est de réduire la taille de l’installation du framework .NET.</span><span class="sxs-lookup"><span data-stu-id="4c29b-144">One of the key design goals for .NET Core is to minimize the size of the .NET framework installation.</span></span> <span data-ttu-id="4c29b-145">Le framework d’application .NET Core contient uniquement les éléments les plus courants du framework .NET complet.</span><span class="sxs-lookup"><span data-stu-id="4c29b-145">The .NET Core Application framework contains only the most common elements of the .NET full framework.</span></span> <span data-ttu-id="4c29b-146">Si une application a besoin de bibliothèques supplémentaires pour certaines de ses fonctionnalités, vous ajoutez ces dépendances dans votre fichier projet (\*.csproj) en C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-146">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="4c29b-147">Dans notre exemple, vous devez ajouter le package `System.Runtime.Serialization.Json` pour que votre application puisse traiter les réponses JSON.</span><span class="sxs-lookup"><span data-stu-id="4c29b-147">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="4c29b-148">Ouvrez votre fichier projet `csproj`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-148">Open your `csproj` project file.</span></span> <span data-ttu-id="4c29b-149">La première ligne du fichier devrait s’afficher comme :</span><span class="sxs-lookup"><span data-stu-id="4c29b-149">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="4c29b-150">Ajoutez ce qui suit immédiatement après cette ligne :</span><span class="sxs-lookup"><span data-stu-id="4c29b-150">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="4c29b-151">La plupart des éditeurs de code fournissent la saisie semi-automatique pour différentes versions de ces bibliothèques.</span><span class="sxs-lookup"><span data-stu-id="4c29b-151">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="4c29b-152">Vous souhaiterez généralement utiliser la dernière version d’un package que vous ajoutez.</span><span class="sxs-lookup"><span data-stu-id="4c29b-152">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="4c29b-153">Toutefois, il est important de vous assurer que les versions de tous les packages correspondent et qu’ils correspondent également la version du framework d’application .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c29b-153">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="4c29b-154">Une fois que vous avez apporté ces modifications, vous devez réexécuter `dotnet restore` ([voir note](#dotnet-restore-note))afin que le package soit installé sur votre système.</span><span class="sxs-lookup"><span data-stu-id="4c29b-154">After you've made these changes, you should run `dotnet restore` ([see note](#dotnet-restore-note)) again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="4c29b-155">Effectuer des requêtes web</span><span class="sxs-lookup"><span data-stu-id="4c29b-155">Making Web Requests</span></span>
<span data-ttu-id="4c29b-156">Vous êtes maintenant prêt à commencer la récupération des données à partir du web.</span><span class="sxs-lookup"><span data-stu-id="4c29b-156">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="4c29b-157">Dans cette application, vous obtiendrez des informations à partir de [l’API GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="4c29b-157">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="4c29b-158">Nous allons lire des informations sur les projets couverts par la [.NET Foundation](http://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="4c29b-158">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="4c29b-159">Vous allez commencer par créer la demande à l’API GitHub pour récupérer des informations sur les projets.</span><span class="sxs-lookup"><span data-stu-id="4c29b-159">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="4c29b-160">Vous allez utiliser le point de terminaison [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span><span class="sxs-lookup"><span data-stu-id="4c29b-160">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="4c29b-161">Vous souhaitez récupérer toutes les informations sur ces projets, vous allez donc utiliser une requête HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="4c29b-161">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="4c29b-162">Votre navigateur utilise également les requêtes HTTP GET, vous pouvez donc coller cette URL dans votre navigateur pour voir les informations que vous recevez et traitez.</span><span class="sxs-lookup"><span data-stu-id="4c29b-162">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="4c29b-163">Vous utilisez la classe <xref:System.Net.Http.HttpClient> pour effectuer des requêtes web.</span><span class="sxs-lookup"><span data-stu-id="4c29b-163">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="4c29b-164">Comme toutes les API .NET modernes, <xref:System.Net.Http.HttpClient> prend en charge uniquement les méthodes async pour ses API les plus anciennes.</span><span class="sxs-lookup"><span data-stu-id="4c29b-164">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="4c29b-165">Commencez par créer une méthode async.</span><span class="sxs-lookup"><span data-stu-id="4c29b-165">Start by making an async method.</span></span> <span data-ttu-id="4c29b-166">Vous allez effectuer l’implémentation lors de la création des fonctionnalités de l’application.</span><span class="sxs-lookup"><span data-stu-id="4c29b-166">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="4c29b-167">Commencez en ouvrant le fichier `program.cs` dans votre répertoire de projet et l’ajout de la méthode suivante à la classe `Program` :</span><span class="sxs-lookup"><span data-stu-id="4c29b-167">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="4c29b-168">Vous devrez ajouter une instruction `using` en haut de votre méthode `Main` afin que le compilateur C# reconnaisse le type <xref:System.Threading.Tasks.Task> :</span><span class="sxs-lookup"><span data-stu-id="4c29b-168">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="4c29b-169">Si vous générez votre projet à ce stade, vous obtiendrez un avertissement généré pour cette méthode, car elle ne contient aucun opérateur `await` et s’exécute de façon synchrone.</span><span class="sxs-lookup"><span data-stu-id="4c29b-169">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="4c29b-170">Ignorez-le pour le moment. vous ajouterez des opérateurs `await` lorsque vous remplirez la méthode.</span><span class="sxs-lookup"><span data-stu-id="4c29b-170">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="4c29b-171">Ensuite, renommez l’espace de noms défini dans l’instruction `namespace` de sa valeur par défaut de `ConsoleApp` en `WebAPIClient`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-171">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="4c29b-172">Plus tard, nous allons définir une classe `repo` dans cet espace de noms.</span><span class="sxs-lookup"><span data-stu-id="4c29b-172">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="4c29b-173">Ensuite, mettez à jour la méthode `Main` pour appeler cette méthode.</span><span class="sxs-lookup"><span data-stu-id="4c29b-173">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="4c29b-174">La méthode `ProcessRepositories` retourne une tâche, et vous ne devez pas quitter le programme avant la fin de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="4c29b-174">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="4c29b-175">Par conséquent, vous devez utiliser la méthode `Wait` pour bloquer et attendre la fin de la tâche :</span><span class="sxs-lookup"><span data-stu-id="4c29b-175">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="4c29b-176">À présent, vous disposez d’un programme qui ne fait rien, mais le fait de façon asynchrone.</span><span class="sxs-lookup"><span data-stu-id="4c29b-176">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="4c29b-177">Nous allons l’améliorer.</span><span class="sxs-lookup"><span data-stu-id="4c29b-177">Let's improve it.</span></span>

<span data-ttu-id="4c29b-178">Tout d’abord, vous avez besoin d’un objet pouvant récupérer des données à partir du web ; pour ce faire, vous pouvez utiliser <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="4c29b-178">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="4c29b-179">Cet objet gère la demande et les réponses.</span><span class="sxs-lookup"><span data-stu-id="4c29b-179">This object handles the request and the responses.</span></span> <span data-ttu-id="4c29b-180">Instanciez une seule instance de ce type dans la classe `Program` dans le fichier Program.cs.</span><span class="sxs-lookup"><span data-stu-id="4c29b-180">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static void Main(string[] args)
        {
            //...
        }
    }
}
```

 <span data-ttu-id="4c29b-181">Revenons à la méthode `ProcessRepositories` et créons sa première version :</span><span class="sxs-lookup"><span data-stu-id="4c29b-181">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="4c29b-182">Vous devrez également ajouter deux nouvelles instructions using en haut du fichier pour que cela compile :</span><span class="sxs-lookup"><span data-stu-id="4c29b-182">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="4c29b-183">Cette première version effectue une requête web pour lire la liste de tous les dépôts de l’organisation dotnet foundation.</span><span class="sxs-lookup"><span data-stu-id="4c29b-183">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="4c29b-184">(L’ID GitHub de la .NET Foundation est 'dotnet').</span><span class="sxs-lookup"><span data-stu-id="4c29b-184">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="4c29b-185">Les premières lignes configurent <xref:System.Net.Http.HttpClient> pour cette requête.</span><span class="sxs-lookup"><span data-stu-id="4c29b-185">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="4c29b-186">Tout d’abord, il est configuré pour accepter les réponses JSON de GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c29b-186">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="4c29b-187">Ce format est simplement du JSON.</span><span class="sxs-lookup"><span data-stu-id="4c29b-187">This format is simply JSON.</span></span> <span data-ttu-id="4c29b-188">La ligne suivante ajoute un en-tête d’agent utilisateur à toutes les requêtes à partir de cet objet.</span><span class="sxs-lookup"><span data-stu-id="4c29b-188">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="4c29b-189">Ces deux en-têtes sont vérifiés par le code du serveur GitHub et sont nécessaires pour récupérer des informations à partir de GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c29b-189">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="4c29b-190">Une fois que vous avez configuré le <xref:System.Net.Http.HttpClient>, effectuez une requête web et récupérez la réponse.</span><span class="sxs-lookup"><span data-stu-id="4c29b-190">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="4c29b-191">Dans cette première version, vous utilisez la méthode pratique <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4c29b-191">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="4c29b-192">Cette méthode démarre une tâche qui effectue la requête web, et, lorsque la demande est renvoyée, lit le flux de réponse puis extrait le contenu à partir du flux.</span><span class="sxs-lookup"><span data-stu-id="4c29b-192">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="4c29b-193">Le corps de la réponse est renvoyé en tant que <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="4c29b-193">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="4c29b-194">La chaîne est disponible lorsque la tâche est terminée.</span><span class="sxs-lookup"><span data-stu-id="4c29b-194">The string is available when the task completes.</span></span> 

<span data-ttu-id="4c29b-195">Les deux dernières lignes de cette méthode attendent cette tâche et impriment la réponse dans la console.</span><span class="sxs-lookup"><span data-stu-id="4c29b-195">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="4c29b-196">Générez l'application et exécutez-la.</span><span class="sxs-lookup"><span data-stu-id="4c29b-196">Build the app, and run it.</span></span> <span data-ttu-id="4c29b-197">L’avertissement de génération a disparu maintenant, car `ProcessRepositories` contient maintenant un opérateur `await`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-197">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="4c29b-198">Vous verrez long affichage de texte au format JSON.</span><span class="sxs-lookup"><span data-stu-id="4c29b-198">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="4c29b-199">Traitement du résultat JSON</span><span class="sxs-lookup"><span data-stu-id="4c29b-199">Processing the JSON Result</span></span>

<span data-ttu-id="4c29b-200">À ce stade, vous avez écrit le code pour récupérer une réponse à partir d’un serveur web et afficher le texte contenu dans cette réponse.</span><span class="sxs-lookup"><span data-stu-id="4c29b-200">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="4c29b-201">Ensuite, nous allons convertir cette réponse JSON en objets C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-201">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="4c29b-202">Le sérialiseur JSON convertit des données JSON en objets C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-202">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="4c29b-203">Votre première tâche consiste à définir un type de classe C# pour contenir les informations à utiliser à partir de cette réponse.</span><span class="sxs-lookup"><span data-stu-id="4c29b-203">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="4c29b-204">Nous allons prendre notre temps pour étudier cela, commençons donc par un type C# simple qui contient le nom du dépôt :</span><span class="sxs-lookup"><span data-stu-id="4c29b-204">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
``` 

<span data-ttu-id="4c29b-205">Placez le code ci-dessus dans un fichier nommé « repo.cs ».</span><span class="sxs-lookup"><span data-stu-id="4c29b-205">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="4c29b-206">Cette version de la classe représente le chemin d’accès le plus simple pour traiter les données JSON.</span><span class="sxs-lookup"><span data-stu-id="4c29b-206">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="4c29b-207">Le nom de classe et le nom du membre correspondent aux noms utilisés dans le paquet JSON, au lieu des conventions C# suivantes.</span><span class="sxs-lookup"><span data-stu-id="4c29b-207">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="4c29b-208">Vous allez corriger cela en fournissant des attributs de configuration ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="4c29b-208">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="4c29b-209">Cette classe décrit une autre fonctionnalité importante de la sérialisation et de désérialisation JSON : tous les champs dans le paquet JSON font partie de cette classe.</span><span class="sxs-lookup"><span data-stu-id="4c29b-209">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="4c29b-210">Le sérialiseur JSON ignore les informations qui ne sont pas incluses dans le type de classe utilisé.</span><span class="sxs-lookup"><span data-stu-id="4c29b-210">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="4c29b-211">Cette fonctionnalité facilite la création de types qui fonctionnent avec uniquement un sous-ensemble des champs dans le paquet JSON.</span><span class="sxs-lookup"><span data-stu-id="4c29b-211">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="4c29b-212">Maintenant que vous avez créé le type, nous allons le désérialiser.</span><span class="sxs-lookup"><span data-stu-id="4c29b-212">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="4c29b-213">Vous devez créer un objet <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="4c29b-213">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="4c29b-214">Cet objet doit connaître le type CLR attendu pour le paquet JSON qu’il récupère.</span><span class="sxs-lookup"><span data-stu-id="4c29b-214">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="4c29b-215">Le paquet de GitHub contient une séquence de dépôts, c’est pourquoi `List<repo>` est du bon type.</span><span class="sxs-lookup"><span data-stu-id="4c29b-215">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="4c29b-216">Ajoutez la ligne suivante à votre méthode `ProcessRepositories` :</span><span class="sxs-lookup"><span data-stu-id="4c29b-216">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="4c29b-217">Vous utilisez deux nouveaux espaces de noms, vous devez donc les ajouter aussi :</span><span class="sxs-lookup"><span data-stu-id="4c29b-217">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="4c29b-218">Ensuite, vous utiliserez le sérialiseur pour convertir le JSON en objets C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-218">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="4c29b-219">Remplacez l’appel à <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> dans votre méthode `ProcessRepositories` avec les deux lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c29b-219">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="4c29b-220">Notez que vous utilisez maintenant <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> au lieu de <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="4c29b-220">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="4c29b-221">Le sérialiseur utilise un flux plutôt qu’une chaîne comme source.</span><span class="sxs-lookup"><span data-stu-id="4c29b-221">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="4c29b-222">Nous allons expliquer quelques fonctionnalités du langage C# qui sont utilisées dans la deuxième ligne ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="4c29b-222">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="4c29b-223">L’argument <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> est une expression `await`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-223">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="4c29b-224">Les expressions await peuvent apparaître quasiment n’importe où dans votre code, bien que jusqu'à présent, vous les avez uniquement vues dans le cadre d’une instruction d’assignation.</span><span class="sxs-lookup"><span data-stu-id="4c29b-224">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="4c29b-225">Deuxièmement, l’opérateur `as` convertit le type au moment de la compilation `object` en `List<repo>`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-225">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="4c29b-226">La déclaration de <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> déclare qu’un objet de type <xref:System.Object?displayProperty=nameWithType> est retourné.</span><span class="sxs-lookup"><span data-stu-id="4c29b-226">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4c29b-227"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> retourne le type que vous avez spécifié une fois que vous l’avez construit (`List<repo>` dans ce didacticiel).</span><span class="sxs-lookup"><span data-stu-id="4c29b-227"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="4c29b-228">Si la conversion échoue, l’opérateur `as` a la valeur `null`, au lieu de lever une exception.</span><span class="sxs-lookup"><span data-stu-id="4c29b-228">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="4c29b-229">Nous en avons presque terminé avec cette section.</span><span class="sxs-lookup"><span data-stu-id="4c29b-229">You're almost done with this section.</span></span> <span data-ttu-id="4c29b-230">Maintenant que vous avez converti le JSON en objets C#, nous allons afficher le nom de chaque dépôt.</span><span class="sxs-lookup"><span data-stu-id="4c29b-230">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="4c29b-231">Remplacez les lignes :</span><span class="sxs-lookup"><span data-stu-id="4c29b-231">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="4c29b-232">avec les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4c29b-232">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="4c29b-233">Compilez et exécutez l'application.</span><span class="sxs-lookup"><span data-stu-id="4c29b-233">Compile and run the application.</span></span> <span data-ttu-id="4c29b-234">Cela affichera les noms des espaces de stockage qui font partie de la .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="4c29b-234">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="4c29b-235">Contrôle de la sérialisation</span><span class="sxs-lookup"><span data-stu-id="4c29b-235">Controlling Serialization</span></span>

<span data-ttu-id="4c29b-236">Avant d’ajouter plus de fonctionnalités, nous allons traiter le type `repo` et lui faire suivre les conventions standard C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-236">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="4c29b-237">Vous verrez comment procéder en annotant le type `repo` avec des *attributs* qui contrôlent la manière dont fonctionne le sérialiseur JSON.</span><span class="sxs-lookup"><span data-stu-id="4c29b-237">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="4c29b-238">Dans votre cas, vous utiliserez ces attributs pour définir un mappage entre les noms de clé JSON et la classe C# et les noms des membres.</span><span class="sxs-lookup"><span data-stu-id="4c29b-238">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="4c29b-239">Les deux attributs utilisés sont l’attribut `DataContract` et l’attribut `DataMember`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-239">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="4c29b-240">Par convention, toutes les classes d’attributs se terminent par le suffixe `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-240">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="4c29b-241">Toutefois, il est inutile d’utiliser ce suffixe lorsque vous appliquez un attribut.</span><span class="sxs-lookup"><span data-stu-id="4c29b-241">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="4c29b-242">Les attributs `DataContract` et `DataMember` se trouvent dans une autre bibliothèque, vous devez donc ajouter cette bibliothèque à votre fichier de projet C# en tant que dépendance.</span><span class="sxs-lookup"><span data-stu-id="4c29b-242">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="4c29b-243">Ajoutez la ligne suivante à la section `<ItemGroup>` de votre fichier projet :</span><span class="sxs-lookup"><span data-stu-id="4c29b-243">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="4c29b-244">Après avoir enregistré le fichier, exécutez `dotnet restore` ([voir note](#dotnet-restore-note)) pour récupérer ce package.</span><span class="sxs-lookup"><span data-stu-id="4c29b-244">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="4c29b-245">Ensuite, ouvrez le fichier `repo.cs`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-245">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="4c29b-246">Nous allons modifier le nom pour adopter la casse Pascal, et entièrement épeler le nom `Repository`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-246">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="4c29b-247">Nous souhaitons toujours mapper des nœuds de « repo » JSON sur ce type, vous devez donc ajouter l’attribut `DataContract` à la déclaration de classe.</span><span class="sxs-lookup"><span data-stu-id="4c29b-247">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="4c29b-248">Vous devez définir la propriété `Name` de l’attribut sur le nom des nœuds JSON qui correspondent à ce type :</span><span class="sxs-lookup"><span data-stu-id="4c29b-248">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="4c29b-249">L’attribut <xref:System.Runtime.Serialization.DataContractAttribute> est un membre de l’espace de noms <xref:System.Runtime.Serialization>, vous devez donc l’instruction `using` appropriée au début du fichier :</span><span class="sxs-lookup"><span data-stu-id="4c29b-249">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="4c29b-250">Vous avez modifié le nom de la classe `repo` en `Repository`, de sorte que vous devrez effectuer le même changement de nom dans le fichier Program.cs (certains éditeurs peuvent prendre en charge une refactorisation de changement de nom qui fera automatiquement cette modification :)</span><span class="sxs-lookup"><span data-stu-id="4c29b-250">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="4c29b-251">Ensuite, nous allons apporter la même modification avec le champ `name` à l’aide de la classe <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4c29b-251">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="4c29b-252">Apportez les modifications suivantes à la déclaration du champ `name` dans repo.cs :</span><span class="sxs-lookup"><span data-stu-id="4c29b-252">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="4c29b-253">Cette modification signifie que vous devez modifier le code qui écrit le nom de chaque dépôt dans program.cs :</span><span class="sxs-lookup"><span data-stu-id="4c29b-253">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="4c29b-254">Effectuez un `dotnet build` suivi d’un `dotnet run` pour vous assurer que vous disposez des bons mappages.</span><span class="sxs-lookup"><span data-stu-id="4c29b-254">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="4c29b-255">Vous devriez voir la même sortie que précédemment.</span><span class="sxs-lookup"><span data-stu-id="4c29b-255">You should see the same output as before.</span></span> <span data-ttu-id="4c29b-256">Avant de traiter d’autres propriétés à partir du serveur web, apportons une dernière modification à la classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-256">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="4c29b-257">Le membre `Name` est un champ accessible publiquement.</span><span class="sxs-lookup"><span data-stu-id="4c29b-257">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="4c29b-258">Cela n’est pas une bonne pratique pour les langages orientés objet, nous allons donc le changer en propriété.</span><span class="sxs-lookup"><span data-stu-id="4c29b-258">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="4c29b-259">Pour ce que nous cherchons à faire, nous n’avons pas besoin de code spécifique à exécuter lors de l’obtention ou la définition de la propriété, mais la modification en propriété permettra d’apporter ces modifications plus facilement par la suite sans casser le code qui utilise la classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-259">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="4c29b-260">Supprimez la définition de champ et remplacez-la par une [propriété implémentée automatiquement](../programming-guide/classes-and-structs/auto-implemented-properties.md) :</span><span class="sxs-lookup"><span data-stu-id="4c29b-260">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="4c29b-261">Le compilateur génère le corps des accesseurs `get` et `set`, mais aussi un champ privé pour stocker le nom.</span><span class="sxs-lookup"><span data-stu-id="4c29b-261">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="4c29b-262">Cela est similaire au code suivant que vous pourriez taper manuellement :</span><span class="sxs-lookup"><span data-stu-id="4c29b-262">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="4c29b-263">Nous allons apporter une modification de plus avant d’ajouter de nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="4c29b-263">Let's make one more change before adding new features.</span></span> <span data-ttu-id="4c29b-264">La méthode `ProcessRepositories` peut faire le travail de façon asynchrone et renvoyer une collection des espaces de stockage.</span><span class="sxs-lookup"><span data-stu-id="4c29b-264">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="4c29b-265">Nous allons renvoyer `List<Repository>` à partir de cette méthode et déplacer le code qui écrit les informations dans la méthode `Main`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-265">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="4c29b-266">Modifiez la signature de `ProcessRepositories` pour retourner une tâche dont le résultat est une liste d’objets `Repository` :</span><span class="sxs-lookup"><span data-stu-id="4c29b-266">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="4c29b-267">Ensuite, retournez simplement les dépôts après le traitement de la réponse JSON :</span><span class="sxs-lookup"><span data-stu-id="4c29b-267">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="4c29b-268">Le compilateur génère l’objet `Task<T>` pour la valeur de retour, car vous avez marqué cette méthode comme `async`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-268">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="4c29b-269">Ensuite, nous allons modifier la méthode `Main` afin qu’elle capture les résultats et écrive le nom de chaque dépôt dans la console.</span><span class="sxs-lookup"><span data-stu-id="4c29b-269">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="4c29b-270">Votre méthode `Main` se présente maintenant comme suit :</span><span class="sxs-lookup"><span data-stu-id="4c29b-270">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="4c29b-271">L’accès à la propriété `Result` d’une tâche est bloqué jusqu'à la fin de la tâche.</span><span class="sxs-lookup"><span data-stu-id="4c29b-271">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="4c29b-272">En règle générale, il serait préférable d’utiliser `await` pour attendre l’achèvement de la tâche, comme dans la méthode `ProcessRepositories`, mais cela n’est pas autorisé dans la méthode `Main`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-272">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="4c29b-273">Lire plus d'informations</span><span class="sxs-lookup"><span data-stu-id="4c29b-273">Reading More Information</span></span>

<span data-ttu-id="4c29b-274">Terminons par le traitement d’un certain nombre de propriétés dans le paquet JSON envoyé à partir de l’API GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c29b-274">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="4c29b-275">Vous ne voudrez pas récupérer tous les éléments, mais ajouter quelques propriétés vous permettra de découvrir d’autres fonctionnalités du langage C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-275">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="4c29b-276">Commençons par ajouter quelques autres types simples à la définition de classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-276">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="4c29b-277">Ajoutez ces propriétés à cette classe :</span><span class="sxs-lookup"><span data-stu-id="4c29b-277">Add these properties to that class:</span></span>

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="4c29b-278">Ces propriétés ont intégré des conversions intégrées du type chaîne (c’est ce que contiennent les paquets JSON) vers le type cible.</span><span class="sxs-lookup"><span data-stu-id="4c29b-278">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="4c29b-279">Le type <xref:System.Uri> peut être nouveau pour vous.</span><span class="sxs-lookup"><span data-stu-id="4c29b-279">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="4c29b-280">Il représente un URI, ou dans ce cas, une URL.</span><span class="sxs-lookup"><span data-stu-id="4c29b-280">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="4c29b-281">Dans le cas des types `Uri` et `int`, si le paquet JSON contient des données qui ne sont pas convertibles dans le type cible, l’action de sérialisation lèvera une exception.</span><span class="sxs-lookup"><span data-stu-id="4c29b-281">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="4c29b-282">Une fois que vous avez ajouté cela, mettez à jour la méthode `Main` pour afficher ces éléments :</span><span class="sxs-lookup"><span data-stu-id="4c29b-282">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```
<span data-ttu-id="4c29b-283">Dans la dernière étape, nous allons ajouter les informations de la dernière opération Push.</span><span class="sxs-lookup"><span data-stu-id="4c29b-283">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="4c29b-284">Ces informations sont formatées de cette façon dans la réponse JSON :</span><span class="sxs-lookup"><span data-stu-id="4c29b-284">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="4c29b-285">Ce format ne suit pas les formats .NET <xref:System.DateTime> standard.</span><span class="sxs-lookup"><span data-stu-id="4c29b-285">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="4c29b-286">Par conséquent, vous devez écrire une méthode de conversion personnalisée.</span><span class="sxs-lookup"><span data-stu-id="4c29b-286">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="4c29b-287">En outre, vous ne souhaiterez probablement pas que la chaîne brute soit exposée aux utilisateurs de la classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-287">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="4c29b-288">Les attributs permettent aussi de contrôler cela.</span><span class="sxs-lookup"><span data-stu-id="4c29b-288">Attributes can help control that as well.</span></span> <span data-ttu-id="4c29b-289">D’abord, définissez une propriété `private` qui contient la représentation sous forme de chaîne de date et d’heure dans votre classe `Repository` :</span><span class="sxs-lookup"><span data-stu-id="4c29b-289">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="4c29b-290">L’attribut `DataMember` informe le sérialiseur qu’elle doit être traitée, même si elle n’est pas un membre public.</span><span class="sxs-lookup"><span data-stu-id="4c29b-290">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="4c29b-291">Ensuite, vous devez écrire une propriété publique en lecture seule qui convertit la chaîne en un objet <xref:System.DateTime> valide et retourne cette <xref:System.DateTime> :</span><span class="sxs-lookup"><span data-stu-id="4c29b-291">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

<span data-ttu-id="4c29b-292">Examinons les nouvelles constructions ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="4c29b-292">Let's go over the new constructs above.</span></span> <span data-ttu-id="4c29b-293">L’attribut `IgnoreDataMember` indique au sérialiseur que ce type ne doit pas être lu ou écrit à partir de n’importe quel objet JSON.</span><span class="sxs-lookup"><span data-stu-id="4c29b-293">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="4c29b-294">Cette propriété contient uniquement un accesseur `get`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-294">This property contains only a `get` accessor.</span></span> <span data-ttu-id="4c29b-295">Il n'existe aucun accesseur `set`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-295">There is no `set` accessor.</span></span> <span data-ttu-id="4c29b-296">C’est la façon dont vous définissez une propriété *en lecture seule* en C#.</span><span class="sxs-lookup"><span data-stu-id="4c29b-296">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="4c29b-297">(Oui, vous pouvez créer des propriétés *en écriture seule* en C#, mais leur intérêt est limité.) La méthode <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> analyse une chaîne et crée un objet <xref:System.DateTime> sous un format de date fourni, puis ajoute des métadonnées supplémentaires à `DateTime` en utilisant un objet `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="4c29b-297">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="4c29b-298">Si l’opération d’analyse échoue, l’accesseur de propriété lève une exception.</span><span class="sxs-lookup"><span data-stu-id="4c29b-298">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="4c29b-299">Pour utiliser <xref:System.Globalization.CultureInfo.InvariantCulture>, vous devez ajouter l’espace de noms <xref:System.Globalization> aux instructions `using` dans `repo.cs` :</span><span class="sxs-lookup"><span data-stu-id="4c29b-299">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="4c29b-300">Enfin, ajoutez une dernière instruction de sortie dans la console et vous êtes prêt à générer et exécuter de nouveau cette application :</span><span class="sxs-lookup"><span data-stu-id="4c29b-300">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="4c29b-301">Votre version doit maintenant correspondre à l’[exemple terminé](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="4c29b-301">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="4c29b-302">Conclusion</span><span class="sxs-lookup"><span data-stu-id="4c29b-302">Conclusion</span></span>

<span data-ttu-id="4c29b-303">Ce didacticiel vous a montré comment effectuer des demandes web, analyser le résultat et afficher les propriétés de ces résultats.</span><span class="sxs-lookup"><span data-stu-id="4c29b-303">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="4c29b-304">Vous avez également ajouté de nouveaux packages en tant que dépendances dans votre projet.</span><span class="sxs-lookup"><span data-stu-id="4c29b-304">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="4c29b-305">Vous avez vu certaines des fonctionnalités du langage C# qui prennent en charge des techniques orientées objet.</span><span class="sxs-lookup"><span data-stu-id="4c29b-305">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

---
title: "Didacticiel : création d’un fournisseur de type (F#)"
description: "Découvrez comment créer vos propres fournisseurs de type F # dans F # 3.0 en examinant les fournisseurs de type simple pour illustrer les concepts de base."
keywords: visual f#, f#, programmation fonctionnelle
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 82bec076-19d4-470c-979f-6c3a14b7c70a
ms.openlocfilehash: 30d1c20d66fd0a193c05c97ee726a886f98356ad
ms.sourcegitcommit: 1c0b0f082b3f300e54b4d069b317ac724c88ddc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="tutorial-creating-a-type-provider"></a><span data-ttu-id="4efb9-104">Didacticiel : Création d’un fournisseur de Type</span><span class="sxs-lookup"><span data-stu-id="4efb9-104">Tutorial: Creating a Type Provider</span></span>

<span data-ttu-id="4efb9-105">Le mécanisme de fournisseur de type en F # est une partie importante de la prise en charge pour la programmation riche d’informations.</span><span class="sxs-lookup"><span data-stu-id="4efb9-105">The type provider mechanism in F# is a significant part of its support for information rich programming.</span></span> <span data-ttu-id="4efb9-106">Ce didacticiel explique comment créer vos propres fournisseurs de type en vous guidant à travers le développement de plusieurs fournisseurs de type simple pour illustrer les concepts de base.</span><span class="sxs-lookup"><span data-stu-id="4efb9-106">This tutorial explains how to create your own type providers by walking you through the development of several simple type providers to illustrate the basic concepts.</span></span> <span data-ttu-id="4efb9-107">Pour plus d’informations sur le mécanisme de fournisseur de type en F #, consultez [fournisseurs de Type](index.md).</span><span class="sxs-lookup"><span data-stu-id="4efb9-107">For more information about the type provider mechanism in F#, see [Type Providers](index.md).</span></span>

<span data-ttu-id="4efb9-108">L’écosystème de F # contient une plage de fournisseurs de type pour les services de données Internet et d’entreprise couramment utilisés.</span><span class="sxs-lookup"><span data-stu-id="4efb9-108">The F# ecosystem contains a range of type providers for commonly used Internet and enterprise data services.</span></span> <span data-ttu-id="4efb9-109">Exemple :</span><span class="sxs-lookup"><span data-stu-id="4efb9-109">For example:</span></span>

- <span data-ttu-id="4efb9-110">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) inclut les fournisseurs de type pour les formats de document JSON, XML, CSV et HTML.</span><span class="sxs-lookup"><span data-stu-id="4efb9-110">[FSharp.Data](https://fsharp.github.io/FSharp.Data/) includes type providers for JSON, XML, CSV and HTML document formats.</span></span>

- <span data-ttu-id="4efb9-111">[SQLProvider](https://fsprojects.github.io/SQLProvider/) fournit un accès fortement typé aux bases de données SQL et un mappage d’objet LINQ F # de requêtes par rapport à ces sources de données.</span><span class="sxs-lookup"><span data-stu-id="4efb9-111">[SQLProvider](https://fsprojects.github.io/SQLProvider/) provides strongly-typed access to SQL databases through a object mapping and F# LINQ queries against these data sources.</span></span>

- <span data-ttu-id="4efb9-112">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) a un ensemble de fournisseurs de type pour le moment de la compilation vérifié l’incorporation de T-SQL en F #.</span><span class="sxs-lookup"><span data-stu-id="4efb9-112">[FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) has a set of type providers for compile-time checked embedding of T-SQL in F#.</span></span>

- <span data-ttu-id="4efb9-113">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) est un ancien ensemble de fournisseurs de type pour une utilisation uniquement avec la programmation .NET Framework pour accéder aux services de données SQL, Entity Framework, OData et WSDL.</span><span class="sxs-lookup"><span data-stu-id="4efb9-113">[FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) is an older set of type providers for use only with .NET Framework programming for accessing SQL, Entity Framework, OData and WSDL data services.</span></span>

<span data-ttu-id="4efb9-114">Le cas échéant, vous pouvez créer des fournisseurs de type personnalisé, ou vous pouvez référencer des fournisseurs de type qu’ils ont créés.</span><span class="sxs-lookup"><span data-stu-id="4efb9-114">Where necessary, you can create custom type providers, or you can reference type providers that others have created.</span></span> <span data-ttu-id="4efb9-115">Par exemple, votre organisation peut avoir un service de données qui fournit un nombre important et croissant de jeux de données nommés, chacun avec son propre schéma stable de données.</span><span class="sxs-lookup"><span data-stu-id="4efb9-115">For example, your organization could have a data service that provides a large and growing number of named data sets, each with its own stable data schema.</span></span> <span data-ttu-id="4efb9-116">Vous pouvez créer un fournisseur de type qui lit les schémas et présente les jeux de données en cours au programmeur de manière fortement typée.</span><span class="sxs-lookup"><span data-stu-id="4efb9-116">You can create a type provider that reads the schemas and presents the current data sets to the programmer in a strongly typed way.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="4efb9-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4efb9-117">Before You Start</span></span>

<span data-ttu-id="4efb9-118">Le mécanisme de fournisseur de type est principalement conçu pour injecter des données stables et informations de service dans l’expérience de programmation F #.</span><span class="sxs-lookup"><span data-stu-id="4efb9-118">The type provider mechanism is primarily designed for injecting stable data and service information spaces into the F# programming experience.</span></span>

<span data-ttu-id="4efb9-119">Ce mécanisme n’est pas conçu pour injecter des espaces d’informations dont le schéma est modifiée au cours de l’exécution du programme avec des méthodes qui sont pertinents pour la logique du programme.</span><span class="sxs-lookup"><span data-stu-id="4efb9-119">This mechanism isn’t designed for injecting information spaces whose schema changes during program execution in ways that are relevant to program logic.</span></span> <span data-ttu-id="4efb9-120">En outre, le mécanisme n’est pas conçu pour intra-langage de programmation méta, bien que ce domaine contient certaines utilisations valides.</span><span class="sxs-lookup"><span data-stu-id="4efb9-120">Also, the mechanism isn't designed for intra-language meta-programming, even though that domain contains some valid uses.</span></span> <span data-ttu-id="4efb9-121">Vous devez utiliser ce mécanisme uniquement si nécessaire et où le développement d’un fournisseur de type génère une valeur très élevée.</span><span class="sxs-lookup"><span data-stu-id="4efb9-121">You should use this mechanism only where necessary and where the development of a type provider yields very high value.</span></span>

<span data-ttu-id="4efb9-122">Vous devez éviter d’écrire un fournisseur de type où un schéma n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="4efb9-122">You should avoid writing a type provider where a schema isn't available.</span></span> <span data-ttu-id="4efb9-123">De même, vous devez éviter d’écrire un fournisseur de type où un ordinaires (ou même un existant) bibliothèque .NET suffirait.</span><span class="sxs-lookup"><span data-stu-id="4efb9-123">Likewise, you should avoid writing a type provider where an ordinary (or even an existing) .NET library would suffice.</span></span>

<span data-ttu-id="4efb9-124">Avant de commencer, vous pouvez poser les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="4efb9-124">Before you start, you might ask the following questions:</span></span>

- <span data-ttu-id="4efb9-125">Vous avez un schéma pour la source d’informations ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-125">Do you have a schema for your information source?</span></span> <span data-ttu-id="4efb9-126">Dans ce cas, ce qui est le mappage dans le système de type .NET et F # ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-126">If so, what’s the mapping into the F# and .NET type system?</span></span>

- <span data-ttu-id="4efb9-127">Pouvez-vous utiliser une API (typée dynamiquement) existante comme point de départ pour votre implémentation ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-127">Can you use an existing (dynamically typed) API as a starting point for your implementation?</span></span>

- <span data-ttu-id="4efb9-128">Vous et votre organisation aura suffisamment utilise du fournisseur de type pour rendre l’écrire utile ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-128">Will you and your organization have enough uses of the type provider to make writing it worthwhile?</span></span> <span data-ttu-id="4efb9-129">Une bibliothèque .NET normale serait répondent à vos besoins ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-129">Would a normal .NET library meet your needs?</span></span>

- <span data-ttu-id="4efb9-130">Combien modifiera votre schéma ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-130">How much will your schema change?</span></span>

- <span data-ttu-id="4efb9-131">Passe au cours de codage ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-131">Will it change during coding?</span></span>

- <span data-ttu-id="4efb9-132">Il modifié entre les sessions de codage ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-132">Will it change between coding sessions?</span></span>

- <span data-ttu-id="4efb9-133">Il est modifié pendant l’exécution du programme ?</span><span class="sxs-lookup"><span data-stu-id="4efb9-133">Will it change during program execution?</span></span>

<span data-ttu-id="4efb9-134">Fournisseurs de type sont mieux adaptées aux situations où le schéma est stable lors de l’exécution et pendant la durée de vie du code compilé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-134">Type providers are best suited to situations where the schema is stable at runtime and during the lifetime of compiled code.</span></span>


## <a name="a-simple-type-provider"></a><span data-ttu-id="4efb9-135">Un fournisseur de Type Simple</span><span class="sxs-lookup"><span data-stu-id="4efb9-135">A Simple Type Provider</span></span>

<span data-ttu-id="4efb9-136">Cet exemple est Samples.HelloWorldTypeProvider, similaires aux exemples dans le `examples` répertoire de la [SDK de fournisseur de Type F #](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span><span class="sxs-lookup"><span data-stu-id="4efb9-136">This sample is Samples.HelloWorldTypeProvider, similar to the samples in the `examples` directory of the [F# Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/).</span></span> <span data-ttu-id="4efb9-137">Le fournisseur met à disposition un « espace de type » qui contient les types d’effacées 100, comme le montre le code suivant à l’aide de syntaxe de signature F # et en omettant les détails pour tous sauf `Type1`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-137">The provider makes available a "type space" that contains 100 erased types, as the following code shows by using F# signature syntax and omitting the details for all except `Type1`.</span></span> <span data-ttu-id="4efb9-138">Pour plus d’informations sur les types effacées, consultez [plus d’informations sur effacées fourni Types](#details-about-erased-provided-types) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4efb9-138">For more information about erased types, see [Details About Erased Provided Types](#details-about-erased-provided-types) later in this topic.</span></span>

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    /// This is an instance property.
    nested type NestedType = 
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

<span data-ttu-id="4efb9-139">Notez que l’ensemble des types et membres fournis est statiquement connu.</span><span class="sxs-lookup"><span data-stu-id="4efb9-139">Note that the set of types and members provided is statically known.</span></span> <span data-ttu-id="4efb9-140">Cet exemple ne tirent parti de la capacité de fournisseurs pour fournir des types qui dépendent d’un schéma.</span><span class="sxs-lookup"><span data-stu-id="4efb9-140">This example doesn't leverage the ability of providers to provide types that depend on a schema.</span></span> <span data-ttu-id="4efb9-141">L’implémentation du fournisseur de type est décrite dans le code suivant, et les détails sont traités dans les sections suivantes de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4efb9-141">The implementation of the type provider is outlined in the following code, and the details are covered in later sections of this topic.</span></span>


>[!WARNING] 
<span data-ttu-id="4efb9-142">Il peut exister des différences entre ce code et les exemples en ligne.</span><span class="sxs-lookup"><span data-stu-id="4efb9-142">There may be differences between this code and the online samples.</span></span>

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this = 

  // Inheriting from this type provides implementations of ITypeProvider 
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) = 
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ] 

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>] 
do()
```

<span data-ttu-id="4efb9-143">Pour utiliser ce fournisseur, ouvrez une instance distincte de Visual Studio, créer un script F #, puis ajoutez une référence au fournisseur à partir de votre script à l’aide de #r comme le montre le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-143">To use this provider, open a separate instance of Visual Studio, create an F# script, and then add a reference to the provider from your script by using #r as the following code shows:</span></span>

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

<span data-ttu-id="4efb9-144">Recherchez ensuite les types sous la `Samples.HelloWorldTypeProvider` espace de noms généré par le fournisseur de type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-144">Then look for the types under the `Samples.HelloWorldTypeProvider` namespace that the type provider generated.</span></span>

<span data-ttu-id="4efb9-145">Avant de recompiler le fournisseur, assurez-vous que vous avez fermé toutes les instances de Visual Studio et F # Interactive qui sont à l’aide de la DLL du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4efb9-145">Before you recompile the provider, make sure that you have closed all instances of Visual Studio and F# Interactive that are using the provider DLL.</span></span> <span data-ttu-id="4efb9-146">Dans le cas contraire, une erreur de build se produit car la DLL de sortie est verrouillée.</span><span class="sxs-lookup"><span data-stu-id="4efb9-146">Otherwise, a build error will occur because the output DLL will be locked.</span></span>

<span data-ttu-id="4efb9-147">Pour déboguer ce fournisseur à l’aide des instructions print, rendre un script qui expose un problème avec le fournisseur, puis utilisez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-147">To debug this provider by using print statements, make a script that exposes a problem with the provider, and then use the following code:</span></span>

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="4efb9-148">Pour déboguer ce fournisseur à l’aide de Visual Studio, ouvrez l’invite de commandes Visual Studio avec des informations d’identification d’administration, puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4efb9-148">To debug this provider by using Visual Studio, open the Visual Studio command prompt with administrative credentials, and run the following command:</span></span>

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

<span data-ttu-id="4efb9-149">En guise d’alternative, ouvrez Visual Studio, ouvrez le menu Déboguer, choisissez `Debug/Attach to process…`et l’attacher à un autre `devenv` processus dans lequel vous modifiez votre script.</span><span class="sxs-lookup"><span data-stu-id="4efb9-149">As an alternative, open Visual Studio, open the Debug menu, choose `Debug/Attach to process…`, and attach to another `devenv` process where you’re editing your script.</span></span> <span data-ttu-id="4efb9-150">À l’aide de cette méthode, vous pouvez plus facilement cibler logique particulier dans le fournisseur de type en tapant interactivement des expressions dans la deuxième instance (avec complète d’IntelliSense et d’autres fonctionnalités).</span><span class="sxs-lookup"><span data-stu-id="4efb9-150">By using this method, you can more easily target particular logic in the type provider by interactively typing expressions into the second instance (with full IntelliSense and other features).</span></span>

<span data-ttu-id="4efb9-151">Vous pouvez désactiver uniquement mon Code de débogage pour mieux identifier les erreurs dans le code généré.</span><span class="sxs-lookup"><span data-stu-id="4efb9-151">You can disable Just My Code debugging to better identify errors in generated code.</span></span> <span data-ttu-id="4efb9-152">Pour plus d’informations sur la façon d’activer ou désactiver cette fonctionnalité, consultez [naviguer dans le Code avec le débogueur](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span><span class="sxs-lookup"><span data-stu-id="4efb9-152">For information about how to enable or disable this feature, see [Navigating through Code with the Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger).</span></span> <span data-ttu-id="4efb9-153">En outre, vous pouvez également définir des exceptions de première chance interception en ouvrant le `Debug` menu, puis en choisissant `Exceptions` ou en appuyant sur Ctrl + Alt + E pour ouvrir le `Exceptions` boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4efb9-153">Also, you can also set first-chance exception catching by opening the `Debug` menu and then choosing `Exceptions` or by choosing the Ctrl+Alt+E keys to open the `Exceptions` dialog box.</span></span> <span data-ttu-id="4efb9-154">Cette boîte de dialogue, sous `Common Language Runtime Exceptions`, sélectionnez le `Thrown` case à cocher.</span><span class="sxs-lookup"><span data-stu-id="4efb9-154">In that dialog box, under `Common Language Runtime Exceptions`, select the `Thrown` check box.</span></span>


### <a name="implementation-of-the-type-provider"></a><span data-ttu-id="4efb9-155">Implémentation du fournisseur de Type</span><span class="sxs-lookup"><span data-stu-id="4efb9-155">Implementation of the Type Provider</span></span>

<span data-ttu-id="4efb9-156">Cette section vous guide dans les sections principales de l’implémentation de fournisseur de type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-156">This section walks you through the principal sections of the type provider implementation.</span></span> <span data-ttu-id="4efb9-157">Tout d’abord, vous définissez le type pour le fournisseur de type personnalisé lui-même :</span><span class="sxs-lookup"><span data-stu-id="4efb9-157">First, you define the type for the custom type provider itself:</span></span>

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

<span data-ttu-id="4efb9-158">Ce type doit être public, et vous devez la marquer avec le [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) afin que le compilateur reconnaît le fournisseur de type lorsqu’un projet distinct de F # fait référence à l’assembly qui contient le type d’attribut.</span><span class="sxs-lookup"><span data-stu-id="4efb9-158">This type must be public, and you must mark it with the [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) attribute so that the compiler will recognize the type provider when a separate F# project references the assembly that contains the type.</span></span> <span data-ttu-id="4efb9-159">Le *config* paramètre est facultatif et, le cas échéant, contient des informations de configuration contextuelles pour l’instance de fournisseur de type créés par le compilateur F #.</span><span class="sxs-lookup"><span data-stu-id="4efb9-159">The *config* parameter is optional, and, if present, contains contextual configuration information for the type provider instance that the F# compiler creates.</span></span>

<span data-ttu-id="4efb9-160">Ensuite, vous implémentez le [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span><span class="sxs-lookup"><span data-stu-id="4efb9-160">Next, you implement the [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface.</span></span> <span data-ttu-id="4efb9-161">Dans ce cas, vous utilisez la `TypeProviderForNamespaces` type à partir de la `ProvidedTypes` API comme type de base.</span><span class="sxs-lookup"><span data-stu-id="4efb9-161">In this case, you use the `TypeProviderForNamespaces` type from the `ProvidedTypes` API as a base type.</span></span> <span data-ttu-id="4efb9-162">Ce type d’assistance peut fournir dynamiquement une collection finie d’autant d’espaces de noms, chacun d’eux contient directement un nombre fini de fixe, fournies dynamiquement des types.</span><span class="sxs-lookup"><span data-stu-id="4efb9-162">This helper type can provide a finite collection of eagerly provided namespaces, each of which directly contains a finite number of fixed, eagerly provided types.</span></span> <span data-ttu-id="4efb9-163">Dans ce contexte, le fournisseur *anticipé* génère des types, même s’ils ne sont pas nécessaires ou utilisés.</span><span class="sxs-lookup"><span data-stu-id="4efb9-163">In this context, the provider *eagerly* generates types even if they aren't needed or used.</span></span>

```fsharp
inherit TypeProviderForNamespaces(config)
```

<span data-ttu-id="4efb9-164">Ensuite, locales privés et des valeurs qui spécifient les types fournis dans l’espace de noms et trouver l’assembly de fournisseur de type lui-même.</span><span class="sxs-lookup"><span data-stu-id="4efb9-164">Next, define local private values that specify the namespace for the provided types, and find the type provider assembly itself.</span></span> <span data-ttu-id="4efb9-165">Cet assembly est utilisé ultérieurement comme type de parent logique des types fournis effacés.</span><span class="sxs-lookup"><span data-stu-id="4efb9-165">This assembly is used later as the logical parent type of the erased types that are provided.</span></span>

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

<span data-ttu-id="4efb9-166">Ensuite, créez une fonction pour fournir chacun des types Type1... Type100.</span><span class="sxs-lookup"><span data-stu-id="4efb9-166">Next, create a function to provide each of the types Type1…Type100.</span></span> <span data-ttu-id="4efb9-167">Cette fonction est expliquée plus en détail plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4efb9-167">This function is explained in more detail later in this topic.</span></span>

```fsharp
let makeOneProvidedType (n:int) = …
```

<span data-ttu-id="4efb9-168">Ensuite, générez les types fournis 100 :</span><span class="sxs-lookup"><span data-stu-id="4efb9-168">Next, generate the 100 provided types:</span></span>

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

<span data-ttu-id="4efb9-169">Ensuite, ajoutez les types comme un espace de noms fourni :</span><span class="sxs-lookup"><span data-stu-id="4efb9-169">Next, add the types as a provided namespace:</span></span>

```fsharp
do this.AddNamespace(namespaceName, types)
```

<span data-ttu-id="4efb9-170">Enfin, ajoutez un attribut d’assembly qui indique que vous créez un fournisseur de type DLL :</span><span class="sxs-lookup"><span data-stu-id="4efb9-170">Finally, add an assembly attribute that indicates that you are creating a type provider DLL:</span></span>

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a><span data-ttu-id="4efb9-171">En fournissant un Type et ses membres</span><span class="sxs-lookup"><span data-stu-id="4efb9-171">Providing One Type And Its Members</span></span>

<span data-ttu-id="4efb9-172">Le `makeOneProvidedType` fonction effectue le travail de fournir un des types.</span><span class="sxs-lookup"><span data-stu-id="4efb9-172">The `makeOneProvidedType` function does the real work of providing one of the types.</span></span>

```fsharp
let makeOneProvidedType (n:int) = 
…
```

<span data-ttu-id="4efb9-173">Cette étape explique l’implémentation de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="4efb9-173">This step explains the implementation of this function.</span></span> <span data-ttu-id="4efb9-174">Commencez par créer le type fourni (par exemple, Type1, lorsque n = 1 ou Type57, lorsque n = 57).</span><span class="sxs-lookup"><span data-stu-id="4efb9-174">First, create the provided type (for example, Type1, when n = 1, or Type57, when n = 57).</span></span>

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

<span data-ttu-id="4efb9-175">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="4efb9-175">You should note the following points:</span></span>

- <span data-ttu-id="4efb9-176">Cette fournie de type est effacé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-176">This provided type is erased.</span></span>  <span data-ttu-id="4efb9-177">Vous indique que le type de base est `obj`, instances seront affiche sous forme de valeurs de type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) dans le code compilé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-177">Because you indicate that the base type is `obj`, instances will appear as values of type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) in compiled code.</span></span>

- <span data-ttu-id="4efb9-178">Lorsque vous spécifiez un type non imbriqué, vous devez spécifier l’assembly et l’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="4efb9-178">When you specify a non-nested type, you must specify the assembly and namespace.</span></span> <span data-ttu-id="4efb9-179">Pour les types effacées, l’assembly doit être l’assembly de fournisseur de type lui-même.</span><span class="sxs-lookup"><span data-stu-id="4efb9-179">For erased types, the assembly should be the type provider assembly itself.</span></span>

<span data-ttu-id="4efb9-180">Ensuite, ajoutez la documentation XML pour le type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-180">Next, add XML documentation to the type.</span></span> <span data-ttu-id="4efb9-181">Cette documentation est retardée, autrement dit, calculée à la demande, si le compilateur hôte en a besoin.</span><span class="sxs-lookup"><span data-stu-id="4efb9-181">This documentation is delayed, that is, computed on-demand if the host compiler needs it.</span></span>

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

<span data-ttu-id="4efb9-182">Ensuite, vous ajoutez une propriété statique fournie pour le type de :</span><span class="sxs-lookup"><span data-stu-id="4efb9-182">Next you add a provided static property to the type:</span></span>

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
                                  propertyType = typeof<string>, 
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

<span data-ttu-id="4efb9-183">L’obtention de cette propriété sera toujours évaluée à la chaîne « Hello ! ».</span><span class="sxs-lookup"><span data-stu-id="4efb9-183">Getting this property will always evaluate to the string "Hello!".</span></span> <span data-ttu-id="4efb9-184">Le `GetterCode` pour la propriété utilise un devis F #, qui représente le code générés par le compilateur hôte pour l’obtention de la propriété.</span><span class="sxs-lookup"><span data-stu-id="4efb9-184">The `GetterCode` for the property uses an F# quotation, which represents the code that the host compiler generates for getting the property.</span></span> <span data-ttu-id="4efb9-185">Pour plus d’informations sur les propositions de prix, consultez [Quotations de Code (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span><span class="sxs-lookup"><span data-stu-id="4efb9-185">For more information about quotations, see [Code Quotations (F#)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).</span></span>

<span data-ttu-id="4efb9-186">Ajouter la documentation XML à la propriété.</span><span class="sxs-lookup"><span data-stu-id="4efb9-186">Add XML documentation to the property.</span></span>

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

<span data-ttu-id="4efb9-187">Le type fourni désormais joindre la propriété fournie.</span><span class="sxs-lookup"><span data-stu-id="4efb9-187">Now attach the provided property to the provided type.</span></span> <span data-ttu-id="4efb9-188">Vous devez associer un membre fourni à un seul et unique type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-188">You must attach a provided member to one and only one type.</span></span> <span data-ttu-id="4efb9-189">Dans le cas contraire, le membre ne sera jamais accessible.</span><span class="sxs-lookup"><span data-stu-id="4efb9-189">Otherwise, the member will never be accessible.</span></span>

```fsharp
t.AddMember staticProp
```

<span data-ttu-id="4efb9-190">Maintenant créer un constructeur fourni qui ne prend aucun paramètre.</span><span class="sxs-lookup"><span data-stu-id="4efb9-190">Now create a provided constructor that takes no parameters.</span></span>

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

<span data-ttu-id="4efb9-191">Le `InvokeCode` pour le constructeur retourne une citation F #, qui représente le code que le compilateur hôte génère lorsque le constructeur est appelé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-191">The `InvokeCode` for the constructor returns an F# quotation, which represents the code that the host compiler generates when the constructor is called.</span></span> <span data-ttu-id="4efb9-192">Par exemple, vous pouvez utiliser le constructeur suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-192">For example, you can use the following constructor:</span></span>

```fsharp
new Type10()
```

<span data-ttu-id="4efb9-193">Une instance du type fourni sera créée avec les données sous-jacentes « Les données d’objet ».</span><span class="sxs-lookup"><span data-stu-id="4efb9-193">An instance of the provided type will be created with underlying data "The object data".</span></span> <span data-ttu-id="4efb9-194">Le code entre guillemets inclut une conversion vers [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) , car ce type est la suppression de ce le type fourni (que vous avez spécifié lorsque vous avez déclaré le type fourni).</span><span class="sxs-lookup"><span data-stu-id="4efb9-194">The quoted code includes a conversion to [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) because that type is the erasure of this provided type (as you specified when you declared the provided type).</span></span>

<span data-ttu-id="4efb9-195">Ajouter la documentation XML pour le constructeur et ajoutez le constructeur fourni pour le type fourni :</span><span class="sxs-lookup"><span data-stu-id="4efb9-195">Add XML documentation to the constructor, and add the provided constructor to the provided type:</span></span>

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

<span data-ttu-id="4efb9-196">Créer un deuxième constructeur fourni qui prend un paramètre :</span><span class="sxs-lookup"><span data-stu-id="4efb9-196">Create a second provided constructor that takes one parameter:</span></span>

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

<span data-ttu-id="4efb9-197">Le `InvokeCode` pour le constructeur retourne à nouveau un devis F #, qui représente le code généré par le compilateur hôte pour un appel à la méthode.</span><span class="sxs-lookup"><span data-stu-id="4efb9-197">The `InvokeCode` for the constructor again returns an F# quotation, which represents the code that the host compiler generated for a call to the method.</span></span> <span data-ttu-id="4efb9-198">Par exemple, vous pouvez utiliser le constructeur suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-198">For example, you can use the following constructor:</span></span>

```fsharp
new Type10("ten")
```

<span data-ttu-id="4efb9-199">Une instance du type fourni est créée avec les données sous-jacentes « 10 ».</span><span class="sxs-lookup"><span data-stu-id="4efb9-199">An instance of the provided type is created with underlying data "ten".</span></span> <span data-ttu-id="4efb9-200">Vous avez peut-être déjà remarqué que le `InvokeCode` fonction retourne une citation.</span><span class="sxs-lookup"><span data-stu-id="4efb9-200">You may have already noticed that the `InvokeCode` function returns a quotation.</span></span> <span data-ttu-id="4efb9-201">L’entrée de cette fonction est une liste d’expressions, un par un paramètre de constructeur.</span><span class="sxs-lookup"><span data-stu-id="4efb9-201">The input to this function is a list of expressions, one per constructor parameter.</span></span> <span data-ttu-id="4efb9-202">Dans ce cas, une expression qui représente la valeur de paramètre est disponible dans `args.[0]`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-202">In this case, an expression that represents the single parameter value is available in `args.[0]`.</span></span> <span data-ttu-id="4efb9-203">Le code d’un appel au constructeur force la valeur de retournée dans le type effacée `obj`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-203">The code for a call to the constructor coerces the return value to the erased type `obj`.</span></span> <span data-ttu-id="4efb9-204">Après avoir ajouté le deuxième constructeur fourni pour le type, vous créez une propriété d’instance fourni :</span><span class="sxs-lookup"><span data-stu-id="4efb9-204">After you add the second provided constructor to the type, you create a provided instance property:</span></span>

```fsharp
let instanceProp = 
    ProvidedProperty(propertyName = "InstanceProperty", 
                     propertyType = typeof<int>, 
                     getterCode= (fun args -> 
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

<span data-ttu-id="4efb9-205">L’obtention de cette propriété retourne la longueur de la chaîne, qui est l’objet de la représentation.</span><span class="sxs-lookup"><span data-stu-id="4efb9-205">Getting this property will return the length of the string, which is the representation object.</span></span> <span data-ttu-id="4efb9-206">Le `GetterCode` propriété retourne une citation F # qui spécifie le code que le compilateur hôte génère pour obtenir la propriété.</span><span class="sxs-lookup"><span data-stu-id="4efb9-206">The `GetterCode` property returns an F# quotation that specifies the code that the host compiler generates to get the property.</span></span> <span data-ttu-id="4efb9-207">Comme `InvokeCode`, le `GetterCode` fonction retourne une citation.</span><span class="sxs-lookup"><span data-stu-id="4efb9-207">Like `InvokeCode`, the `GetterCode` function returns a quotation.</span></span> <span data-ttu-id="4efb9-208">Le compilateur hôte appelle cette fonction avec une liste d’arguments.</span><span class="sxs-lookup"><span data-stu-id="4efb9-208">The host compiler calls this function with a list of arguments.</span></span> <span data-ttu-id="4efb9-209">Dans ce cas, les arguments sont simplement l’expression unique qui représente l’instance sur laquelle l’accesseur Get est appelée, auquel vous pouvez accéder à l’aide de `args.[0]`. L’implémentation de `GetterCode` puis jonctions de fil dans la soumission du résultat du type effacées `obj`, et un cast est utilisé pour satisfaire le mécanisme du compilateur pour la vérification des types que l’objet est une chaîne.</span><span class="sxs-lookup"><span data-stu-id="4efb9-209">In this case, the arguments include just the single expression that represents the instance upon which the getter is being called, which you can access by using `args.[0]`.The implementation of `GetterCode` then splices into the result quotation at the erased type `obj`, and a cast is used to satisfy the compiler's mechanism for checking types that the object is a string.</span></span> <span data-ttu-id="4efb9-210">La partie suivante de `makeOneProvidedType` fournit une méthode d’instance avec un paramètre.</span><span class="sxs-lookup"><span data-stu-id="4efb9-210">The next part of `makeOneProvidedType` provides an instance method with one parameter.</span></span>

```fsharp
let instanceMeth = 
    ProvidedMethod(methodName = "InstanceMethod", 
                   parameters = [ProvidedParameter("x",typeof<int>)], 
                   returnType = typeof<char>, 
                   invokeCode = (fun args -> 
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

<span data-ttu-id="4efb9-211">Enfin, créez un type imbriqué qui contient les propriétés imbriquées 100.</span><span class="sxs-lookup"><span data-stu-id="4efb9-211">Finally, create a nested type that contains 100 nested properties.</span></span> <span data-ttu-id="4efb9-212">Imbriqué de la création de ce type et ses propriétés est retardé, autrement dit, calculée à la demande.</span><span class="sxs-lookup"><span data-stu-id="4efb9-212">The creation of this nested type and its properties is delayed, that is, computed on-demand.</span></span>

```fsharp
t.AddMembersDelayed(fun () -> 
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () -> 
    let staticPropsInNestedType = 
      [ for i in 1 .. 100 do
          let valueOfTheProperty = "I am string "  + string i

          let p = 
            ProvidedProperty(propertyName = "StaticProperty" + string i, 
              propertyType = typeof<string>, 
              isStatic = true,
              getterCode= (fun args -> <@@ valueOfTheProperty @@>))

          p.AddXmlDocDelayed(fun () -> 
              sprintf "This is StaticProperty%d on NestedType" i)

          yield p ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a><span data-ttu-id="4efb9-213">Pour plus d’informations sur les Types fournis effacés</span><span class="sxs-lookup"><span data-stu-id="4efb9-213">Details about Erased Provided Types</span></span>

<span data-ttu-id="4efb9-214">L’exemple de cette section fournit uniquement *effacées des types fournis*, qui sont particulièrement utile dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4efb9-214">The example in this section provides only *erased provided types*, which are particularly useful in the following situations:</span></span>

- <span data-ttu-id="4efb9-215">Lorsque vous écrivez un fournisseur pour un espace d’informations qui contient uniquement les données et les méthodes.</span><span class="sxs-lookup"><span data-stu-id="4efb9-215">When you are writing a provider for an information space that contains only data and methods.</span></span>

- <span data-ttu-id="4efb9-216">Lorsque vous écrivez un fournisseur où précis runtime une sémantique de type ne sont pas critique pour l’utilisation pratique de l’espace d’informations.</span><span class="sxs-lookup"><span data-stu-id="4efb9-216">When you are writing a provider where accurate runtime-type semantics aren't critical for practical use of the information space.</span></span>

- <span data-ttu-id="4efb9-217">Lorsque vous écrivez un fournisseur pour un espace d’informations est trop volumineuse et interconnectés qu’il soit techniquement possible de générer des types .NET réels pour l’espace d’informations.</span><span class="sxs-lookup"><span data-stu-id="4efb9-217">When you are writing a provider for an information space that is so large and interconnected that it isn’t technically feasible to generate real .NET types for the information space.</span></span>

<span data-ttu-id="4efb9-218">Dans cet exemple, chaque fournie type est effacé en type `obj`, et toutes les utilisations du type seront affiche en tant que type `obj` dans le code compilé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-218">In this example, each provided type is erased to type `obj`, and all uses of the type will appear as type `obj` in compiled code.</span></span> <span data-ttu-id="4efb9-219">En fait, les objets sous-jacents dans ces exemples sont des chaînes, mais le type apparaîtra comme `System.Object` dans .NET code compilé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-219">In fact, the underlying objects in these examples are strings, but the type will appear as `System.Object` in .NET compiled code.</span></span> <span data-ttu-id="4efb9-220">Comme avec toutes les utilisations d’effacement de type, vous pouvez utiliser la conversion boxing explicite, unboxing et de la conversion de compromettre l’effacées types.</span><span class="sxs-lookup"><span data-stu-id="4efb9-220">As with all uses of type erasure, you can use explicit boxing, unboxing, and casting to subvert erased types.</span></span> <span data-ttu-id="4efb9-221">Dans ce cas, une exception cast non valide peut entraîner lorsque l’objet est utilisé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-221">In this case, a cast exception that isn’t valid may result when the object is used.</span></span> <span data-ttu-id="4efb9-222">Un fournisseur runtime peut définir son propre type de représentation privé pour vous protéger contre les représentations sous forme de valeur est false.</span><span class="sxs-lookup"><span data-stu-id="4efb9-222">A provider runtime can define its own private representation type to help protect against false representations.</span></span> <span data-ttu-id="4efb9-223">Impossible de définir des types effacées en F # lui-même.</span><span class="sxs-lookup"><span data-stu-id="4efb9-223">You can’t define erased types in F# itself.</span></span> <span data-ttu-id="4efb9-224">Seuls les types fournis peuvent être effacées.</span><span class="sxs-lookup"><span data-stu-id="4efb9-224">Only provided types may be erased.</span></span> <span data-ttu-id="4efb9-225">Vous devez comprendre les ramifications, à la fois pratique et sémantique de l’aide des types effacées de votre fournisseur de type ou d’un fournisseur qui fournit effacées types.</span><span class="sxs-lookup"><span data-stu-id="4efb9-225">You must understand the ramifications, both practical and semantic, of using either erased types for your type provider or a provider that provides erased types.</span></span> <span data-ttu-id="4efb9-226">Un type effacé n’a aucune véritable type .NET.</span><span class="sxs-lookup"><span data-stu-id="4efb9-226">An erased type has no real .NET type.</span></span> <span data-ttu-id="4efb9-227">Par conséquent, vous ne pouvez pas faire précise sur le type, et vous pourrez compromettre types effacées si vous utilisez des casts de runtime et d’autres techniques qui s’appuient sur la sémantique de type exacte du runtime.</span><span class="sxs-lookup"><span data-stu-id="4efb9-227">Therefore, you cannot do accurate reflection over the type, and you might subvert erased types if you use runtime casts and other techniques that rely on exact runtime type semantics.</span></span> <span data-ttu-id="4efb9-228">Subversion de types effacées entraîne souvent des exceptions de cast de type lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="4efb9-228">Subversion of erased types frequently results in type cast exceptions at runtime.</span></span>


### <a name="choosing-representations-for-erased-provided-types"></a><span data-ttu-id="4efb9-229">Choix des représentations pour effacer fourni Types</span><span class="sxs-lookup"><span data-stu-id="4efb9-229">Choosing Representations for Erased Provided Types</span></span>

<span data-ttu-id="4efb9-230">Pour certaines utilisations des types fournis effacés, aucune représentation n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4efb9-230">For some uses of erased provided types, no representation is required.</span></span> <span data-ttu-id="4efb9-231">Par exemple, l’effacées fourni type peut contenir uniquement des propriétés statiques et des membres et aucun constructeur, et aucune méthode ou propriété ne retourne une instance du type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-231">For example, the erased provided type might contain only static properties and members and no constructors, and no methods or properties would return an instance of the type.</span></span> <span data-ttu-id="4efb9-232">Si vous pouvez joindre des instances d’un élément effacé le type fourni, vous devez prendre en compte les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="4efb9-232">If you can reach instances of an erased provided type, you must consider the following questions:</span></span>

<span data-ttu-id="4efb9-233">**Quelle est la suppression d’un type fourni ?**</span><span class="sxs-lookup"><span data-stu-id="4efb9-233">**What is the erasure of a provided type?**</span></span>

- <span data-ttu-id="4efb9-234">L’effacement d’un type fourni est la façon dont le type s’affiche dans le code .NET compilé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-234">The erasure of a provided type is how the type appears in compiled .NET code.</span></span>

- <span data-ttu-id="4efb9-235">L’effacement d’un type de classe effacées fourni est toujours le premier non effacé type de base dans la chaîne d’héritage du type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-235">The erasure of a provided erased class type is always the first non-erased base type in the inheritance chain of the type.</span></span>

- <span data-ttu-id="4efb9-236">L’effacement d’un type interface effacées fournie est toujours `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-236">The erasure of a provided erased interface type is always `System.Object`.</span></span>

<span data-ttu-id="4efb9-237">**Quelles sont les représentations sous forme d’un type fourni ?**</span><span class="sxs-lookup"><span data-stu-id="4efb9-237">**What are the representations of a provided type?**</span></span>

- <span data-ttu-id="4efb9-238">Le jeu d’objets possible pour un type fourni effacé sont appelés ses représentations.</span><span class="sxs-lookup"><span data-stu-id="4efb9-238">The set of possible objects for an erased provided type are called its representations.</span></span> <span data-ttu-id="4efb9-239">Dans l’exemple dans ce document, les représentations sous forme de tous les fourni l’effacées types `Type1..Type100` sont toujours des objets de chaîne.</span><span class="sxs-lookup"><span data-stu-id="4efb9-239">In the example in this document, the representations of all the erased provided types `Type1..Type100` are always string objects.</span></span>

<span data-ttu-id="4efb9-240">Toutes les représentations sous forme d’un type fourni doit être compatible avec l’effacement du type fourni.</span><span class="sxs-lookup"><span data-stu-id="4efb9-240">All representations of a provided type must be compatible with the erasure of the provided type.</span></span> <span data-ttu-id="4efb9-241">(Dans le cas contraire, le compilateur F # génère une erreur pour une utilisation du fournisseur de type, ou du code non vérifiable .NET qui n’est pas valide est généré.</span><span class="sxs-lookup"><span data-stu-id="4efb9-241">(Otherwise, either the F# compiler will give an error for a use of the type provider, or unverifiable .NET code that isn't valid will be generated.</span></span> <span data-ttu-id="4efb9-242">Un fournisseur de type n’est pas valide si elle retourne le code qui donne une représentation qui n’est pas valide.)</span><span class="sxs-lookup"><span data-stu-id="4efb9-242">A type provider isn’t valid if it returns code that gives a  representation that isn't valid.)</span></span>

<span data-ttu-id="4efb9-243">Vous pouvez choisir une représentation pour les objets fournis à l’aide d’une des méthodes suivantes, qui sont très courantes :</span><span class="sxs-lookup"><span data-stu-id="4efb9-243">You can choose a representation for provided objects by using either of the following approaches, both of which are very common:</span></span>

- <span data-ttu-id="4efb9-244">Si vous fournissez simplement un wrapper fortement typé sur un type .NET existant, il est souvent logique pour votre type effacer à ce type, utilisez des instances de ce type en tant que représentations, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="4efb9-244">If you're simply providing a strongly typed wrapper over an existing .NET type, it often makes sense for your type to erase to that type, use instances of that type as representations, or both.</span></span> <span data-ttu-id="4efb9-245">Cette approche est appropriée lorsque la plupart des méthodes existantes de ce type sont toujours judicieux lors de l’utilisation de la version fortement typée.</span><span class="sxs-lookup"><span data-stu-id="4efb9-245">This approach is appropriate when most of the existing methods on that type still make sense when using the strongly typed version.</span></span>

- <span data-ttu-id="4efb9-246">Si vous souhaitez créer une API qui diffère considérablement de toute API .NET existant, il est judicieux de créer des types de runtime qui seront l’effacement de type et les représentations sous forme de types fournis.</span><span class="sxs-lookup"><span data-stu-id="4efb9-246">If you want to create an API that differs significantly from any existing .NET API, it makes sense to create runtime types that will be the type erasure and representations for the provided types.</span></span>

<span data-ttu-id="4efb9-247">L’exemple dans ce document utilise des chaînes en tant que représentations d’objets fournis.</span><span class="sxs-lookup"><span data-stu-id="4efb9-247">The example in this document uses strings as representations of provided objects.</span></span> <span data-ttu-id="4efb9-248">Souvent, il peut être approprié d’utiliser d’autres objets pour les représentations.</span><span class="sxs-lookup"><span data-stu-id="4efb9-248">Frequently, it may be appropriate to use other objects for representations.</span></span> <span data-ttu-id="4efb9-249">Par exemple, vous pouvez utiliser un dictionnaire en tant qu’un jeu de propriétés :</span><span class="sxs-lookup"><span data-stu-id="4efb9-249">For example, you may use a dictionary as a property bag:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

<span data-ttu-id="4efb9-250">En guise d’alternative, vous pouvez définir un type dans votre fournisseur de type qui sera utilisé lors de l’exécution pour former la représentation, ainsi que d’un ou plusieurs opérations d’exécution :</span><span class="sxs-lookup"><span data-stu-id="4efb9-250">As an alternative, you may define a type in your type provider that will be used at runtime to form the representation, along with one or more runtime operations:</span></span>

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

<span data-ttu-id="4efb9-251">Membres fournis peuvent ensuite construire des instances de ce type d’objet :</span><span class="sxs-lookup"><span data-stu-id="4efb9-251">Provided members can then construct instances of this object type:</span></span>

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

<span data-ttu-id="4efb9-252">Dans ce cas, vous pouvez utiliser (facultatif) ce type en tant que l’effacement de type en spécifiant ce type comme le `baseType` lors de la construction du `ProvidedTypeDefinition`:</span><span class="sxs-lookup"><span data-stu-id="4efb9-252">In this case, you may (optionally) use this type as the type erasure by specifying this type as the `baseType` when constructing the `ProvidedTypeDefinition`:</span></span>

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a><span data-ttu-id="4efb9-253">Leçons clés</span><span class="sxs-lookup"><span data-stu-id="4efb9-253">Key Lessons</span></span>

<span data-ttu-id="4efb9-254">La section précédente décrit comment créer un fournisseur de type effacement simple qui fournit une gamme de types, propriétés et méthodes.</span><span class="sxs-lookup"><span data-stu-id="4efb9-254">The previous section explained how to create a simple erasing type provider that provides a range of types, properties, and methods.</span></span> <span data-ttu-id="4efb9-255">Également, cette section explique le concept d’effacement de type, y compris des avantages et les inconvénients de fournir des types effacées à partir d’un fournisseur de type et décrit les représentations sous forme de types effacées.</span><span class="sxs-lookup"><span data-stu-id="4efb9-255">This section also explained the concept of type erasure, including some of the advantages and disadvantages of providing erased types from a type provider, and discussed representations of erased types.</span></span>


## <a name="a-type-provider-that-uses-static-parameters"></a><span data-ttu-id="4efb9-256">Un fournisseur de Type qui utilise les paramètres statiques</span><span class="sxs-lookup"><span data-stu-id="4efb9-256">A Type Provider That Uses Static Parameters</span></span>

<span data-ttu-id="4efb9-257">La possibilité de paramétrer des fournisseurs de type en données statiques autorise de nombreux scénarios intéressants, même dans les cas où le fournisseur n’a pas besoin accéder aux données locales ou distantes.</span><span class="sxs-lookup"><span data-stu-id="4efb9-257">The ability to parameterize type providers by static data enables many interesting scenarios, even in cases when the provider doesn't need to access any local or remote data.</span></span> <span data-ttu-id="4efb9-258">Dans cette section, vous allez apprendre quelques techniques de base pour assembler un tel fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4efb9-258">In this section, you’ll learn some basic techniques for putting together such a provider.</span></span>


### <a name="type-checked-regex-provider"></a><span data-ttu-id="4efb9-259">Type contrôlé Regex fournisseur</span><span class="sxs-lookup"><span data-stu-id="4efb9-259">Type Checked Regex Provider</span></span>

<span data-ttu-id="4efb9-260">Imaginez que vous souhaitez implémenter un fournisseur de type pour les expressions régulières qui encapsule le .NET <xref:System.Text.RegularExpressions.Regex> bibliothèques dans une interface qui fournit des garanties de compilation suivantes :</span><span class="sxs-lookup"><span data-stu-id="4efb9-260">Imagine that you want to implement a type provider for regular expressions that wraps the .NET <xref:System.Text.RegularExpressions.Regex> libraries in an interface that provides the following compile-time guarantees:</span></span>

- <span data-ttu-id="4efb9-261">Vérification d’une expression régulière valide.</span><span class="sxs-lookup"><span data-stu-id="4efb9-261">Verifying whether a regular expression is valid.</span></span>

- <span data-ttu-id="4efb9-262">Fournit des propriétés nommées de correspondances qui sont basées sur les noms de groupe dans l’expression régulière.</span><span class="sxs-lookup"><span data-stu-id="4efb9-262">Providing named properties on matches that are based on any group names in the regular expression.</span></span>

<span data-ttu-id="4efb9-263">Cette section vous montre comment utiliser des fournisseurs de type pour créer un `RegexTyped` de type que le modèle d’expression régulière est pour offrir ces avantages.</span><span class="sxs-lookup"><span data-stu-id="4efb9-263">This section shows you how to use type providers to create a `RegexTyped` type that the regular expression pattern parameterizes to provide these benefits.</span></span> <span data-ttu-id="4efb9-264">Le compilateur signale une erreur si le modèle fourni n’est pas valide, le fournisseur de type peut extraire les groupes à partir du modèle afin que vous pouvez y accéder à l’aide de ces propriétés sur les correspondances.</span><span class="sxs-lookup"><span data-stu-id="4efb9-264">The compiler will report an error if the supplied pattern isn't valid, and the type provider can extract the groups from the pattern so that you can access them by using named properties on matches.</span></span> <span data-ttu-id="4efb9-265">Lorsque vous concevez un fournisseur de type, vous devez envisager l’aspect de son API exposée aux utilisateurs finaux et comment cette conception se traduit en code .NET.</span><span class="sxs-lookup"><span data-stu-id="4efb9-265">When you design a type provider, you should consider how its exposed API should look to end users and how this design will translate to .NET code.</span></span> <span data-ttu-id="4efb9-266">L’exemple suivant montre comment utiliser une telle API pour obtenir les composants de l’indicatif :</span><span class="sxs-lookup"><span data-stu-id="4efb9-266">The following example shows how to use such an API to get the components of the area code:</span></span>

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

<span data-ttu-id="4efb9-267">L’exemple suivant montre comment le fournisseur de type convertit ces appels :</span><span class="sxs-lookup"><span data-stu-id="4efb9-267">The following example shows how the type provider translates these calls:</span></span>

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

<span data-ttu-id="4efb9-268">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="4efb9-268">Note the following points:</span></span>

- <span data-ttu-id="4efb9-269">Le type d’expression régulière standard représente paramétré `RegexTyped` type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-269">The standard Regex type represents the parameterized `RegexTyped` type.</span></span>

- <span data-ttu-id="4efb9-270">Le `RegexTyped` constructeur entraîne un appel au constructeur Regex, en passant l’argument de type statique pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="4efb9-270">The `RegexTyped` constructor results in a call to the Regex constructor, passing in the static type argument for the pattern.</span></span>

- <span data-ttu-id="4efb9-271">Les résultats de la `Match` méthode sont représentées par la norme <xref:System.Text.RegularExpressions.Match> type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-271">The results of the `Match` method are represented by the standard <xref:System.Text.RegularExpressions.Match> type.</span></span>

- <span data-ttu-id="4efb9-272">Chaque groupe nommé entraîne une propriété fournie, et l’accès à la propriété entraîne une utilisation d’un indexeur sur une correspondance `Groups` collection.</span><span class="sxs-lookup"><span data-stu-id="4efb9-272">Each named group results in a provided property, and accessing the property results in a use of an indexer on a match’s `Groups` collection.</span></span>

<span data-ttu-id="4efb9-273">Le code suivant est le cœur de la logique pour implémenter ce type de fournisseur, et cet exemple omet l’ajout de tous les membres pour le type fourni.</span><span class="sxs-lookup"><span data-stu-id="4efb9-273">The following code is the core of the logic to implement such a provider, and this example omits the addition of all members to the provided type.</span></span> <span data-ttu-id="4efb9-274">Pour plus d’informations sur chaque membre ajouté, consultez la section correspondante plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4efb9-274">For information about each added member, see the appropriate section later in this topic.</span></span> <span data-ttu-id="4efb9-275">Pour le code complet, téléchargez l’exemple à partir de la [F # 3.0 exemple Pack](https://fsharp3sample.codeplex.com) sur le site Web Codeplex.</span><span class="sxs-lookup"><span data-stu-id="4efb9-275">For the full code, download the sample from the [F# 3.0 Sample Pack](https://fsharp3sample.codeplex.com) on the Codeplex website.</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams, 
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with 
          | [| :? string as pattern|] -> 

            // Create an instance of the regular expression. 
            //
            // This will fail with System.ArgumentException if the regular expression is not valid. 
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)            

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty = 
              ProvidedTypeDefinition(
                thisAssembly, 
                rootNamespace, 
                typeName, 
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values")) 

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

<span data-ttu-id="4efb9-276">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="4efb9-276">Note the following points:</span></span>

- <span data-ttu-id="4efb9-277">Le fournisseur de type accepte deux paramètres statiques : le `pattern`, qui est obligatoire et le `options`, lesquels sont facultatifs (étant donné que la valeur par défaut est fournie).</span><span class="sxs-lookup"><span data-stu-id="4efb9-277">The type provider takes two static parameters: the `pattern`, which is mandatory, and the `options`, which are optional (because a default value is provided).</span></span>

- <span data-ttu-id="4efb9-278">Une fois les arguments statiques sont fournis, vous créez une instance de l’expression régulière.</span><span class="sxs-lookup"><span data-stu-id="4efb9-278">After the static arguments are supplied, you create an instance of the regular expression.</span></span> <span data-ttu-id="4efb9-279">Cette instance lève une exception si l’expression régulière est incorrect, et cette erreur ne sera signalée aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4efb9-279">This instance will throw an exception if the Regex is malformed, and this error will be reported to users.</span></span>

- <span data-ttu-id="4efb9-280">Dans la `DefineStaticParameters` rappel, vous définissez le type qui sera renvoyé après les arguments sont fournis.</span><span class="sxs-lookup"><span data-stu-id="4efb9-280">Within the `DefineStaticParameters` callback, you define the type that will be returned after the arguments are supplied.</span></span>

- <span data-ttu-id="4efb9-281">Ce code définit `HideObjectMethods` sur true afin que l’expérience IntelliSense restera simplifiée.</span><span class="sxs-lookup"><span data-stu-id="4efb9-281">This code sets `HideObjectMethods` to true so that the IntelliSense experience will remain streamlined.</span></span> <span data-ttu-id="4efb9-282">Cet attribut provoque la `Equals`, `GetHashCode`, `Finalize`, et `GetType` membres à supprimer dans les listes IntelliSense pour un objet fourni.</span><span class="sxs-lookup"><span data-stu-id="4efb9-282">This attribute causes the `Equals`, `GetHashCode`, `Finalize`, and `GetType` members to be suppressed from IntelliSense lists for a provided object.</span></span>

- <span data-ttu-id="4efb9-283">Vous utilisez `obj` comme type de base de la méthode, mais que vous allez utiliser un `Regex` objet en tant que la représentation sous forme de runtime de ce type, comme le montre l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="4efb9-283">You use `obj` as the base type of the method, but you’ll use a `Regex` object as the runtime representation of this type, as the next example shows.</span></span>

- <span data-ttu-id="4efb9-284">L’appel à la `Regex` constructeur lève une <xref:System.ArgumentException> quand une expression régulière n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="4efb9-284">The call to the `Regex` constructor throws a <xref:System.ArgumentException> when a regular expression isn’t valid.</span></span> <span data-ttu-id="4efb9-285">Le compilateur intercepte cette exception et signale un message d’erreur à l’utilisateur au moment de la compilation ou dans l’éditeur Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4efb9-285">The compiler catches this exception and reports an error message to the user at compile time or in the Visual Studio editor.</span></span> <span data-ttu-id="4efb9-286">Cette exception permet à des expressions régulières pour être validé sans exécution d’une application.</span><span class="sxs-lookup"><span data-stu-id="4efb9-286">This exception enables regular expressions to be validated without running an application.</span></span>

<span data-ttu-id="4efb9-287">Le type défini ci-dessus n’est pas utile encore, car il ne contient pas les méthodes explicites ou les propriétés.</span><span class="sxs-lookup"><span data-stu-id="4efb9-287">The type defined above isn't useful yet because it doesn’t contain any meaningful methods or properties.</span></span> <span data-ttu-id="4efb9-288">Tout d’abord, ajoutez un mappage statique `IsMatch` méthode :</span><span class="sxs-lookup"><span data-stu-id="4efb9-288">First, add a static `IsMatch` method:</span></span>

```fsharp
let isMatch = 
    ProvidedMethod(
        methodName = "IsMatch", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = typeof<bool>, 
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string." 
ty.AddMember isMatch
```

<span data-ttu-id="4efb9-289">Le code précédent définit une méthode `IsMatch`, qui prend une chaîne comme entrée et retourne un `bool`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-289">The previous code defines a method `IsMatch`, which takes a string as input and returns a `bool`.</span></span> <span data-ttu-id="4efb9-290">La seule difficulté consiste à utiliser le `args` argument dans le `InvokeCode` définition.</span><span class="sxs-lookup"><span data-stu-id="4efb9-290">The only tricky part is the use of the `args` argument within the `InvokeCode` definition.</span></span> <span data-ttu-id="4efb9-291">Dans cet exemple, `args` est une liste de soumissions qui représente les arguments de cette méthode.</span><span class="sxs-lookup"><span data-stu-id="4efb9-291">In this example, `args` is a list of quotations that represents the arguments to this method.</span></span> <span data-ttu-id="4efb9-292">Si la méthode est une méthode d’instance, le premier argument représente le `this` argument.</span><span class="sxs-lookup"><span data-stu-id="4efb9-292">If the method is an instance method, the first argument represents the `this` argument.</span></span> <span data-ttu-id="4efb9-293">Toutefois, pour une méthode statique, les arguments sont tout simplement des arguments explicites à la méthode.</span><span class="sxs-lookup"><span data-stu-id="4efb9-293">However, for a static method, the arguments are all just the explicit arguments to the method.</span></span> <span data-ttu-id="4efb9-294">Notez que le type de la valeur entre guillemets doit correspondre au type de retour spécifié (dans ce cas, `bool`).</span><span class="sxs-lookup"><span data-stu-id="4efb9-294">Note that the type of the quoted value should match the specified return type (in this case, `bool`).</span></span> <span data-ttu-id="4efb9-295">Notez également que ce code utilise le `AddXmlDoc` méthode pour s’assurer que la méthode fournie a également toute documentation utile, vous pouvez fournir via IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4efb9-295">Also note that this code uses the `AddXmlDoc` method to make sure that the provided method also has useful documentation, which you can supply through IntelliSense.</span></span>

<span data-ttu-id="4efb9-296">Ensuite, ajoutez une instance de méthode de correspondance.</span><span class="sxs-lookup"><span data-stu-id="4efb9-296">Next, add an instance Match method.</span></span> <span data-ttu-id="4efb9-297">Toutefois, cette méthode doit retourner une valeur d’un `Match` type afin que les groupes sont accessibles de manière fortement typée.</span><span class="sxs-lookup"><span data-stu-id="4efb9-297">However, this method should return a value of a provided `Match` type so that the groups can be accessed in a strongly typed fashion.</span></span> <span data-ttu-id="4efb9-298">Par conséquent, vous déclarez le `Match` type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-298">Thus, you first declare the `Match` type.</span></span> <span data-ttu-id="4efb9-299">Étant donné que ce type varie selon le modèle a été fourni comme argument statique, ce type doit être imbriqué dans la définition de type paramétré :</span><span class="sxs-lookup"><span data-stu-id="4efb9-299">Because this type depends on the pattern that was supplied as a static argument, this type must be nested within the parameterized type definition:</span></span>

```fsharp
let matchTy = 
    ProvidedTypeDefinition(
        "MatchType", 
        baseType = Some baseTy, 
        hideObjectMethods = true)

ty.AddMember matchTy
```

<span data-ttu-id="4efb9-300">Vous montre ensuite comment ajouter une propriété du type de correspondance pour chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="4efb9-300">You then add one property to the Match type for each group.</span></span> <span data-ttu-id="4efb9-301">Lors de l’exécution, une correspondance est représentée comme un <xref:System.Text.RegularExpressions.Match> valeur, par conséquent, le guillemet anglais qui définit la propriété doit utiliser le <xref:System.Text.RegularExpressions.Match.Groups> indexé de propriété pour obtenir le groupe approprié.</span><span class="sxs-lookup"><span data-stu-id="4efb9-301">At runtime, a match is represented as a <xref:System.Text.RegularExpressions.Match> value, so the quotation that defines the property must use the <xref:System.Text.RegularExpressions.Match.Groups> indexed property to get the relevant group.</span></span>

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop = 
      ProvidedProperty(
        propertyName = group, 
        propertyType = typeof<Group>, 
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

<span data-ttu-id="4efb9-302">Là encore, notez que vous ajoutez la documentation XML à la propriété fournie.</span><span class="sxs-lookup"><span data-stu-id="4efb9-302">Again, note that you’re adding XML documentation to the provided property.</span></span> <span data-ttu-id="4efb9-303">Notez également une propriété pouvant être lus si un `GetterCode` (fonction) est fournie, et la propriété peut être écrite si un `SetterCode` (fonction) est fournie, la propriété résultante est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="4efb9-303">Also note that a property can be read if a `GetterCode` function is provided, and the property can be written if a `SetterCode` function is provided, so the resulting property is read only.</span></span>

<span data-ttu-id="4efb9-304">Vous pouvez désormais créer une méthode d’instance qui retourne une valeur de ce `Match` type :</span><span class="sxs-lookup"><span data-stu-id="4efb9-304">Now you can create an instance method that returns a value of this `Match` type:</span></span>

```fsharp
let matchMethod = 
    ProvidedMethod(
        methodName = "Match", 
        parameters = [ProvidedParameter("input", typeof<string>)], 
        returnType = matchTy, 
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first ocurrence of this regular expression" 

ty.AddMember matchMeth
```

<span data-ttu-id="4efb9-305">Étant donné que vous créez une méthode d’instance, `args.[0]` représente le `RegexTyped` instance sur laquelle la méthode est appelée, et `args.[1]` est l’argument d’entrée.</span><span class="sxs-lookup"><span data-stu-id="4efb9-305">Because you are creating an instance method, `args.[0]` represents the `RegexTyped` instance on which the method is being called, and `args.[1]` is the input argument.</span></span>

<span data-ttu-id="4efb9-306">Enfin, fournissez un constructeur afin que les instances du type fourni peuvent être créées.</span><span class="sxs-lookup"><span data-stu-id="4efb9-306">Finally, provide a constructor so that instances of the provided type can be created.</span></span>

```fsharp
let ctor = 
    ProvidedConstructor(
        parameters = [], 
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

<span data-ttu-id="4efb9-307">Le constructeur efface simplement à la création d’une instance de Regex de .NET standard, qui est à nouveau convertie (boxed) à un objet, car `obj` est l’effacement du type fourni.</span><span class="sxs-lookup"><span data-stu-id="4efb9-307">The constructor merely erases to the creation of a standard .NET Regex instance, which is again boxed to an object because `obj` is the erasure of the provided type.</span></span> <span data-ttu-id="4efb9-308">Avec cette modification, l’utilisation de l’API exemple spécifié précédemment dans la rubrique fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="4efb9-308">With that change, the sample API usage that specified earlier in the topic works as expected.</span></span> <span data-ttu-id="4efb9-309">Le code suivant est complet et finale :</span><span class="sxs-lookup"><span data-stu-id="4efb9-309">The following code is complete and final:</span></span>

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams, 
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with 
            | [| :? string as pattern|] -> 

                // Create an instance of the regular expression. 

                let r = System.Text.RegularExpressions.Regex(pattern)            

                // Declare the typed regex provided type.

                let ty = 
                    ProvidedTypeDefinition(
                        thisAssembly, 
                        rootNamespace, 
                        typeName, 
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch = 
                    ProvidedMethod(
                        methodName = "IsMatch", 
                        parameters = [ProvidedParameter("input", typeof<string>)], 
                        returnType = typeof<bool>, 
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>) 

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy = 
                    ProvidedTypeDefinition(
                        "MatchType", 
                        baseType = Some baseTy, 
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop = 
                          ProvidedProperty(
                            propertyName = group, 
                            propertyType = typeof<Group>, 
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth = 
                  ProvidedMethod(
                    methodName = "Match", 
                    parameters = [ProvidedParameter("input", typeof<string>)], 
                    returnType = matchTy, 
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor = 
                  ProvidedConstructor(
                    parameters = [], 
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values")) 

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a><span data-ttu-id="4efb9-310">Leçons clés</span><span class="sxs-lookup"><span data-stu-id="4efb9-310">Key Lessons</span></span>

<span data-ttu-id="4efb9-311">Cette section explique comment créer un fournisseur de type qui opère sur ses paramètres statiques.</span><span class="sxs-lookup"><span data-stu-id="4efb9-311">This section explained how to create a type provider that operates on its static parameters.</span></span> <span data-ttu-id="4efb9-312">Le fournisseur vérifie le paramètre static et fournit des opérations en fonction de sa valeur.</span><span class="sxs-lookup"><span data-stu-id="4efb9-312">The provider checks the static parameter and provides operations based on its value.</span></span>


## <a name="a-type-provider-that-is-backed-by-local-data"></a><span data-ttu-id="4efb9-313">Un fournisseur de Type qui est sauvegardé par les données locales</span><span class="sxs-lookup"><span data-stu-id="4efb9-313">A Type Provider That Is Backed By Local Data</span></span>

<span data-ttu-id="4efb9-314">Vous pourriez fréquemment des fournisseurs de type pour présenter les API basées sur les paramètres statiques, mais également des informations à partir des systèmes locaux ou distants.</span><span class="sxs-lookup"><span data-stu-id="4efb9-314">Frequently you might want type providers to present APIs based on not only static parameters but also information from local or remote systems.</span></span> <span data-ttu-id="4efb9-315">Cette section traite des fournisseurs de type qui sont basées sur les données locales, telles que des fichiers de données locaux.</span><span class="sxs-lookup"><span data-stu-id="4efb9-315">This section discusses type providers that are based on local data, such as local data files.</span></span>


### <a name="simple-csv-file-provider"></a><span data-ttu-id="4efb9-316">Fournisseur du fichier CSV simple</span><span class="sxs-lookup"><span data-stu-id="4efb9-316">Simple CSV File Provider</span></span>

<span data-ttu-id="4efb9-317">À titre d’exemple, considérez un fournisseur de type pour l’accès aux données scientifiques au format de valeurs séparées par des virgules (CSV).</span><span class="sxs-lookup"><span data-stu-id="4efb9-317">As a simple example, consider a type provider for accessing scientific data in Comma Separated Value (CSV) format.</span></span> <span data-ttu-id="4efb9-318">Cette section part du principe que les fichiers CSV contient une ligne d’en-tête suivie par les données à virgule flottante, comme l’illustre le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-318">This section assumes that the CSV files contain a header row followed by floating point data, as the following table illustrates:</span></span>


|<span data-ttu-id="4efb9-319">Distance (compteur)</span><span class="sxs-lookup"><span data-stu-id="4efb9-319">Distance (meter)</span></span>|<span data-ttu-id="4efb9-320">Temps (en secondes)</span><span class="sxs-lookup"><span data-stu-id="4efb9-320">Time (second)</span></span>|
|----------------|-------------|
|<span data-ttu-id="4efb9-321">50.0</span><span class="sxs-lookup"><span data-stu-id="4efb9-321">50.0</span></span>|<span data-ttu-id="4efb9-322">3.7</span><span class="sxs-lookup"><span data-stu-id="4efb9-322">3.7</span></span>|
|<span data-ttu-id="4efb9-323">100.0</span><span class="sxs-lookup"><span data-stu-id="4efb9-323">100.0</span></span>|<span data-ttu-id="4efb9-324">5.2</span><span class="sxs-lookup"><span data-stu-id="4efb9-324">5.2</span></span>|
|<span data-ttu-id="4efb9-325">150.0</span><span class="sxs-lookup"><span data-stu-id="4efb9-325">150.0</span></span>|<span data-ttu-id="4efb9-326">6.4</span><span class="sxs-lookup"><span data-stu-id="4efb9-326">6.4</span></span>|

<span data-ttu-id="4efb9-327">Cette section montre comment fournir un type que vous pouvez utiliser pour obtenir des lignes avec un `Distance` propriété de type `float<meter>` et un `Time` propriété de type `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-327">This section shows how to provide a type that you can use to get rows with a `Distance` property of type `float<meter>` and a `Time` property of type `float<second>`.</span></span> <span data-ttu-id="4efb9-328">Par souci de simplicité, les hypothèses suivantes sont effectuées :</span><span class="sxs-lookup"><span data-stu-id="4efb9-328">For simplicity, the following assumptions are made:</span></span>

- <span data-ttu-id="4efb9-329">Les noms d’en-tête sont sans unité ou avoir la forme « Nom (unité) » et ne pas contenir de virgules.</span><span class="sxs-lookup"><span data-stu-id="4efb9-329">Header names are either unit-less or have the form "Name (unit)" and don't contain commas.</span></span>

- <span data-ttu-id="4efb9-330">Les unités sont toutes les unités du système International (SI) en tant que le [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames (Module) (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module définit.</span><span class="sxs-lookup"><span data-stu-id="4efb9-330">Units are all Systeme International (SI) units as the [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F#)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module defines.</span></span>

- <span data-ttu-id="4efb9-331">Les unités sont tout simples (par exemple, contrôler) plutôt que composée (par exemple, compteur/seconde).</span><span class="sxs-lookup"><span data-stu-id="4efb9-331">Units are all simple (for example, meter) rather than compound (for example, meter/second).</span></span>

- <span data-ttu-id="4efb9-332">Toutes les colonnes contiennent des données à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="4efb9-332">All columns contain floating point data.</span></span>

<span data-ttu-id="4efb9-333">Un fournisseur plus complète serait assouplir ces restrictions.</span><span class="sxs-lookup"><span data-stu-id="4efb9-333">A more complete provider would loosen these restrictions.</span></span>

<span data-ttu-id="4efb9-334">Là encore, la première étape consiste à prendre en compte l’aspect de l’API.</span><span class="sxs-lookup"><span data-stu-id="4efb9-334">Again the first step is to consider how the API should look.</span></span> <span data-ttu-id="4efb9-335">Étant donné un `info.csv` fichier avec le contenu du tableau précédent (au format séparées par des virgules), les utilisateurs du fournisseur doivent être en mesure d’écrire du code qui ressemble à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-335">Given an `info.csv` file with the contents from the previous table (in comma-separated format), users of the provider should be able to write code that resembles the following example:</span></span>

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

<span data-ttu-id="4efb9-336">Dans ce cas, le compilateur doit convertir ces appels quelque chose comme l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-336">In this case, the compiler should convert these calls into something like the following example:</span></span>

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

<span data-ttu-id="4efb9-337">La traduction optimale nécessitera le fournisseur de type définir un réel `CsvFile` type dans assembly du fournisseur de type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-337">The optimal translation will require the type provider to define a real `CsvFile` type in the type provider's assembly.</span></span> <span data-ttu-id="4efb9-338">Fournisseurs de type reposent souvent sur quelques types d’assistance et des méthodes pour encapsuler la logique importante.</span><span class="sxs-lookup"><span data-stu-id="4efb9-338">Type providers often rely on a few helper types and methods to wrap important logic.</span></span> <span data-ttu-id="4efb9-339">Étant donné que les mesures sont effacés au moment de l’exécution, vous pouvez utiliser un `float[]` comme type effacé pour une ligne.</span><span class="sxs-lookup"><span data-stu-id="4efb9-339">Because measures are erased at runtime, you can use a `float[]` as the erased type for a row.</span></span> <span data-ttu-id="4efb9-340">Le compilateur traite les différentes colonnes comme ayant des types de mesure différente.</span><span class="sxs-lookup"><span data-stu-id="4efb9-340">The compiler will treat different columns as having different measure types.</span></span> <span data-ttu-id="4efb9-341">Par exemple, la première colonne dans notre exemple a type `float<meter>`, et le deuxième `float<second>`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-341">For example, the first column in our example has type `float<meter>`, and the second has `float<second>`.</span></span> <span data-ttu-id="4efb9-342">Toutefois, la représentation sous forme d’effacées peut rester simple.</span><span class="sxs-lookup"><span data-stu-id="4efb9-342">However, the erased representation can remain quite simple.</span></span>

<span data-ttu-id="4efb9-343">Le code suivant illustre le cœur de l’implémentation.</span><span class="sxs-lookup"><span data-stu-id="4efb9-343">The following code shows the core of the implementation.</span></span>

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data = 
        seq { for line in File.ReadAllLines(filename) |> Seq.skip 1 do
                 yield line.Split(',') |> Array.map float }
        |> Seq.cache
    member __.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->
    
        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop = 
                ProvidedProperty(fieldName, fieldTy, 
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop) 

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 = 
            ProvidedConstructor([], 
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)], 
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop = 
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy), 
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

<span data-ttu-id="4efb9-344">Notez les points suivants concernant l’implémentation :</span><span class="sxs-lookup"><span data-stu-id="4efb9-344">Note the following points about the implementation:</span></span>

- <span data-ttu-id="4efb9-345">Constructeurs surchargés autorisent le fichier d’origine ou qui a un schéma identique à lire.</span><span class="sxs-lookup"><span data-stu-id="4efb9-345">Overloaded constructors allow either the original file or one that has an identical schema to be read.</span></span> <span data-ttu-id="4efb9-346">Ce modèle est courant lorsque vous écrivez un fournisseur de type pour les sources de données locales ou distantes, et ce modèle permet à un fichier local à utiliser comme modèle pour les données distantes.</span><span class="sxs-lookup"><span data-stu-id="4efb9-346">This pattern is common when you write a type provider for local or remote data sources, and this pattern allows a local file to be used as the template for remote data.</span></span>

- <span data-ttu-id="4efb9-347">Vous pouvez utiliser la [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) valeur qui est passée au constructeur de fournisseur de type pour résoudre les noms de fichiers relatifs.</span><span class="sxs-lookup"><span data-stu-id="4efb9-347">You can use the [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) value that’s passed in to the type provider constructor to resolve relative file names.</span></span>

- <span data-ttu-id="4efb9-348">Vous pouvez utiliser la `AddDefinitionLocation` méthode pour définir l’emplacement des propriétés fournies.</span><span class="sxs-lookup"><span data-stu-id="4efb9-348">You can use the `AddDefinitionLocation` method to define the location of the provided properties.</span></span> <span data-ttu-id="4efb9-349">Par conséquent, si vous utilisez `Go To Definition` sur une propriété fournie, le fichier CSV s’ouvre dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4efb9-349">Therefore, if you use `Go To Definition` on a provided property, the CSV file will open in Visual Studio.</span></span>

- <span data-ttu-id="4efb9-350">Vous pouvez utiliser la `ProvidedMeasureBuilder` type pour rechercher les unités SI et pour générer les `float<_>` types.</span><span class="sxs-lookup"><span data-stu-id="4efb9-350">You can use the `ProvidedMeasureBuilder` type to look up the SI units and to generate the relevant `float<_>` types.</span></span>

### <a name="key-lessons"></a><span data-ttu-id="4efb9-351">Leçons clés</span><span class="sxs-lookup"><span data-stu-id="4efb9-351">Key Lessons</span></span>

<span data-ttu-id="4efb9-352">Cette section explique comment créer un fournisseur de type pour une source de données locale avec un schéma simple qui est contenu dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="4efb9-352">This section explained how to create a type provider for a local data source with a simple schema that's contained in the data source itself.</span></span>


## <a name="going-further"></a><span data-ttu-id="4efb9-353">Aller plus loin</span><span class="sxs-lookup"><span data-stu-id="4efb9-353">Going Further</span></span>

<span data-ttu-id="4efb9-354">Les sections suivantes contiennent des suggestions pour approfondir ce sujet.</span><span class="sxs-lookup"><span data-stu-id="4efb9-354">The following sections include suggestions for further study.</span></span>


### <a name="a-look-at-the-compiled-code-for-erased-types"></a><span data-ttu-id="4efb9-355">Examiner le Code compilé pour les Types effacés</span><span class="sxs-lookup"><span data-stu-id="4efb9-355">A Look at the Compiled Code for Erased Types</span></span>

<span data-ttu-id="4efb9-356">Pour vous donner une idée de la façon dont l’utilisation du fournisseur de type correspond au code qui est émis, examinez la fonction suivante à l’aide de la `HelloWorldTypeProvider` qui est utilisée plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4efb9-356">To give you some idea of how the use of the type provider corresponds to the code that's emitted, look at the following function by using the `HelloWorldTypeProvider` that's used earlier in this topic.</span></span>

```fsharp
let function1 () = 
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

<span data-ttu-id="4efb9-357">Voici une image du code qui en résulte décompilé en utilisant ildasm.exe :</span><span class="sxs-lookup"><span data-stu-id="4efb9-357">Here’s an image of the resulting code decompiled by using ildasm.exe:</span></span>

```
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

<span data-ttu-id="4efb9-358">Comme le montre l’exemple, toutes les mentions de type `Type1` et `InstanceProperty` propriété ont été effacées, en laissant uniquement les opérations sur les types de runtime impliqués.</span><span class="sxs-lookup"><span data-stu-id="4efb9-358">As the example shows, all mentions of the type `Type1` and the `InstanceProperty` property have been erased, leaving only operations on the runtime types involved.</span></span>


### <a name="design-and-naming-conventions-for-type-providers"></a><span data-ttu-id="4efb9-359">Conception et les Conventions d’affectation de noms pour les fournisseurs de Type</span><span class="sxs-lookup"><span data-stu-id="4efb9-359">Design and Naming Conventions for Type Providers</span></span>
<span data-ttu-id="4efb9-360">Observez les conventions suivantes lors de la création de fournisseurs de type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-360">Observe the following conventions when authoring type providers.</span></span>

<span data-ttu-id="4efb9-361">**Fournisseurs de protocoles de connexion** en général, les noms de la plupart des DLL de fournisseur pour des protocoles de connexion de données et de service, telles que les connexions OData ou SQL, doivent se terminer dans `TypeProvider` ou `TypeProviders`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-361">**Providers for Connectivity Protocols** In general, names of most provider DLLs for data and service connectivity protocols, such as OData or SQL connections, should end in `TypeProvider` or `TypeProviders`.</span></span> <span data-ttu-id="4efb9-362">Par exemple, utilisez un nom de la DLL qui ressemble à la chaîne suivante :</span><span class="sxs-lookup"><span data-stu-id="4efb9-362">For example, use a DLL name that resembles the following string:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.dll
```

<span data-ttu-id="4efb9-363">Vérifiez que vos types fournis sont membres de l’espace de noms correspondante et indiquent le protocole de connexion que vous avez implémentée :</span><span class="sxs-lookup"><span data-stu-id="4efb9-363">Ensure that your provided types are members of the corresponding namespace, and indicate the connectivity protocol that you implemented:</span></span>

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

<span data-ttu-id="4efb9-364">**Utilitaire de fournisseurs pour le codage général**.</span><span class="sxs-lookup"><span data-stu-id="4efb9-364">**Utility Providers for General Coding**.</span></span>  <span data-ttu-id="4efb9-365">Pour un fournisseur type utilitaire tel que des expressions régulières, le fournisseur de type peut être dans une bibliothèque de base, comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-365">For a utility type provider such as that for regular expressions, the type provider may be part of a base library, as the following example shows:</span></span>

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

<span data-ttu-id="4efb9-366">Dans ce cas, le type fourni apparaîtrait à un moment approprié selon les conventions de conception .NET normales :</span><span class="sxs-lookup"><span data-stu-id="4efb9-366">In this case, the provided type would appear at an appropriate point according to normal .NET design conventions:</span></span>

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

<span data-ttu-id="4efb9-367">**Sources de données singleton**.</span><span class="sxs-lookup"><span data-stu-id="4efb9-367">**Singleton Data Sources**.</span></span> <span data-ttu-id="4efb9-368">Certains fournisseurs de type se connecter à une source de données dédié et fournissent des données uniquement.</span><span class="sxs-lookup"><span data-stu-id="4efb9-368">Some type providers connect to a single dedicated data source and provide only data.</span></span> <span data-ttu-id="4efb9-369">Dans ce cas, vous devez supprimer la `TypeProvider` suffixe et utiliser les conventions normales d’affectation de noms .NET :</span><span class="sxs-lookup"><span data-stu-id="4efb9-369">In this case, you should drop the `TypeProvider` suffix and use normal conventions for .NET naming:</span></span>

```fsharp
#r "Fabrikam.Data.Freebase.dll"
  
let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

<span data-ttu-id="4efb9-370">Pour plus d’informations, consultez le `GetConnection` concevoir convention qui est décrite plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4efb9-370">For more information, see the `GetConnection` design convention that's described later in this topic.</span></span>


### <a name="design-patterns-for-type-providers"></a><span data-ttu-id="4efb9-371">Modèles de conception pour les fournisseurs de Type</span><span class="sxs-lookup"><span data-stu-id="4efb9-371">Design Patterns for Type Providers</span></span>

<span data-ttu-id="4efb9-372">Les sections suivantes décrivent les modèles de conception que vous pouvez utiliser lors de la création de fournisseurs de type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-372">The following sections describe design patterns you can use when authoring type providers.</span></span>


#### <a name="the-getconnection-design-pattern"></a><span data-ttu-id="4efb9-373">Le modèle de conception de GetConnection</span><span class="sxs-lookup"><span data-stu-id="4efb9-373">The GetConnection Design Pattern</span></span>
<span data-ttu-id="4efb9-374">La plupart des fournisseurs de type doivent être écrit pour utiliser la `GetConnection` modèle qui est utilisé par les fournisseurs de type dans FSharp.Data.TypeProviders.dll, comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-374">Most type providers should be written to use the `GetConnection` pattern that's used by the type providers in FSharp.Data.TypeProviders.dll, as the following example shows:</span></span>

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a><span data-ttu-id="4efb9-375">Fournisseurs de type soutenues par les Services et les données distantes</span><span class="sxs-lookup"><span data-stu-id="4efb9-375">Type Providers Backed By Remote Data and Services</span></span>

<span data-ttu-id="4efb9-376">Avant de créer un fournisseur de type qui est sauvegardé par les services et les données distantes, vous devez envisager une gamme de problèmes inhérents à la programmation connectée.</span><span class="sxs-lookup"><span data-stu-id="4efb9-376">Before you create a type provider that's backed by remote data and services, you must consider a range of issues that are inherent in connected programming.</span></span> <span data-ttu-id="4efb9-377">Ces problèmes incluent les points suivants :</span><span class="sxs-lookup"><span data-stu-id="4efb9-377">These issues include the following considerations:</span></span>

- <span data-ttu-id="4efb9-378">Mappage de schéma</span><span class="sxs-lookup"><span data-stu-id="4efb9-378">schema mapping</span></span>

- <span data-ttu-id="4efb9-379">activité et invalidation en cas de modification de schéma</span><span class="sxs-lookup"><span data-stu-id="4efb9-379">liveness and invalidation in the presence of schema change</span></span>

- <span data-ttu-id="4efb9-380">la mise en cache de schéma</span><span class="sxs-lookup"><span data-stu-id="4efb9-380">schema caching</span></span>

- <span data-ttu-id="4efb9-381">implémentations asynchrones d’opérations d’accès aux données</span><span class="sxs-lookup"><span data-stu-id="4efb9-381">asynchronous implementations of data access operations</span></span>

- <span data-ttu-id="4efb9-382">prise en charge des requêtes, y compris les requêtes LINQ</span><span class="sxs-lookup"><span data-stu-id="4efb9-382">supporting queries, including LINQ queries</span></span>

- <span data-ttu-id="4efb9-383">informations d’identification et l’authentification</span><span class="sxs-lookup"><span data-stu-id="4efb9-383">credentials and authentication</span></span>

<span data-ttu-id="4efb9-384">Cette rubrique n’Explorer davantage ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="4efb9-384">This topic doesn't explore these issues further.</span></span>

### <a name="additional-authoring-techniques"></a><span data-ttu-id="4efb9-385">Autres Techniques de création</span><span class="sxs-lookup"><span data-stu-id="4efb9-385">Additional Authoring Techniques</span></span>

<span data-ttu-id="4efb9-386">Lorsque vous écrivez vos propres fournisseurs de type, vous souhaiterez probablement utiliser les techniques supplémentaires suivantes.</span><span class="sxs-lookup"><span data-stu-id="4efb9-386">When you write your own type providers, you might want to use the following additional techniques.</span></span>

### <a name="creating-types-and-members-on-demand"></a><span data-ttu-id="4efb9-387">Création de Types et membres à la demande</span><span class="sxs-lookup"><span data-stu-id="4efb9-387">Creating Types and Members On-Demand</span></span>

<span data-ttu-id="4efb9-388">L’API ProvidedType a différée des versions de AddMember.</span><span class="sxs-lookup"><span data-stu-id="4efb9-388">The ProvidedType API has delayed versions of AddMember.</span></span>

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

<span data-ttu-id="4efb9-389">Ces versions sont utilisées pour créer des espaces à la demande de types.</span><span class="sxs-lookup"><span data-stu-id="4efb9-389">These versions are used to create on-demand spaces of types.</span></span>

### <a name="providing-array-types-and-generic-type-instantiations"></a><span data-ttu-id="4efb9-390">En fournissant des types de tableau et les instanciations de Type générique</span><span class="sxs-lookup"><span data-stu-id="4efb9-390">Providing Array types and Generic Type Instantiations</span></span>

<span data-ttu-id="4efb9-391">Assurez-vous de membres fournies (dont les signatures incluent les types tableau, types byref et instanciations de types génériques) à l’aide du vecteur normal `MakeArrayType`, `MakePointerType`, et `MakeGenericType` sur n’importe quelle instance de <xref:System.Type>, y compris `ProvidedTypeDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-391">You make provided members (whose signatures include array types, byref types, and instantiations of generic types) by using the normal `MakeArrayType`, `MakePointerType`, and `MakeGenericType` on any instance of <xref:System.Type>, including `ProvidedTypeDefinitions`.</span></span>

> [!NOTE]
> <span data-ttu-id="4efb9-392">Dans certains cas vous devrez peut-être utiliser l’application d’assistance dans `ProvidedTypeBuilder.MakeGenericType`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-392">In some cases you may have to use the helper in `ProvidedTypeBuilder.MakeGenericType`.</span></span>  <span data-ttu-id="4efb9-393">Consultez le [documentation du SDK de fournisseur de Type](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="4efb9-393">See the [Type Provider SDK documentation](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) for more details.</span></span>

### <a name="providing-unit-of-measure-annotations"></a><span data-ttu-id="4efb9-394">Fournir l’unité de mesure Annotations</span><span class="sxs-lookup"><span data-stu-id="4efb9-394">Providing Unit of Measure Annotations</span></span>

<span data-ttu-id="4efb9-395">L’API ProvidedTypes fournit des Assistants pour fournir des annotations de mesure.</span><span class="sxs-lookup"><span data-stu-id="4efb9-395">The ProvidedTypes API provides helpers for providing measure annotations.</span></span> <span data-ttu-id="4efb9-396">Par exemple, pour fournir le type `float<kg>`, utilisez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-396">For example, to provide the type `float<kg>`, use the following code:</span></span>

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  <span data-ttu-id="4efb9-397">Pour fournir le type `Nullable<decimal<kg/m^2>>`, utilisez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4efb9-397">To provide the type `Nullable<decimal<kg/m^2>>`, use the following code:</span></span>

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a><span data-ttu-id="4efb9-398">L’accès aux ressources de projet Local ou le Script Local</span><span class="sxs-lookup"><span data-stu-id="4efb9-398">Accessing Project-Local or Script-Local Resources</span></span>

<span data-ttu-id="4efb9-399">Chaque instance d’un fournisseur de type peut être accordée à un `TypeProviderConfig` valeur pendant la construction.</span><span class="sxs-lookup"><span data-stu-id="4efb9-399">Each instance of a type provider can be given a `TypeProviderConfig` value during construction.</span></span> <span data-ttu-id="4efb9-400">Cette valeur contient le dossier « résolution » pour le fournisseur (autrement dit, le dossier de projet pour la compilation ou le répertoire qui contient un script), la liste des assemblys référencés et d’autres informations.</span><span class="sxs-lookup"><span data-stu-id="4efb9-400">This value contains the "resolution folder" for the provider (that is, the project folder for the compilation or the directory that contains a script), the list of referenced assemblies, and other information.</span></span>

### <a name="invalidation"></a><span data-ttu-id="4efb9-401">Invalidation</span><span class="sxs-lookup"><span data-stu-id="4efb9-401">Invalidation</span></span>

<span data-ttu-id="4efb9-402">Fournisseurs peuvent déclencher des signaux d’invalidation pour notifier le service de langage F # qui les hypothèses de schéma a peut-être été modifié.</span><span class="sxs-lookup"><span data-stu-id="4efb9-402">Providers can raise invalidation signals to notify the F# language service that the schema assumptions may have changed.</span></span> <span data-ttu-id="4efb9-403">En cas d’invalidation, un typecheck est réexécutée si le fournisseur est hébergé dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4efb9-403">When invalidation occurs, a typecheck is redone if the provider is being hosted in Visual Studio.</span></span> <span data-ttu-id="4efb9-404">Ce signal est ignoré lorsque le fournisseur est hébergé dans F # Interactive ou par le compilateur F # (fsc.exe).</span><span class="sxs-lookup"><span data-stu-id="4efb9-404">This signal will be ignored when the provider is hosted in F# Interactive or by the F# Compiler (fsc.exe).</span></span>

### <a name="caching-schema-information"></a><span data-ttu-id="4efb9-405">La mise en cache des informations de schéma</span><span class="sxs-lookup"><span data-stu-id="4efb9-405">Caching Schema Information</span></span>

<span data-ttu-id="4efb9-406">Fournisseurs souvent doivent mettre en cache l’accès aux informations de schéma.</span><span class="sxs-lookup"><span data-stu-id="4efb9-406">Providers must often cache access to schema information.</span></span> <span data-ttu-id="4efb9-407">Les données mises en cache doivent être stockées à l’aide d’un nom de fichier est fourni comme paramètre statique ou en tant que données de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4efb9-407">The cached data should be stored by using a file name that's given as a static parameter or as user data.</span></span> <span data-ttu-id="4efb9-408">Un exemple de mise en cache de schéma est le `LocalSchemaFile` paramètre dans les fournisseurs de type dans le `FSharp.Data.TypeProviders` assembly.</span><span class="sxs-lookup"><span data-stu-id="4efb9-408">An example of schema caching is the `LocalSchemaFile` parameter in the type providers in the `FSharp.Data.TypeProviders` assembly.</span></span> <span data-ttu-id="4efb9-409">Dans l’implémentation de ces fournisseurs, ce paramètre statique dirige le fournisseur de type à utiliser les informations de schéma dans le fichier local spécifié au lieu de l’accès à la source de données sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="4efb9-409">In the implementation of these providers, this static parameter directs the type provider to use the schema information in the specified local file instead of accessing the data source over the network.</span></span> <span data-ttu-id="4efb9-410">Pour utiliser les informations de schéma mis en cache, vous devez également définir le paramètre static `ForceUpdate` à `false`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-410">To use cached schema information, you must also set the static parameter `ForceUpdate` to `false`.</span></span> <span data-ttu-id="4efb9-411">Vous pouvez utiliser une technique similaire pour activer l’accès aux données en ligne et hors connexion.</span><span class="sxs-lookup"><span data-stu-id="4efb9-411">You could use a similar technique to enable online and offline data access.</span></span>

### <a name="backing-assembly"></a><span data-ttu-id="4efb9-412">Assembly de stockage</span><span class="sxs-lookup"><span data-stu-id="4efb9-412">Backing Assembly</span></span>

<span data-ttu-id="4efb9-413">Lorsque vous compilez un `.dll` ou `.exe` de fichiers, le fichier de sauvegarde pour les types générés est statiquement liée dans l’assembly résultant.</span><span class="sxs-lookup"><span data-stu-id="4efb9-413">When you compile a `.dll` or `.exe` file, the backing .dll file for generated types is statically linked into the resulting assembly.</span></span> <span data-ttu-id="4efb9-414">Ce lien est créé en copiant les définitions de type (Microsoft Intermediate Language) et toutes les ressources managées à partir de l’assembly de stockage dans l’assembly final.</span><span class="sxs-lookup"><span data-stu-id="4efb9-414">This link is created by copying the Intermediate Language (IL) type definitions and any managed resources from the backing assembly into the final assembly.</span></span> <span data-ttu-id="4efb9-415">Lorsque vous utilisez F # Interactive, le fichier de sauvegarde n’est pas copié et est chargé à la place directement dans le processus interactif F #.</span><span class="sxs-lookup"><span data-stu-id="4efb9-415">When you use F# Interactive, the backing .dll file isn't copied and is instead loaded directly into the F# Interactive process.</span></span>

### <a name="exceptions-and-diagnostics-from-type-providers"></a><span data-ttu-id="4efb9-416">Exceptions et des Diagnostics à partir des fournisseurs de Type</span><span class="sxs-lookup"><span data-stu-id="4efb9-416">Exceptions and Diagnostics from Type Providers</span></span>

<span data-ttu-id="4efb9-417">Toutes les utilisations de tous les membres de types fournis peuvent lever des exceptions.</span><span class="sxs-lookup"><span data-stu-id="4efb9-417">All uses of all members from provided types may throw exceptions.</span></span> <span data-ttu-id="4efb9-418">Dans tous les cas, si un fournisseur de type lève une exception, le compilateur hôte attributs de l’erreur à un fournisseur de type spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4efb9-418">In all cases, if a type provider throws an exception, the host compiler attributes the error to a specific type provider.</span></span>

- <span data-ttu-id="4efb9-419">Exceptions de fournisseur de type ne génère jamais dans les erreurs internes du compilateur.</span><span class="sxs-lookup"><span data-stu-id="4efb9-419">Type provider exceptions should never result in internal compiler errors.</span></span>

- <span data-ttu-id="4efb9-420">Fournisseurs de type ne peut pas signaler les avertissements.</span><span class="sxs-lookup"><span data-stu-id="4efb9-420">Type providers can't report warnings.</span></span>

- <span data-ttu-id="4efb9-421">Lorsqu’un fournisseur de type est hébergé dans le compilateur F #, un environnement de développement F # ou F # Interactive, toutes les exceptions de ce fournisseur sont interceptées.</span><span class="sxs-lookup"><span data-stu-id="4efb9-421">When a type provider is hosted in the F# compiler, an F# development environment, or F# Interactive, all exceptions from that provider are caught.</span></span> <span data-ttu-id="4efb9-422">La propriété de Message est toujours le texte d’erreur, et aucune trace de la pile s’affiche.</span><span class="sxs-lookup"><span data-stu-id="4efb9-422">The Message property is always the error text, and no stack trace appears.</span></span> <span data-ttu-id="4efb9-423">Si vous souhaitez lever une exception, vous pouvez lever les exemples suivants : `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-423">If you’re going to throw an exception, you can throw the following examples: `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.</span></span>

#### <a name="providing-generated-types"></a><span data-ttu-id="4efb9-424">En fournissant les Types générés</span><span class="sxs-lookup"><span data-stu-id="4efb9-424">Providing Generated Types</span></span>

<span data-ttu-id="4efb9-425">Jusqu'à présent, ce document a expliqué comment fournir des types effacées.</span><span class="sxs-lookup"><span data-stu-id="4efb9-425">So far, this document has explained how to provide erased types.</span></span> <span data-ttu-id="4efb9-426">Vous pouvez également utiliser le mécanisme de fournisseur de type en F # pour fournir des types générés, qui sont ajoutés en tant que définitions de type .NET réelles dans le programme de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4efb9-426">You can also use the type provider mechanism in F# to provide generated types, which are added as real .NET type definitions into the users' program.</span></span> <span data-ttu-id="4efb9-427">Vous devez faire référence à généré fourni des types à l’aide d’une définition de type.</span><span class="sxs-lookup"><span data-stu-id="4efb9-427">You must refer to generated provided types by using a type definition.</span></span>

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

<span data-ttu-id="4efb9-428">Le code d’assistance ProvidedTypes-0,2 qui fait partie de la version 3.0) (F # prend uniquement en charge limitée pour fournir des types générés.</span><span class="sxs-lookup"><span data-stu-id="4efb9-428">The ProvidedTypes-0.2 helper code that is part of the F# 3.0 release has only limited support for providing generated types.</span></span> <span data-ttu-id="4efb9-429">Les instructions suivantes doivent être remplies pour une définition de type généré :</span><span class="sxs-lookup"><span data-stu-id="4efb9-429">The following statements must be true for a generated type definition:</span></span>

- <span data-ttu-id="4efb9-430">`isErased` doit avoir la valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-430">`isErased` must be set to `false`.</span></span>

- <span data-ttu-id="4efb9-431">Le type généré doit être ajouté à un nouvellement construit `ProvidedAssembly()`, qui représente un conteneur pour les fragments de code généré.</span><span class="sxs-lookup"><span data-stu-id="4efb9-431">The generated type must be added to a newly constructed `ProvidedAssembly()`, which represents a container for generated code fragments.</span></span>

- <span data-ttu-id="4efb9-432">Le fournisseur doit disposer d’un assembly qui a un fichier .dll de stockage réel .NET avec un fichier .dll correspondant sur le disque.</span><span class="sxs-lookup"><span data-stu-id="4efb9-432">The provider must have an assembly that has an actual backing .NET .dll file with a matching .dll file on disk.</span></span>


## <a name="rules-and-limitations"></a><span data-ttu-id="4efb9-433">Règles et Limitations</span><span class="sxs-lookup"><span data-stu-id="4efb9-433">Rules and Limitations</span></span>

<span data-ttu-id="4efb9-434">Lorsque vous écrivez des fournisseurs de type, gardez les règles suivantes et les limitations à l’esprit.</span><span class="sxs-lookup"><span data-stu-id="4efb9-434">When you write type providers, keep the following rules and limitations in mind.</span></span>


### <a name="provided-types-must-be-reachable"></a><span data-ttu-id="4efb9-435">Types fournis doivent être accessibles</span><span class="sxs-lookup"><span data-stu-id="4efb9-435">Provided types must be reachable</span></span>

<span data-ttu-id="4efb9-436">Tous les fourni types doivent être accessibles à partir des types non imbriqués.</span><span class="sxs-lookup"><span data-stu-id="4efb9-436">All provided types should be reachable from the non-nested types.</span></span> <span data-ttu-id="4efb9-437">Les types non imbriqués figurent dans l’appel à la `TypeProviderForNamespaces` constructeur ou un appel à `AddNamespace`.</span><span class="sxs-lookup"><span data-stu-id="4efb9-437">The non-nested types are given in the call to the `TypeProviderForNamespaces` constructor or a call to `AddNamespace`.</span></span> <span data-ttu-id="4efb9-438">Par exemple, si le fournisseur fournit un type `StaticClass.P : T`, vous devez vous assurer que T est un type non imbriqué ou imbriqués sous un.</span><span class="sxs-lookup"><span data-stu-id="4efb9-438">For example, if the provider provides a type `StaticClass.P : T`, you must ensure that T is either a non-nested type or nested under one.</span></span>

<span data-ttu-id="4efb9-439">Par exemple, certains fournisseurs ont une classe statique comme `DataTypes` qui contiennent ces `T1, T2, T3, ...` types.</span><span class="sxs-lookup"><span data-stu-id="4efb9-439">For example, some providers have a static class such as `DataTypes` that contain these `T1, T2, T3, ...` types.</span></span> <span data-ttu-id="4efb9-440">Sinon, l’erreur indique qu’une référence au type T dans l’assembly A a été trouvée, mais le type n’a pas pu être trouvé dans cet assembly.</span><span class="sxs-lookup"><span data-stu-id="4efb9-440">Otherwise, the error says that a reference to type T in assembly A was found, but the type couldn't be found in that assembly.</span></span> <span data-ttu-id="4efb9-441">Si cette erreur s’affiche, vérifiez que tous les sous-types votre peuvent être atteint à partir des types de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="4efb9-441">If this error appears, verify that all your subtypes can be reached from the provider types.</span></span> <span data-ttu-id="4efb9-442">Remarque : Ces `T1, T2, T3...` types sont appelés les *à la volée* types.</span><span class="sxs-lookup"><span data-stu-id="4efb9-442">Note: These `T1, T2, T3...` types are referred to as the *on-the-fly* types.</span></span> <span data-ttu-id="4efb9-443">Pensez à les placer dans un espace de noms accessible ou d’un type de parent.</span><span class="sxs-lookup"><span data-stu-id="4efb9-443">Remember to put them in an accessible namespace or a parent type.</span></span>

### <a name="limitations-of-the-type-provider-mechanism"></a><span data-ttu-id="4efb9-444">Limitations du mécanisme de fournisseur de Type</span><span class="sxs-lookup"><span data-stu-id="4efb9-444">Limitations of the Type Provider Mechanism</span></span>

<span data-ttu-id="4efb9-445">Le mécanisme de fournisseur de type en F # présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4efb9-445">The type provider mechanism in F# has the following limitations:</span></span>

- <span data-ttu-id="4efb9-446">L’infrastructure sous-jacente pour les fournisseurs de type en F # ne prend pas en charge fournie générique types ou méthodes génériques fournies.</span><span class="sxs-lookup"><span data-stu-id="4efb9-446">The underlying infrastructure for type providers in F# doesn't support provided generic types or provided generic methods.</span></span>

- <span data-ttu-id="4efb9-447">Le mécanisme ne prend pas en charge les types imbriqués avec des paramètres statiques.</span><span class="sxs-lookup"><span data-stu-id="4efb9-447">The mechanism doesn't support nested types with static parameters.</span></span>

## <a name="development-tips"></a><span data-ttu-id="4efb9-448">Conseils de développement</span><span class="sxs-lookup"><span data-stu-id="4efb9-448">Development Tips</span></span>

<span data-ttu-id="4efb9-449">Vous trouverez les conseils suivants utiles pendant le processus de développement.</span><span class="sxs-lookup"><span data-stu-id="4efb9-449">You might find the following tips helpful during the development process.</span></span>

### <a name="run-two-instances-of-visual-studio"></a><span data-ttu-id="4efb9-450">Exécutez deux Instances de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4efb9-450">Run Two Instances of Visual Studio</span></span>

<span data-ttu-id="4efb9-451">Vous pouvez développer le fournisseur de type dans une seule instance et le fournisseur de test dans l’autre, car le test IDE effectuera un verrou sur le fichier .dll qui empêche que le fournisseur de type en cours de reconstruction.</span><span class="sxs-lookup"><span data-stu-id="4efb9-451">You can develop the type provider in one instance and test the provider in the other because the test IDE will take a lock on the .dll file that prevents the type provider from being rebuilt.</span></span> <span data-ttu-id="4efb9-452">Par conséquent, vous devez fermer la deuxième instance de Visual Studio pendant que le fournisseur est créé dans la première instance, puis vous devez rouvrir la deuxième instance une fois le fournisseur est créé.</span><span class="sxs-lookup"><span data-stu-id="4efb9-452">Thus, you must close the second instance of Visual Studio while the provider is built in the first instance, and then you must reopen the second instance after the provider is built.</span></span>

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a><span data-ttu-id="4efb9-453">Déboguer les fournisseurs de type à l’aide d’appels de fsc.exe</span><span class="sxs-lookup"><span data-stu-id="4efb9-453">Debug type providers by using invocations of fsc.exe</span></span>

<span data-ttu-id="4efb9-454">Vous pouvez appeler des fournisseurs de type à l’aide des outils suivants :</span><span class="sxs-lookup"><span data-stu-id="4efb9-454">You can invoke type providers by using the following tools:</span></span>

- <span data-ttu-id="4efb9-455">FSC.exe (F # de la ligne de commande du compilateur)</span><span class="sxs-lookup"><span data-stu-id="4efb9-455">fsc.exe (The F# command line compiler)</span></span>

- <span data-ttu-id="4efb9-456">fsi.exe (F # Interactive du compilateur)</span><span class="sxs-lookup"><span data-stu-id="4efb9-456">fsi.exe (The F# Interactive compiler)</span></span>

- <span data-ttu-id="4efb9-457">devenv.exe (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="4efb9-457">devenv.exe (Visual Studio)</span></span>

<span data-ttu-id="4efb9-458">Vous pouvez souvent de déboguer plus facilement les fournisseurs de type à l’aide de fsc.exe sur un fichier de script de test (par exemple, script.fsx).</span><span class="sxs-lookup"><span data-stu-id="4efb9-458">You can often debug type providers most easily by using fsc.exe on a test script file (for example, script.fsx).</span></span> <span data-ttu-id="4efb9-459">Vous pouvez lancer un débogueur à partir d’une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="4efb9-459">You can launch a debugger from a command prompt.</span></span>

```
  devenv /debugexe fsc.exe script.fsx
```

  <span data-ttu-id="4efb9-460">Vous pouvez utiliser la journalisation de l’impression à stdout.</span><span class="sxs-lookup"><span data-stu-id="4efb9-460">You can use print-to-stdout logging.</span></span>


## <a name="see-also"></a><span data-ttu-id="4efb9-461">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4efb9-461">See Also</span></span>

* [<span data-ttu-id="4efb9-462">Fournisseurs de type</span><span class="sxs-lookup"><span data-stu-id="4efb9-462">Type Providers</span></span>](index.md)

* [<span data-ttu-id="4efb9-463">Le Kit de développement logiciel de fournisseur de Type</span><span class="sxs-lookup"><span data-stu-id="4efb9-463">The Type Provider SDK</span></span>](https://github.com/fsprojects/FSharp.TypeProviders.SDK)


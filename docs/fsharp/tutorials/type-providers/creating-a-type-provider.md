---
title: 'Didacticiel : Créer un fournisseur de Type (F #)'
description: 'Découvrez comment créer vos propres fournisseurs de type F # dans F # 3.0 en examinant les fournisseurs de type simple pour illustrer les concepts de base.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: cea71a2b71f660971c1b2dde702c9b489be48cee
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="tutorial-create-a-type-provider"></a>Didacticiel : Créer un fournisseur de Type

Le mécanisme de fournisseur de type en F # est une partie importante de la prise en charge pour la programmation riche d’informations. Ce didacticiel explique comment créer vos propres fournisseurs de type en vous guidant à travers le développement de plusieurs fournisseurs de type simple pour illustrer les concepts de base. Pour plus d’informations sur le mécanisme de fournisseur de type en F #, consultez [fournisseurs de Type](index.md).

L’écosystème de F # contient une plage de fournisseurs de type pour les services de données Internet et d’entreprise couramment utilisés. Par exemple :

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) inclut les fournisseurs de type pour les formats de document JSON, XML, CSV et HTML.

- [SQLProvider](https://fsprojects.github.io/SQLProvider/) fournit un accès fortement typé aux bases de données SQL et un mappage d’objet LINQ F # de requêtes par rapport à ces sources de données.

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) a un ensemble de fournisseurs de type pour le moment de la compilation vérifié l’incorporation de T-SQL en F #.

- [FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) est un ancien ensemble de fournisseurs de type pour une utilisation uniquement avec la programmation .NET Framework pour accéder aux services de données SQL, Entity Framework, OData et WSDL.

Le cas échéant, vous pouvez créer des fournisseurs de type personnalisé, ou vous pouvez référencer des fournisseurs de type qu’ils ont créés. Par exemple, votre organisation peut avoir un service de données qui fournit un nombre important et croissant de jeux de données nommés, chacun avec son propre schéma stable de données. Vous pouvez créer un fournisseur de type qui lit les schémas et présente les jeux de données en cours au programmeur de manière fortement typée.


## <a name="before-you-start"></a>Avant de commencer

Le mécanisme de fournisseur de type est principalement conçu pour injecter des données stables et informations de service dans l’expérience de programmation F #.

Ce mécanisme n’est pas conçu pour injecter des espaces d’informations dont le schéma est modifiée au cours de l’exécution du programme avec des méthodes qui sont pertinents pour la logique du programme. En outre, le mécanisme n’est pas conçu pour intra-langage de programmation méta, bien que ce domaine contient certaines utilisations valides. Vous devez utiliser ce mécanisme uniquement si nécessaire et où le développement d’un fournisseur de type génère une valeur très élevée.

Vous devez éviter d’écrire un fournisseur de type où un schéma n’est pas disponible. De même, vous devez éviter d’écrire un fournisseur de type où un ordinaires (ou même un existant) bibliothèque .NET suffirait.

Avant de commencer, vous pouvez poser les questions suivantes :

- Vous avez un schéma pour la source d’informations ? Dans ce cas, ce qui est le mappage dans le système de type .NET et F # ?

- Pouvez-vous utiliser une API (typée dynamiquement) existante comme point de départ pour votre implémentation ?

- Vous et votre organisation aura suffisamment utilise du fournisseur de type pour rendre l’écrire utile ? Une bibliothèque .NET normale serait répondent à vos besoins ?

- Combien modifiera votre schéma ?

- Passe au cours de codage ?

- Il modifié entre les sessions de codage ?

- Il est modifié pendant l’exécution du programme ?

Fournisseurs de type sont mieux adaptées aux situations où le schéma est stable lors de l’exécution et pendant la durée de vie du code compilé.


## <a name="a-simple-type-provider"></a>Un fournisseur de Type Simple

Cet exemple est Samples.HelloWorldTypeProvider, similaires aux exemples dans le `examples` répertoire de la [SDK de fournisseur de Type F #](https://github.com/fsprojects/FSharp.TypeProviders.SDK/). Le fournisseur met à disposition un « espace de type » qui contient les types d’effacées 100, comme le montre le code suivant à l’aide de syntaxe de signature F # et en omettant les détails pour tous sauf `Type1`. Pour plus d’informations sur les types effacées, consultez [plus d’informations sur effacées fourni Types](#details-about-erased-provided-types) plus loin dans cette rubrique.

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

Notez que l’ensemble des types et membres fournis est statiquement connu. Cet exemple ne tirent parti de la capacité de fournisseurs pour fournir des types qui dépendent d’un schéma. L’implémentation du fournisseur de type est décrite dans le code suivant, et les détails sont traités dans les sections suivantes de cette rubrique.


>[!WARNING] 
Il peut exister des différences entre ce code et les exemples en ligne.

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

Pour utiliser ce fournisseur, ouvrez une instance distincte de Visual Studio, créer un script F #, puis ajoutez une référence au fournisseur à partir de votre script à l’aide de #r comme le montre le code suivant :

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

Recherchez ensuite les types sous la `Samples.HelloWorldTypeProvider` espace de noms généré par le fournisseur de type.

Avant de recompiler le fournisseur, assurez-vous que vous avez fermé toutes les instances de Visual Studio et F # Interactive qui sont à l’aide de la DLL du fournisseur. Dans le cas contraire, une erreur de build se produit car la DLL de sortie est verrouillée.

Pour déboguer ce fournisseur à l’aide des instructions print, rendre un script qui expose un problème avec le fournisseur, puis utilisez le code suivant :

```fsharp
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Pour déboguer ce fournisseur à l’aide de Visual Studio, ouvrez l’invite de commandes Visual Studio avec des informations d’identification d’administration, puis exécutez la commande suivante :

```fsharp
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

En guise d’alternative, ouvrez Visual Studio, ouvrez le menu Déboguer, choisissez `Debug/Attach to process…`et l’attacher à un autre `devenv` processus dans lequel vous modifiez votre script. À l’aide de cette méthode, vous pouvez plus facilement cibler logique particulier dans le fournisseur de type en tapant interactivement des expressions dans la deuxième instance (avec complète d’IntelliSense et d’autres fonctionnalités).

Vous pouvez désactiver uniquement mon Code de débogage pour mieux identifier les erreurs dans le code généré. Pour plus d’informations sur la façon d’activer ou désactiver cette fonctionnalité, consultez [naviguer dans le Code avec le débogueur](/visualstudio/debugger/navigating-through-code-with-the-debugger). En outre, vous pouvez également définir des exceptions de première chance interception en ouvrant le `Debug` menu, puis en choisissant `Exceptions` ou en appuyant sur Ctrl + Alt + E pour ouvrir le `Exceptions` boîte de dialogue. Cette boîte de dialogue, sous `Common Language Runtime Exceptions`, sélectionnez le `Thrown` case à cocher.


### <a name="implementation-of-the-type-provider"></a>Implémentation du fournisseur de Type

Cette section vous guide dans les sections principales de l’implémentation de fournisseur de type. Tout d’abord, vous définissez le type pour le fournisseur de type personnalisé lui-même :

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Ce type doit être public, et vous devez la marquer avec le [TypeProvider](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) afin que le compilateur reconnaît le fournisseur de type lorsqu’un projet distinct de F # fait référence à l’assembly qui contient le type d’attribut. Le *config* paramètre est facultatif et, le cas échéant, contient des informations de configuration contextuelles pour l’instance de fournisseur de type créés par le compilateur F #.

Ensuite, vous implémentez le [ITypeProvider](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) interface. Dans ce cas, vous utilisez la `TypeProviderForNamespaces` type à partir de la `ProvidedTypes` API comme type de base. Ce type d’assistance peut fournir dynamiquement une collection finie d’autant d’espaces de noms, chacun d’eux contient directement un nombre fini de fixe, fournies dynamiquement des types. Dans ce contexte, le fournisseur *anticipé* génère des types, même s’ils ne sont pas nécessaires ou utilisés.

```fsharp
inherit TypeProviderForNamespaces(config)
```

Ensuite, locales privés et des valeurs qui spécifient les types fournis dans l’espace de noms et trouver l’assembly de fournisseur de type lui-même. Cet assembly est utilisé ultérieurement comme type de parent logique des types fournis effacés.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

Ensuite, créez une fonction pour fournir chacun des types Type1... Type100. Cette fonction est expliquée plus en détail plus loin dans cette rubrique.

```fsharp
let makeOneProvidedType (n:int) = …
```

Ensuite, générez les types fournis 100 :

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Ensuite, ajoutez les types comme un espace de noms fourni :

```fsharp
do this.AddNamespace(namespaceName, types)
```

Enfin, ajoutez un attribut d’assembly qui indique que vous créez un fournisseur de type DLL :

```fsharp
[<assembly:TypeProviderAssembly>] 
do()
```

### <a name="providing-one-type-and-its-members"></a>En fournissant un Type et ses membres

Le `makeOneProvidedType` fonction effectue le travail de fournir un des types.

```fsharp
let makeOneProvidedType (n:int) = 
…
```

Cette étape explique l’implémentation de cette fonction. Commencez par créer le type fourni (par exemple, Type1, lorsque n = 1 ou Type57, lorsque n = 57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code, 
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

Notez les points suivants :

- Cette fournie de type est effacé.  Vous indique que le type de base est `obj`, instances seront affiche sous forme de valeurs de type [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) dans le code compilé.

- Lorsque vous spécifiez un type non imbriqué, vous devez spécifier l’assembly et l’espace de noms. Pour les types effacées, l’assembly doit être l’assembly de fournisseur de type lui-même.

Ensuite, ajoutez la documentation XML pour le type. Cette documentation est retardée, autrement dit, calculée à la demande, si le compilateur hôte en a besoin.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

Ensuite, vous ajoutez une propriété statique fournie pour le type de :

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty", 
                                  propertyType = typeof<string>, 
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

L’obtention de cette propriété sera toujours évaluée à la chaîne « Hello ! ». Le `GetterCode` pour la propriété utilise un devis F #, qui représente le code générés par le compilateur hôte pour l’obtention de la propriété. Pour plus d’informations sur les propositions de prix, consultez [Quotations de Code (F #)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).

Ajouter la documentation XML à la propriété.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

Le type fourni désormais joindre la propriété fournie. Vous devez associer un membre fourni à un seul et unique type. Dans le cas contraire, le membre ne sera jamais accessible.

```fsharp
t.AddMember staticProp
```

Maintenant créer un constructeur fourni qui ne prend aucun paramètre.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ], 
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

Le `InvokeCode` pour le constructeur retourne une citation F #, qui représente le code que le compilateur hôte génère lorsque le constructeur est appelé. Par exemple, vous pouvez utiliser le constructeur suivant :

```fsharp
new Type10()
```

Une instance du type fourni sera créée avec les données sous-jacentes « Les données d’objet ». Le code entre guillemets inclut une conversion vers [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) , car ce type est la suppression de ce le type fourni (que vous avez spécifié lorsque vous avez déclaré le type fourni).

Ajouter la documentation XML pour le constructeur et ajoutez le constructeur fourni pour le type fourni :

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Créer un deuxième constructeur fourni qui prend un paramètre :

```fsharp
let ctor2 = 
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ], 
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

Le `InvokeCode` pour le constructeur retourne à nouveau un devis F #, qui représente le code généré par le compilateur hôte pour un appel à la méthode. Par exemple, vous pouvez utiliser le constructeur suivant :

```fsharp
new Type10("ten")
```

Une instance du type fourni est créée avec les données sous-jacentes « 10 ». Vous avez peut-être déjà remarqué que le `InvokeCode` fonction retourne une citation. L’entrée de cette fonction est une liste d’expressions, un par un paramètre de constructeur. Dans ce cas, une expression qui représente la valeur de paramètre est disponible dans `args.[0]`. Le code d’un appel au constructeur force la valeur de retournée dans le type effacée `obj`. Après avoir ajouté le deuxième constructeur fourni pour le type, vous créez une propriété d’instance fourni :

```fsharp
let instanceProp = 
    ProvidedProperty(propertyName = "InstanceProperty", 
                     propertyType = typeof<int>, 
                     getterCode= (fun args -> 
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

L’obtention de cette propriété retourne la longueur de la chaîne, qui est l’objet de la représentation. Le `GetterCode` propriété retourne une citation F # qui spécifie le code que le compilateur hôte génère pour obtenir la propriété. Comme `InvokeCode`, le `GetterCode` fonction retourne une citation. Le compilateur hôte appelle cette fonction avec une liste d’arguments. Dans ce cas, les arguments sont simplement l’expression unique qui représente l’instance sur laquelle l’accesseur Get est appelée, auquel vous pouvez accéder à l’aide de `args.[0]`. L’implémentation de `GetterCode` puis jonctions de fil dans la soumission du résultat du type effacées `obj`, et un cast est utilisé pour satisfaire le mécanisme du compilateur pour la vérification des types que l’objet est une chaîne. La partie suivante de `makeOneProvidedType` fournit une méthode d’instance avec un paramètre.

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

Enfin, créez un type imbriqué qui contient les propriétés imbriquées 100. Imbriqué de la création de ce type et ses propriétés est retardé, autrement dit, calculée à la demande.

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

### <a name="details-about-erased-provided-types"></a>Pour plus d’informations sur les Types fournis effacés

L’exemple de cette section fournit uniquement *effacées des types fournis*, qui sont particulièrement utile dans les situations suivantes :

- Lorsque vous écrivez un fournisseur pour un espace d’informations qui contient uniquement les données et les méthodes.

- Lorsque vous écrivez un fournisseur où précis runtime une sémantique de type ne sont pas critique pour l’utilisation pratique de l’espace d’informations.

- Lorsque vous écrivez un fournisseur pour un espace d’informations est trop volumineuse et interconnectés qu’il soit techniquement possible de générer des types .NET réels pour l’espace d’informations.

Dans cet exemple, chaque fournie type est effacé en type `obj`, et toutes les utilisations du type seront affiche en tant que type `obj` dans le code compilé. En fait, les objets sous-jacents dans ces exemples sont des chaînes, mais le type apparaîtra comme `System.Object` dans .NET code compilé. Comme avec toutes les utilisations d’effacement de type, vous pouvez utiliser la conversion boxing explicite, unboxing et de la conversion de compromettre l’effacées types. Dans ce cas, une exception cast non valide peut entraîner lorsque l’objet est utilisé. Un fournisseur runtime peut définir son propre type de représentation privé pour vous protéger contre les représentations sous forme de valeur est false. Impossible de définir des types effacées en F # lui-même. Seuls les types fournis peuvent être effacées. Vous devez comprendre les ramifications, à la fois pratique et sémantique de l’aide des types effacées de votre fournisseur de type ou d’un fournisseur qui fournit effacées types. Un type effacé n’a aucune véritable type .NET. Par conséquent, vous ne pouvez pas faire précise sur le type, et vous pourrez compromettre types effacées si vous utilisez des casts de runtime et d’autres techniques qui s’appuient sur la sémantique de type exacte du runtime. Subversion de types effacées entraîne souvent des exceptions de cast de type lors de l’exécution.


### <a name="choosing-representations-for-erased-provided-types"></a>Choix des représentations pour effacer fourni Types

Pour certaines utilisations des types fournis effacés, aucune représentation n’est nécessaire. Par exemple, l’effacées fourni type peut contenir uniquement des propriétés statiques et des membres et aucun constructeur, et aucune méthode ou propriété ne retourne une instance du type. Si vous pouvez joindre des instances d’un élément effacé le type fourni, vous devez prendre en compte les questions suivantes :

**Quelle est la suppression d’un type fourni ?**

- L’effacement d’un type fourni est la façon dont le type s’affiche dans le code .NET compilé.

- L’effacement d’un type de classe effacées fourni est toujours le premier non effacé type de base dans la chaîne d’héritage du type.

- L’effacement d’un type interface effacées fournie est toujours `System.Object`.

**Quelles sont les représentations sous forme d’un type fourni ?**

- Le jeu d’objets possible pour un type fourni effacé sont appelés ses représentations. Dans l’exemple dans ce document, les représentations sous forme de tous les fourni l’effacées types `Type1..Type100` sont toujours des objets de chaîne.

Toutes les représentations sous forme d’un type fourni doit être compatible avec l’effacement du type fourni. (Dans le cas contraire, le compilateur F # génère une erreur pour une utilisation du fournisseur de type, ou du code non vérifiable .NET qui n’est pas valide est généré. Un fournisseur de type n’est pas valide si elle retourne le code qui donne une représentation qui n’est pas valide.)

Vous pouvez choisir une représentation pour les objets fournis à l’aide d’une des méthodes suivantes, qui sont très courantes :

- Si vous fournissez simplement un wrapper fortement typé sur un type .NET existant, il est souvent logique pour votre type effacer à ce type, utilisez des instances de ce type en tant que représentations, ou les deux. Cette approche est appropriée lorsque la plupart des méthodes existantes de ce type sont toujours judicieux lors de l’utilisation de la version fortement typée.

- Si vous souhaitez créer une API qui diffère considérablement de toute API .NET existant, il est judicieux de créer des types de runtime qui seront l’effacement de type et les représentations sous forme de types fournis.

L’exemple dans ce document utilise des chaînes en tant que représentations d’objets fournis. Souvent, il peut être approprié d’utiliser d’autres objets pour les représentations. Par exemple, vous pouvez utiliser un dictionnaire en tant qu’un jeu de propriétés :

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

En guise d’alternative, vous pouvez définir un type dans votre fournisseur de type qui sera utilisé lors de l’exécution pour former la représentation, ainsi que d’un ou plusieurs opérations d’exécution :

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

Membres fournis peuvent ensuite construire des instances de ce type d’objet :

```fsharp
ProvidedConstructor(parameters = [], 
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

Dans ce cas, vous pouvez utiliser (facultatif) ce type en tant que l’effacement de type en spécifiant ce type comme le `baseType` lors de la construction du `ProvidedTypeDefinition`:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Leçons clés

La section précédente décrit comment créer un fournisseur de type effacement simple qui fournit une gamme de types, propriétés et méthodes. Également, cette section explique le concept d’effacement de type, y compris des avantages et les inconvénients de fournir des types effacées à partir d’un fournisseur de type et décrit les représentations sous forme de types effacées.


## <a name="a-type-provider-that-uses-static-parameters"></a>Un fournisseur de Type qui utilise les paramètres statiques

La possibilité de paramétrer des fournisseurs de type en données statiques autorise de nombreux scénarios intéressants, même dans les cas où le fournisseur n’a pas besoin accéder aux données locales ou distantes. Dans cette section, vous allez apprendre quelques techniques de base pour assembler un tel fournisseur.


### <a name="type-checked-regex-provider"></a>Type contrôlé Regex fournisseur

Imaginez que vous souhaitez implémenter un fournisseur de type pour les expressions régulières qui encapsule le .NET <xref:System.Text.RegularExpressions.Regex> bibliothèques dans une interface qui fournit des garanties de compilation suivantes :

- Vérification d’une expression régulière valide.

- Fournit des propriétés nommées de correspondances qui sont basées sur les noms de groupe dans l’expression régulière.

Cette section vous montre comment utiliser des fournisseurs de type pour créer un `RegexTyped` de type que le modèle d’expression régulière est pour offrir ces avantages. Le compilateur signale une erreur si le modèle fourni n’est pas valide, le fournisseur de type peut extraire les groupes à partir du modèle afin que vous pouvez y accéder à l’aide de ces propriétés sur les correspondances. Lorsque vous concevez un fournisseur de type, vous devez envisager l’aspect de son API exposée aux utilisateurs finaux et comment cette conception se traduit en code .NET. L’exemple suivant montre comment utiliser une telle API pour obtenir les composants de l’indicatif :

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

L’exemple suivant montre comment le fournisseur de type convertit ces appels :

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

Notez les points suivants :

- Le type d’expression régulière standard représente paramétré `RegexTyped` type.

- Le `RegexTyped` constructeur entraîne un appel au constructeur Regex, en passant l’argument de type statique pour le modèle.

- Les résultats de la `Match` méthode sont représentées par la norme <xref:System.Text.RegularExpressions.Match> type.

- Chaque groupe nommé entraîne une propriété fournie, et l’accès à la propriété entraîne une utilisation d’un indexeur sur une correspondance `Groups` collection.

Le code suivant est le cœur de la logique pour implémenter ce type de fournisseur, et cet exemple omet l’ajout de tous les membres pour le type fourni. Pour plus d’informations sur chaque membre ajouté, consultez la section correspondante plus loin dans cette rubrique. Pour le code complet, téléchargez l’exemple à partir de la [F # 3.0 exemple Pack](https://fsharp3sample.codeplex.com) sur le site Web Codeplex.

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

Notez les points suivants :

- Le fournisseur de type accepte deux paramètres statiques : le `pattern`, qui est obligatoire et le `options`, lesquels sont facultatifs (étant donné que la valeur par défaut est fournie).

- Une fois les arguments statiques sont fournis, vous créez une instance de l’expression régulière. Cette instance lève une exception si l’expression régulière est incorrect, et cette erreur ne sera signalée aux utilisateurs.

- Dans la `DefineStaticParameters` rappel, vous définissez le type qui sera renvoyé après les arguments sont fournis.

- Ce code définit `HideObjectMethods` sur true afin que l’expérience IntelliSense restera simplifiée. Cet attribut provoque la `Equals`, `GetHashCode`, `Finalize`, et `GetType` membres à supprimer dans les listes IntelliSense pour un objet fourni.

- Vous utilisez `obj` comme type de base de la méthode, mais que vous allez utiliser un `Regex` objet en tant que la représentation sous forme de runtime de ce type, comme le montre l’exemple suivant.

- L’appel à la `Regex` constructeur lève une <xref:System.ArgumentException> quand une expression régulière n’est pas valide. Le compilateur intercepte cette exception et signale un message d’erreur à l’utilisateur au moment de la compilation ou dans l’éditeur Visual Studio. Cette exception permet à des expressions régulières pour être validé sans exécution d’une application.

Le type défini ci-dessus n’est pas utile encore, car il ne contient pas les méthodes explicites ou les propriétés. Tout d’abord, ajoutez un mappage statique `IsMatch` méthode :

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

Le code précédent définit une méthode `IsMatch`, qui prend une chaîne comme entrée et retourne un `bool`. La seule difficulté consiste à utiliser le `args` argument dans le `InvokeCode` définition. Dans cet exemple, `args` est une liste de soumissions qui représente les arguments de cette méthode. Si la méthode est une méthode d’instance, le premier argument représente le `this` argument. Toutefois, pour une méthode statique, les arguments sont tout simplement des arguments explicites à la méthode. Notez que le type de la valeur entre guillemets doit correspondre au type de retour spécifié (dans ce cas, `bool`). Notez également que ce code utilise le `AddXmlDoc` méthode pour s’assurer que la méthode fournie a également toute documentation utile, vous pouvez fournir via IntelliSense.

Ensuite, ajoutez une instance de méthode de correspondance. Toutefois, cette méthode doit retourner une valeur d’un `Match` type afin que les groupes sont accessibles de manière fortement typée. Par conséquent, vous déclarez le `Match` type. Étant donné que ce type varie selon le modèle a été fourni comme argument statique, ce type doit être imbriqué dans la définition de type paramétré :

```fsharp
let matchTy = 
    ProvidedTypeDefinition(
        "MatchType", 
        baseType = Some baseTy, 
        hideObjectMethods = true)

ty.AddMember matchTy
```

Vous montre ensuite comment ajouter une propriété du type de correspondance pour chaque groupe. Lors de l’exécution, une correspondance est représentée comme un <xref:System.Text.RegularExpressions.Match> valeur, par conséquent, le guillemet anglais qui définit la propriété doit utiliser le <xref:System.Text.RegularExpressions.Match.Groups> indexé de propriété pour obtenir le groupe approprié.

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

Là encore, notez que vous ajoutez la documentation XML à la propriété fournie. Notez également une propriété pouvant être lus si un `GetterCode` (fonction) est fournie, et la propriété peut être écrite si un `SetterCode` (fonction) est fournie, la propriété résultante est en lecture seule.

Vous pouvez désormais créer une méthode d’instance qui retourne une valeur de ce `Match` type :

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

Étant donné que vous créez une méthode d’instance, `args.[0]` représente le `RegexTyped` instance sur laquelle la méthode est appelée, et `args.[1]` est l’argument d’entrée.

Enfin, fournissez un constructeur afin que les instances du type fourni peuvent être créées.

```fsharp
let ctor = 
    ProvidedConstructor(
        parameters = [], 
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

Le constructeur efface simplement à la création d’une instance de Regex de .NET standard, qui est à nouveau convertie (boxed) à un objet, car `obj` est l’effacement du type fourni. Avec cette modification, l’utilisation de l’API exemple spécifié précédemment dans la rubrique fonctionne comme prévu. Le code suivant est complet et finale :

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

### <a name="key-lessons"></a>Leçons clés

Cette section explique comment créer un fournisseur de type qui opère sur ses paramètres statiques. Le fournisseur vérifie le paramètre static et fournit des opérations en fonction de sa valeur.


## <a name="a-type-provider-that-is-backed-by-local-data"></a>Un fournisseur de Type qui est sauvegardé par les données locales

Vous pourriez fréquemment des fournisseurs de type pour présenter les API basées sur les paramètres statiques, mais également des informations à partir des systèmes locaux ou distants. Cette section traite des fournisseurs de type qui sont basées sur les données locales, telles que des fichiers de données locaux.


### <a name="simple-csv-file-provider"></a>Fournisseur du fichier CSV simple

À titre d’exemple, considérez un fournisseur de type pour l’accès aux données scientifiques au format de valeurs séparées par des virgules (CSV). Cette section part du principe que les fichiers CSV contient une ligne d’en-tête suivie par les données à virgule flottante, comme l’illustre le tableau suivant :


|Distance (compteur)|Temps (en secondes)|
|----------------|-------------|
|50.0|3.7|
|100.0|5.2|
|150.0|6.4|

Cette section montre comment fournir un type que vous pouvez utiliser pour obtenir des lignes avec un `Distance` propriété de type `float<meter>` et un `Time` propriété de type `float<second>`. Par souci de simplicité, les hypothèses suivantes sont effectuées :

- Les noms d’en-tête sont sans unité ou avoir la forme « Nom (unité) » et ne pas contenir de virgules.

- Les unités sont toutes les unités du système International (SI) en tant que le [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames (Module) (F #)](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) module définit.

- Les unités sont tout simples (par exemple, contrôler) plutôt que composée (par exemple, compteur/seconde).

- Toutes les colonnes contiennent des données à virgule flottante.

Un fournisseur plus complète serait assouplir ces restrictions.

Là encore, la première étape consiste à prendre en compte l’aspect de l’API. Étant donné un `info.csv` fichier avec le contenu du tableau précédent (au format séparées par des virgules), les utilisateurs du fournisseur doivent être en mesure d’écrire du code qui ressemble à l’exemple suivant :

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

Dans ce cas, le compilateur doit convertir ces appels quelque chose comme l’exemple suivant :

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

La traduction optimale nécessitera le fournisseur de type définir un réel `CsvFile` type dans assembly du fournisseur de type. Fournisseurs de type reposent souvent sur quelques types d’assistance et des méthodes pour encapsuler la logique importante. Étant donné que les mesures sont effacés au moment de l’exécution, vous pouvez utiliser un `float[]` comme type effacé pour une ligne. Le compilateur traite les différentes colonnes comme ayant des types de mesure différente. Par exemple, la première colonne dans notre exemple a type `float<meter>`, et le deuxième `float<second>`. Toutefois, la représentation sous forme d’effacées peut rester simple.

Le code suivant illustre le cœur de l’implémentation.

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

Notez les points suivants concernant l’implémentation :

- Constructeurs surchargés autorisent le fichier d’origine ou qui a un schéma identique à lire. Ce modèle est courant lorsque vous écrivez un fournisseur de type pour les sources de données locales ou distantes, et ce modèle permet à un fichier local à utiliser comme modèle pour les données distantes.

- Vous pouvez utiliser la [TypeProviderConfig](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) valeur qui est passée au constructeur de fournisseur de type pour résoudre les noms de fichiers relatifs.

- Vous pouvez utiliser la `AddDefinitionLocation` méthode pour définir l’emplacement des propriétés fournies. Par conséquent, si vous utilisez `Go To Definition` sur une propriété fournie, le fichier CSV s’ouvre dans Visual Studio.

- Vous pouvez utiliser la `ProvidedMeasureBuilder` type pour rechercher les unités SI et pour générer les `float<_>` types.

### <a name="key-lessons"></a>Leçons clés

Cette section explique comment créer un fournisseur de type pour une source de données locale avec un schéma simple qui est contenu dans la source de données.


## <a name="going-further"></a>Aller plus loin

Les sections suivantes contiennent des suggestions pour approfondir ce sujet.


### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Examiner le Code compilé pour les Types effacés

Pour vous donner une idée de la façon dont l’utilisation du fournisseur de type correspond au code qui est émis, examinez la fonction suivante à l’aide de la `HelloWorldTypeProvider` qui est utilisée plus haut dans cette rubrique.

```fsharp
let function1 () = 
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Voici une image du code qui en résulte décompilé en utilisant ildasm.exe :

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

Comme le montre l’exemple, toutes les mentions de type `Type1` et `InstanceProperty` propriété ont été effacées, en laissant uniquement les opérations sur les types de runtime impliqués.


### <a name="design-and-naming-conventions-for-type-providers"></a>Conception et les Conventions d’affectation de noms pour les fournisseurs de Type
Observez les conventions suivantes lors de la création de fournisseurs de type.

**Fournisseurs de protocoles de connexion** en général, les noms de la plupart des DLL de fournisseur pour des protocoles de connexion de données et de service, telles que les connexions OData ou SQL, doivent se terminer dans `TypeProvider` ou `TypeProviders`. Par exemple, utilisez un nom de la DLL qui ressemble à la chaîne suivante :

```
  Fabrikam.Management.BasicTypeProviders.dll
```

Vérifiez que vos types fournis sont membres de l’espace de noms correspondante et indiquent le protocole de connexion que vous avez implémentée :

```
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**Utilitaire de fournisseurs pour le codage général**.  Pour un fournisseur type utilitaire tel que des expressions régulières, le fournisseur de type peut être dans une bibliothèque de base, comme le montre l’exemple suivant :

```fsharp
  #r "Fabrikam.Core.Text.Utilities.dll"
```

Dans ce cas, le type fourni apparaîtrait à un moment approprié selon les conventions de conception .NET normales :

```fsharp
  open Fabrikam.Core.Text.RegexTyped
  
  let regex = new RegexTyped<"a+b+a+b+">()
```

**Sources de données singleton**. Certains fournisseurs de type se connecter à une source de données dédié et fournissent des données uniquement. Dans ce cas, vous devez supprimer la `TypeProvider` suffixe et utiliser les conventions normales d’affectation de noms .NET :

```fsharp
#r "Fabrikam.Data.Freebase.dll"
  
let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Pour plus d’informations, consultez le `GetConnection` concevoir convention qui est décrite plus loin dans cette rubrique.


### <a name="design-patterns-for-type-providers"></a>Modèles de conception pour les fournisseurs de Type

Les sections suivantes décrivent les modèles de conception que vous pouvez utiliser lors de la création de fournisseurs de type.


#### <a name="the-getconnection-design-pattern"></a>Le modèle de conception de GetConnection
La plupart des fournisseurs de type doivent être écrit pour utiliser la `GetConnection` modèle qui est utilisé par les fournisseurs de type dans FSharp.Data.TypeProviders.dll, comme le montre l’exemple suivant :

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Fournisseurs de type soutenues par les Services et les données distantes

Avant de créer un fournisseur de type qui est sauvegardé par les services et les données distantes, vous devez envisager une gamme de problèmes inhérents à la programmation connectée. Ces problèmes incluent les points suivants :

- Mappage de schéma

- activité et invalidation en cas de modification de schéma

- la mise en cache de schéma

- implémentations asynchrones d’opérations d’accès aux données

- prise en charge des requêtes, y compris les requêtes LINQ

- informations d’identification et l’authentification

Cette rubrique n’Explorer davantage ces problèmes.

### <a name="additional-authoring-techniques"></a>Autres Techniques de création

Lorsque vous écrivez vos propres fournisseurs de type, vous souhaiterez probablement utiliser les techniques supplémentaires suivantes.

### <a name="creating-types-and-members-on-demand"></a>Création de Types et membres à la demande

L’API ProvidedType a différée des versions de AddMember.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Ces versions sont utilisées pour créer des espaces à la demande de types.

### <a name="providing-array-types-and-generic-type-instantiations"></a>En fournissant des types de tableau et les instanciations de Type générique

Assurez-vous de membres fournies (dont les signatures incluent les types tableau, types byref et instanciations de types génériques) à l’aide du vecteur normal `MakeArrayType`, `MakePointerType`, et `MakeGenericType` sur n’importe quelle instance de <xref:System.Type>, y compris `ProvidedTypeDefinitions`.

> [!NOTE]
> Dans certains cas vous devrez peut-être utiliser l’application d’assistance dans `ProvidedTypeBuilder.MakeGenericType`.  Consultez le [documentation du SDK de fournisseur de Type](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations) pour plus d’informations.

### <a name="providing-unit-of-measure-annotations"></a>Fournir l’unité de mesure Annotations

L’API ProvidedTypes fournit des Assistants pour fournir des annotations de mesure. Par exemple, pour fournir le type `float<kg>`, utilisez le code suivant :

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Pour fournir le type `Nullable<decimal<kg/m^2>>`, utilisez le code suivant :

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>L’accès aux ressources de projet Local ou le Script Local

Chaque instance d’un fournisseur de type peut être accordée à un `TypeProviderConfig` valeur pendant la construction. Cette valeur contient le dossier « résolution » pour le fournisseur (autrement dit, le dossier de projet pour la compilation ou le répertoire qui contient un script), la liste des assemblys référencés et d’autres informations.

### <a name="invalidation"></a>Invalidation

Fournisseurs peuvent déclencher des signaux d’invalidation pour notifier le service de langage F # qui les hypothèses de schéma a peut-être été modifié. En cas d’invalidation, un typecheck est réexécutée si le fournisseur est hébergé dans Visual Studio. Ce signal est ignoré lorsque le fournisseur est hébergé dans F # Interactive ou par le compilateur F # (fsc.exe).

### <a name="caching-schema-information"></a>La mise en cache des informations de schéma

Fournisseurs souvent doivent mettre en cache l’accès aux informations de schéma. Les données mises en cache doivent être stockées à l’aide d’un nom de fichier est fourni comme paramètre statique ou en tant que données de l’utilisateur. Un exemple de mise en cache de schéma est le `LocalSchemaFile` paramètre dans les fournisseurs de type dans le `FSharp.Data.TypeProviders` assembly. Dans l’implémentation de ces fournisseurs, ce paramètre statique dirige le fournisseur de type à utiliser les informations de schéma dans le fichier local spécifié au lieu de l’accès à la source de données sur le réseau. Pour utiliser les informations de schéma mis en cache, vous devez également définir le paramètre static `ForceUpdate` à `false`. Vous pouvez utiliser une technique similaire pour activer l’accès aux données en ligne et hors connexion.

### <a name="backing-assembly"></a>Assembly de stockage

Lorsque vous compilez un `.dll` ou `.exe` de fichiers, le fichier de sauvegarde pour les types générés est statiquement liée dans l’assembly résultant. Ce lien est créé en copiant les définitions de type (Microsoft Intermediate Language) et toutes les ressources managées à partir de l’assembly de stockage dans l’assembly final. Lorsque vous utilisez F # Interactive, le fichier de sauvegarde n’est pas copié et est chargé à la place directement dans le processus interactif F #.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Exceptions et des Diagnostics à partir des fournisseurs de Type

Toutes les utilisations de tous les membres de types fournis peuvent lever des exceptions. Dans tous les cas, si un fournisseur de type lève une exception, le compilateur hôte attributs de l’erreur à un fournisseur de type spécifiques.

- Exceptions de fournisseur de type ne génère jamais dans les erreurs internes du compilateur.

- Fournisseurs de type ne peut pas signaler les avertissements.

- Lorsqu’un fournisseur de type est hébergé dans le compilateur F #, un environnement de développement F # ou F # Interactive, toutes les exceptions de ce fournisseur sont interceptées. La propriété de Message est toujours le texte d’erreur, et aucune trace de la pile s’affiche. Si vous souhaitez lever une exception, vous pouvez lever les exemples suivants : `System.NotSupportedException`, `System.IO.IOException`, `System.Exception`.

#### <a name="providing-generated-types"></a>En fournissant les Types générés

Jusqu'à présent, ce document a expliqué comment fournir des types effacées. Vous pouvez également utiliser le mécanisme de fournisseur de type en F # pour fournir des types générés, qui sont ajoutés en tant que définitions de type .NET réelles dans le programme de l’utilisateur. Vous devez faire référence à généré fourni des types à l’aide d’une définition de type.

```fsharp
open Microsoft.FSharp.TypeProviders 

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

Le code d’assistance ProvidedTypes-0,2 qui fait partie de la version 3.0) (F # prend uniquement en charge limitée pour fournir des types générés. Les instructions suivantes doivent être remplies pour une définition de type généré :

- `isErased` doit avoir la valeur `false`.

- Le type généré doit être ajouté à un nouvellement construit `ProvidedAssembly()`, qui représente un conteneur pour les fragments de code généré.

- Le fournisseur doit disposer d’un assembly qui a un fichier .dll de stockage réel .NET avec un fichier .dll correspondant sur le disque.


## <a name="rules-and-limitations"></a>Règles et Limitations

Lorsque vous écrivez des fournisseurs de type, gardez les règles suivantes et les limitations à l’esprit.


### <a name="provided-types-must-be-reachable"></a>Types fournis doivent être accessibles

Tous les fourni types doivent être accessibles à partir des types non imbriqués. Les types non imbriqués figurent dans l’appel à la `TypeProviderForNamespaces` constructeur ou un appel à `AddNamespace`. Par exemple, si le fournisseur fournit un type `StaticClass.P : T`, vous devez vous assurer que T est un type non imbriqué ou imbriqués sous un.

Par exemple, certains fournisseurs ont une classe statique comme `DataTypes` qui contiennent ces `T1, T2, T3, ...` types. Sinon, l’erreur indique qu’une référence au type T dans l’assembly A a été trouvée, mais le type n’a pas pu être trouvé dans cet assembly. Si cette erreur s’affiche, vérifiez que tous les sous-types votre peuvent être atteint à partir des types de fournisseur. Remarque : Ces `T1, T2, T3...` types sont appelés les *à la volée* types. Pensez à les placer dans un espace de noms accessible ou d’un type de parent.

### <a name="limitations-of-the-type-provider-mechanism"></a>Limitations du mécanisme de fournisseur de Type

Le mécanisme de fournisseur de type en F # présente les limitations suivantes :

- L’infrastructure sous-jacente pour les fournisseurs de type en F # ne prend pas en charge fournie générique types ou méthodes génériques fournies.

- Le mécanisme ne prend pas en charge les types imbriqués avec des paramètres statiques.

## <a name="development-tips"></a>Conseils de développement

Vous trouverez les conseils suivants utiles pendant le processus de développement.

### <a name="run-two-instances-of-visual-studio"></a>Exécutez deux Instances de Visual Studio

Vous pouvez développer le fournisseur de type dans une seule instance et le fournisseur de test dans l’autre, car le test IDE effectuera un verrou sur le fichier .dll qui empêche que le fournisseur de type en cours de reconstruction. Par conséquent, vous devez fermer la deuxième instance de Visual Studio pendant que le fournisseur est créé dans la première instance, puis vous devez rouvrir la deuxième instance une fois le fournisseur est créé.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Déboguer les fournisseurs de type à l’aide d’appels de fsc.exe

Vous pouvez appeler des fournisseurs de type à l’aide des outils suivants :

- FSC.exe (F # de la ligne de commande du compilateur)

- fsi.exe (F # Interactive du compilateur)

- devenv.exe (Visual Studio)

Vous pouvez souvent de déboguer plus facilement les fournisseurs de type à l’aide de fsc.exe sur un fichier de script de test (par exemple, script.fsx). Vous pouvez lancer un débogueur à partir d’une invite de commandes.

```
  devenv /debugexe fsc.exe script.fsx
```

  Vous pouvez utiliser la journalisation de l’impression à stdout.


## <a name="see-also"></a>Voir aussi

* [Fournisseurs de type](index.md)

* [Le Kit de développement logiciel de fournisseur de Type](https://github.com/fsprojects/FSharp.TypeProviders.SDK)


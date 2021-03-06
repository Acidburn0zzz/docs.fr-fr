---
title: Rendre une image plus facile à déboguer dans .NET
description: Découvrez comment configurer une image exécutable pour un débogage simplifié à l’aide des IDE bascule et options de ligne de commande.
ms.date: 08/30/2018
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bab707afb059d4fcbd46a9ee54edead991be523
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362009"
---
# <a name="making-an-image-easier-to-debug-in-net"></a>Rendre une image plus facile à déboguer dans .NET

Lors de la compilation de code non managé, vous pouvez configurer une image exécutable pour le débogage en définissant des commutateurs ou des options de ligne de commande de l’IDE. Par exemple, vous pouvez utiliser l’option de ligne de commande /**Zi** dans Visual C++ pour lui demander de produire des fichiers de symboles de débogage (extension de fichier .pdb). De même, l’option de ligne de commande /**Od** indique au compilateur de désactiver l’optimisation. Le code résultant s’exécute plus lentement, mais il est plus facile à déboguer, quand c’est nécessaire.

Lors de la compilation de .NET Framework du code managé, les compilateurs tels que Visual C++, Visual Basic et c# compilent leur programme source en langage intermédiaire Microsoft (MSIL). MSIL est ensuite compilé par JIT, juste avant l’exécution, en code machine natif. Comme avec le code non managé, vous pouvez configurer une image exécutable pour le débogage en définissant des commutateurs ou des options de ligne de commande de l’IDE. Vous pouvez également configurer la compilation JIT pour le débogage de la même façon.

Cette configuration JIT a deux aspects :

- Vous pouvez demander au compilateur JIT de générer des informations de suivi. Ceci permet au débogueur de faire correspondre une chaîne d’instructions MSIL à son équivalent en code machine, et d’effectuer le suivi des emplacements de stockage des variables locales et des arguments de fonction. À compter de .NET Framework version 2.0, le compilateur JIT génère toujours des informations de suivi, il est donc pas nécessaire pour la demande.

- Vous pouvez demander au compilateur JIT ne pas optimiser le code machine résultant.

Normalement, le compilateur qui génère le code MSIL définit ces options du compilateur JIT correctement, en fonction des commutateurs IDE ou des options de ligne de commande que vous spécifiez, par exemple, /**Od**.

Dans certains cas, vous pouvez changer le comportement du compilateur JIT afin que le code machine généré soit plus facile à déboguer. Par exemple, vous pouvez générer des informations de suivi JIT pour une version commerciale ou pour l’optimisation du contrôle. Vous pouvez faire cela avec un fichier d’initialisation (.ini).

Par exemple, si l’assembly que vous souhaitez déboguer est appelé *MyApp.exe*, vous pouvez ensuite créer un fichier texte nommé *MyApp.ini*, dans le même dossier que *MyApp.exe*, qui contient Ces trois lignes :

```ini
[.NET Framework Debugging Control]
GenerateTrackingInfo=1
AllowOptimize=0
```

Vous pouvez définir la valeur de chaque option sur 0 ou 1. Les options absentes ont 0 comme valeur par défaut. La définition de `GenerateTrackingInfo` sur 1 et de `AllowOptimize` sur 0 est ce qui permet le débogage le plus facile.

À compter de .NET Framework version 2.0, le compilateur JIT génère toujours des informations de suivi, quel que soit la valeur de `GenerateTrackingInfo`; Toutefois, le `AllowOptimize` valeur a toujours un effet. Quand vous utilisez le générateur d’images natives [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) pour précompiler l’image native sans optimisation, le fichier .ini doit être présent dans le dossier cible avec `AllowOptimize=0` quand Ngen.exe s’exécute. Si vous avez précompilé un assembly sans optimisation, vous devez supprimer le code précompilé à l’aide de NGen.exe **/ désinstallation** option avant de réexécuter Ngen.exe pour précompiler le code de manière optimisée. Si le fichier .ini n’est pas présent dans le dossier, Ngen.exe précompile par défaut le code de manière optimisée.

<xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> contrôle les paramètres pour un assembly. **DebuggableAttribute** comprend deux champs qui contrôlent si le compilateur JIT doit optimiser et/ou générer des informations de suivi. À compter de .NET Framework version 2.0, le compilateur JIT génère toujours des informations de suivi.

Pour une version commerciale, les compilateurs ne définissent les **DebuggableAttribute**. Par défaut, le compilateur JIT génère les meilleures performances, plus difficiles à déboguer le code machine. L’activation du suivi dans JIT diminue légèrement les performances, tandis que la désactivation de l’optimisation les réduit considérablement.

**DebuggableAttribute** s’applique à la totalité d’un assembly, et non pas à des modules individuels dans l’assembly. Les outils de développement doivent donc attacher des attributs personnalisés au jeton de métadonnées de l’assembly si un assembly a déjà été créé, ou à la classe appelée **System.Runtime.CompilerServices.AssemblyAttributesGoHere**. L’outil ALink promeut ensuite ces **DebuggableAttribute** attributs à partir de chaque module à l’assembly qu’ils deviennent une partie de. S’il existe un conflit, l’opération ALink échoue.

> [!NOTE]
> Dans la version 1.0 du .NET Framework, le compilateur Microsoft Visual C++ ajoute **DebuggableAttribute** quand les options du compilateur **/clr** et **/Zi** sont spécifiées. Dans la version 1.1 du .NET Framework, vous devez ajouter le **DebuggableAttribute** manuellement dans votre code ou en utilisant le **/ASSEMBLYDEBUG** option de l’éditeur de liens.

## <a name="see-also"></a>Voir aussi

- [Débogage, traçage et profilage](../../../docs/framework/debug-trace-profile/index.md)
- [Activation du débogage juste-à-temps](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)
- [Activation du profilage](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s5ec0es1(v=vs.100))

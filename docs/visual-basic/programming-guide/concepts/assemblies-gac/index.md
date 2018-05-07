---
title: Assemblys et le Global Assembly Cache (Visual Basic)
ms.date: 07/20/2015
ms.assetid: fcf78ff1-f1ab-4a5d-b6d8-00d2046b6c80
ms.openlocfilehash: 6d1692d6b62e1f1f3a8f979d3de242003f034ed5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="assemblies-and-the-global-assembly-cache-visual-basic"></a>Assemblys et le Global Assembly Cache (Visual Basic)
Les assemblys constituent l’unité fondamentale dans le déploiement, la gestion de version, la portée d’activation et les autorisations de sécurité d’une application .NET. Les assemblys prennent la forme d’un fichier exécutable (.exe) ou d’un fichier de bibliothèque de liens dynamiques (.dll) et sont les blocs de construction du .NET Framework. Ils fournissent au Common Language Runtime les informations dont il a besoin pour connaître les implémentations de type. Vous pouvez comparer un assembly à une collection de types et de ressources conçus pour opérer ensemble et former une unité logique de fonctionnalité.  
  
 Les assemblys peuvent contenir un ou plusieurs modules. Par exemple, les projets plus importants peuvent être planifiés de sorte que plusieurs développeurs individuels travaillent sur des modules distincts, qui se regroupent pour créer un assembly unique. Pour plus d’informations sur les modules, consultez la rubrique [Comment : générer un assembly multifichier](../../../../framework/app-domains/how-to-build-a-multifile-assembly.md).  
  
 Les assemblys ont les propriétés suivantes :  
  
-   Les assemblys sont implémentés en tant que fichiers .exe ou .dll.  
  
-   Vous pouvez partager un assembly entre des applications en le plaçant dans le Global Assembly Cache. Les assemblys doivent avoir un nom fort avant d’être inclus dans le GAC. Pour plus d’informations, consultez [Assemblys avec nom fort](../../../../framework/app-domains/strong-named-assemblies.md).  
  
-   Les assemblys sont chargés en mémoire uniquement s’ils sont requis. S’ils ne sont pas utilisés, ils ne sont pas chargés. Cela signifie que les assemblys peuvent être un moyen efficace pour gérer les ressources dans les grands projets.  
  
-   Vous pouvez obtenir par programme des informations sur un assembly à l’aide de la réflexion. Pour plus d’informations, consultez la page [Réflexion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).  
  
-   Si vous voulez charger un assembly seulement pour l’inspecter, utilisez une méthode comme <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>.  
  
## <a name="assembly-manifest"></a>Manifeste d'assembly  
 Tous les assemblys contiennent un *manifeste d’assembly*. Semblable à une table des matières, le manifeste d’assembly contient les éléments suivants :  
  
-   L’identité de l’assembly (nom et version).  
  
-   Une table de fichiers décrivant tous les autres fichiers qui composent l’assembly, par exemple, les autres assemblys que vous avez créés et qui sont utilisés par votre fichier .exe ou .dll, ou même des fichiers bitmap ou Readme.  
  
-   Une *liste de référence de l’assembly*, qui est une liste de toutes les dépendances externes, fichiers .dll ou autres, nécessaires à votre application qui ont été créés par quelqu’un d’autre. Les références de l’assembly contiennent des références aux objets globaux et privés. Les objets globaux résident dans le GAC, une zone disponible pour d’autres applications, qui est comparable au répertoire System32. L’espace de noms <xref:Microsoft.VisualBasic?displayProperty=nameWithType> est un exemple d’un assembly dans le Global Assembly Cache. Les objets privés doivent être dans un répertoire au même niveau ou à un niveau inférieur que celui du répertoire dans lequel votre application est installée.  
  
 Étant donné que les assemblys contiennent des informations sur le contenu, le contrôle de version et les dépendances, les applications créées avec Visual Basic n’utilisent pas les valeurs de registre Windows pour fonctionner correctement. Les assemblys réduisent les conflits de fichiers .dll et rendent vos applications plus fiables et plus faciles à déployer. Dans de nombreux cas, vous pouvez installer une application .NET simplement en copiant ses fichiers sur l’ordinateur cible.  
  
 Pour plus d’informations, consultez [Manifeste d’assembly](../../../../framework/app-domains/assembly-manifest.md).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Ajout d’une référence à un assembly  
 Pour utiliser un assembly, vous devez y ajouter une référence. Ensuite, vous devez utiliser [l’instruction Imports](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) pour choisir l’espace de noms des éléments que vous souhaitez utiliser. Une fois qu’un assembly est référencé et importé, toutes les classes, propriétés, méthodes accessibles et les autres membres de ses espaces de noms sont disponibles pour votre application comme si leur code faisait partie de votre fichier source.  
  
## <a name="creating-an-assembly"></a>Création d’un assembly  
 Compilez votre application en la générant à partir de la ligne de commande à l’aide du compilateur de ligne de commande. Pour plus d’informations sur la création d’assemblys à partir de la ligne de commande, consultez [Génération à partir de la ligne de commande](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
> [!NOTE]
>  Pour générer un assembly dans Visual Studio, dans le menu **Générer**, choisissez **Générer**.  
  
## <a name="see-also"></a>Voir aussi  
 [Assemblys dans le Common Language Runtime](../../../../framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Assemblys friend (Visual Basic)](friend-assemblies.md)  
 [Comment : partager un Assembly avec d’autres Applications (Visual Basic)](how-to-share-an-assembly-with-other-applications.md)  
 [Comment : charger et décharger des assemblys (Visual Basic)](how-to-load-and-unload-assemblies.md)  
 [Comment : déterminer si un fichier est un Assembly (Visual Basic)](how-to-determine-if-a-file-is-an-assembly.md)  
 [Comment : créer et utiliser des assemblys à l’aide de la ligne de commande (Visual Basic)](how-to-create-and-use-assemblies-using-the-command-line.md)  
 [Procédure pas à pas : Incorporation de Types provenant d’assemblys managés dans Visual Studio (Visual Basic)](walkthrough-embedding-types-from-managed-assemblies-in-vs.md)  
 [Procédure pas à pas : incorporation d’informations de type provenant d’assemblys Microsoft Office dans Visual Studio (Visual Basic)](walkthrough-embedding-type-information-from-microsoft-office-assemblies-in-vs.md)

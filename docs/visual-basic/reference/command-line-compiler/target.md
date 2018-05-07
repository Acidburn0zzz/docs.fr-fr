---
title: -target (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf47b24446656a539400c825f3332a70d211dad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="-target-visual-basic"></a>-target (Visual Basic)
Spécifie le format de sortie du compilateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Notes  
 Le tableau suivant résume l’effet de la `-target` option.  
  
|**Option**|**Comportement**|  
|----------------|------------------|  
|`-target:exe`|Indique au compilateur de créer une application console exécutable.<br /><br /> Cette option est la valeur par défaut lorsqu’aucun `-target` option est spécifiée. Le fichier exécutable est créé avec l’extension .exe.<br /><br /> Sauf indication contraire avec les `/out` option, le nom de fichier de sortie prend le nom du fichier d’entrée qui contient le `Sub Main` procédure.<br /><br /> Seul `Sub Main` procédure est requise dans les fichiers de code source qui sont compilés dans un fichier .exe. Utilisez le `-main` option du compilateur pour spécifier la classe qui contient le `Sub Main` procédure.|  
|`-target:library`|Indique au compilateur créer une bibliothèque de liens dynamiques (DLL).<br /><br /> Le fichier de bibliothèque de liens dynamiques est créé avec l’extension .dll.<br /><br /> Sauf indication contraire avec les `-out` option, le nom de fichier de sortie prend le nom du premier fichier d’entrée.<br /><br /> Lorsque vous générez une DLL, un `Sub Main` procédure n’est pas nécessaire.|  
|`-target:module`|Indique au compilateur générer un module qui peut être ajouté à un assembly.<br /><br /> Le fichier de sortie est créé avec une extension de fichier .netmodule.<br /><br /> Le common language runtime .NET ne peut pas charger un fichier qui ne dispose pas d’un assembly. Toutefois, vous pouvez incorporer un fichier de ce type dans le manifeste d’assembly d’un assembly à l’aide de `-reference`.<br /><br /> Lorsque le code d’un module référence des types internes dans un autre module, les deux modules doivent être incorporés dans un manifeste d’assembly à l’aide de `-reference`.<br /><br /> Le [- /addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option importe des métadonnées à partir d’un module.|  
|`-target:winexe`|Indique au compilateur créer une application exécutable basé sur Windows.<br /><br /> Le fichier exécutable est créé avec l’extension .exe. Une application basée sur Windows est un qui fournit une interface utilisateur à partir du [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] bibliothèque de classes ou avec les API Win32.<br /><br /> Sauf indication contraire avec les `-out` option, le nom de fichier de sortie prend le nom du fichier d’entrée qui contient le `Sub Main` procédure.<br /><br /> Seul `Sub Main` procédure est requise dans les fichiers de code source qui sont compilés dans un fichier .exe. Dans le cas où votre code possède plus d’une classe qui a un `Sub Main` procédure, utilisez le `-main` option du compilateur pour spécifier la classe qui contient le `Sub Main` procédure|  
|`-target:appcontainerexe`|Indique au compilateur créer une application Windows exécutable qui doit être exécutée dans un conteneur d’application. Ce paramètre est conçu pour être utilisé pour [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] applications.<br /><br /> Le **appcontainerexe** paramètre définit un bit dans le champ des caractéristiques de la [exécutable Portable](http://go.microsoft.com/fwlink/p/?LinkId=236960) fichier. Ce bit indique que l’application doit être exécutée dans un conteneur d’application. Lorsque ce bit est défini, une erreur se produit si le `CreateProcess` méthode tente de lancer l’application en dehors d’un conteneur d’application. À l’exception de ce paramètre, bits **-target : appcontainerexe** équivaut à **-target : winexe**.<br /><br /> Le fichier exécutable est créé avec l’extension .exe.<br /><br /> Sauf indication contraire à l’aide de la `-out` option, le nom de fichier de sortie prend le nom du fichier d’entrée qui contient le `Sub Main` procédure.<br /><br /> Seul `Sub Main` procédure est requise dans les fichiers de code source qui sont compilés dans un fichier .exe. Si votre code contient plus d’une classe qui a un `Sub Main` procédure, utilisez le `-main` option du compilateur pour spécifier la classe qui contient le `Sub Main` procédure|  
|`-target:winmdobj`|Indique au compilateur créer un fichier intermédiaire qui peut être converti dans un fichier binaire (.winmd) de Windows Runtime. Le fichier .winmd peut être consommé par les programmes JavaScript et C++, en plus des programmes de langage managé.<br /><br /> Le fichier intermédiaire est créé avec l’extension .winmdobj.<br /><br /> Sauf indication contraire à l’aide de la `-out` option, le nom de fichier de sortie prend le nom du premier fichier d’entrée. A `Sub Main` procédure n’est pas nécessaire.<br /><br /> Le fichier .winmdobj est conçu pour être utilisé comme entrée pour le <xref:Microsoft.Build.Tasks.WinMDExp> exporter l’outil pour générer un fichier de métadonnées (WinMD) de Windows. Le fichier WinMD a une extension .winmd et contient le code à partir de la bibliothèque d’origine et les définitions de WinMD que JavaScript, C++ et l’utilisation de Windows Runtime.|  
  
 Sauf si vous spécifiez `-target:module`, `-target` provoque un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] manifeste d’assembly à ajouter à un fichier de sortie.  
  
 Chaque instance de Vbc.exe produit, au plus, un fichier de sortie. Si vous spécifiez une option du compilateur, telles que `-out` ou `-target` plusieurs fois, il le compilateur traite est placé entre en vigueur. Plus d’informations sur tous les fichiers d’une compilation sont ajoutées au manifeste. Tous les fichiers de sortie sauf ceux créés avec `-target:module` contiennent les métadonnées de l’assembly dans le manifeste. Utilisez [Ildasm.exe (désassembleur IL)](https://msdn.microsoft.com/library/f7dy01k1) pour afficher les métadonnées dans un fichier de sortie.  
  
 La forme abrégée de `-target` est `-t`.  
  
### <a name="to-set--target-in-the-visual-studio-ide"></a>Pour définir - cible dans l’IDE de Visual Studio  
  
1.  Sélectionnez un projet dans l' **Explorateur de solutions**. Dans le menu **Projet**, cliquez sur **Propriétés**.   
  
2.  Cliquez sur l’onglet **Application** .  
  
3.  Modifiez la valeur dans la **Type d’Application** boîte.  
  
## <a name="example"></a>Exemple  
 Le code suivant compile `in.vb`, en créant `in.dll`:  
  
```console
vbc -target:library in.vb  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Compilateur de ligne de commande de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [-référence (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)  
 [Assemblys et le Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Exemples de lignes de commande de compilation](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 7b9485c1bc2f87ca9f007a4e1ce2f63c055100c1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815977"
---
# <a name="-netcf"></a>-netcf
Configure le compilateur pour cibler le [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-netcf  
```  
  
## <a name="remarks"></a>Notes  
 Le `-netcf` option, le compilateur Visual Basic à cibler le [!INCLUDE[Compact](~/includes/compact-md.md)] au lieu de la version complète [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Fonctionnalités de langage qui sont trouve uniquement dans la version complète [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] est désactivé.  
  
 Le `-netcf` option est conçue pour être utilisée avec [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Les fonctionnalités de langage désactivées par `-netcf` sont les mêmes fonctionnalités de langage pas présentes dans les fichiers ciblés avec `-sdkpath`.  
  
> [!NOTE]
>  Le `-netcf` option n’est pas disponible dans l’environnement de développement Visual Studio ; il est disponible uniquement lors de la compilation à partir de la ligne de commande. Le `-netcf` option est définie lorsqu’un projet smart device de Visual Basic est chargé.  
  
 Le `-netcf` option modifie les fonctionnalités de langage suivantes :  
  
-   Le [fin \<mot clé > instruction](../../../visual-basic/language-reference/statements/end-keyword-statement.md) mot clé, qui termine l’exécution d’un programme, est désactivé. Le programme suivant se compile et s’exécute sans `-netcf` mais échoue au moment de la compilation avec `-netcf`.  
  
     [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]  
  
-   Liaison tardive dans chacun des formulaires est désactivée. Erreurs de compilation sont générées lorsque des scénarios de liaison tardive reconnus sont rencontrées. Le programme suivant se compile et s’exécute sans `-netcf` mais échoue au moment de la compilation avec `-netcf`.  
  
     [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]  
  
-   Le [automatique](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), et [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificateurs sont désactivées. La syntaxe de la [instruction Declare](../../../visual-basic/language-reference/statements/declare-statement.md) instruction est également modifiée pour `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. Le code suivant montre l’effet de `-netcf` sur une compilation.  
  
     [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]  
  
-   À l’aide de mots clés Visual Basic 6.0 qui ont été supprimés à partir de Visual Basic génère une erreur différente lorsque `-netcf` est utilisé. Cela affecte les messages d’erreur pour les mots clés suivants :  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a>Exemple  
 Le code suivant compile `Myfile.vb` avec la [!INCLUDE[Compact](~/includes/compact-md.md)], l’utilisation des versions de mscorlib.dll et de Microsoft.VisualBasic.dll trouvées dans le répertoire d’installation par défaut de la [!INCLUDE[Compact](~/includes/compact-md.md)] sur le lecteur C. En règle générale, vous utiliseriez la version la plus récente de la [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Voir aussi

- [Compilateur de ligne de commande de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Exemples de lignes de commande de compilation](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)

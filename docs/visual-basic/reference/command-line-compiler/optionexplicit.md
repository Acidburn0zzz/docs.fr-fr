---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 54d438541e8840e4394b24b20b4f394ff8cdb820
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332389"
---
# <a name="-optionexplicit"></a>-optionexplicit
Indique au compilateur de signaler des erreurs si les variables ne sont pas déclarées avant leur utilisation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Arguments  
 `+` &#124; `-`  
 Facultatif. Spécifiez `-optionexplicit+` pour exiger la déclaration explicite des variables. Le `-optionexplicit+` option est la valeur par défaut et est identique à `-optionexplicit`. Le `-optionexplicit-` option permet la déclaration implicite de variables.  
  
## <a name="remarks"></a>Notes  
 Si le fichier de code source contient un [instruction Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), l’instruction remplace le `-optionexplicit` paramètre du compilateur de ligne de commande.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Pour définir - optionexplicit dans l’IDE Visual Studio  
  
1. Sélectionnez un projet dans l' **Explorateur de solutions**. Dans le menu **Projet**, cliquez sur **Propriétés**.   
  
2. Cliquez sur l’onglet **Compiler**.  
  
3. Modifiez la valeur dans le **Option Explicit** boîte.  
  
## <a name="example"></a>Exemple  
 Le code suivant compile si `-optionexplicit-` est utilisé.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Voir aussi

- [Compilateur de ligne de commande de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Exemples de lignes de commande de compilation](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Explicit, instruction](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Valeurs par défaut VB, Projets, boîte de dialogue Options](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

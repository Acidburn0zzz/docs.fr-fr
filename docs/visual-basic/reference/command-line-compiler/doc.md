---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b64372d4b6063da85739e939bb33abd4650ecb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651555"
---
# <a name="-doc"></a>-doc
Traite les commentaires de documentation pour les diriger vers un fichier XML.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a>Arguments  
  
|Terme|Définition|  
|---|---|  
|`+` &#124; `-`|Facultatif. Spécification +, ou simplement `-doc`, indique au compilateur de générer des informations de documentation et les placer dans un fichier XML. Spécification de `-` est l’équivalent de ne pas spécifier `-doc`, à l’origine d’aucune information de documentation doit être créé.|  
|`file`|Obligatoire si l'option `-doc:` est utilisée. Spécifie le fichier XML de sortie, qui est renseigné avec les commentaires à partir des fichiers de code source de la compilation. Si le nom de fichier contient un espace, mettre le nom entre guillemets (« »).|  
  
## <a name="remarks"></a>Notes  
 Le `-doc` option contrôle si le compilateur génère un fichier XML contenant les commentaires de documentation. Si vous utilisez la `-doc:file` syntaxe, la `file` paramètre spécifie le nom du fichier XML. Si vous utilisez `-doc` ou `-doc+`, le compilateur prend le nom du fichier XML à partir du fichier exécutable ou la bibliothèque que le compilateur est en train de créer. Si vous utilisez `-doc-` ou ne spécifiez pas la `-doc` option, le compilateur ne crée pas d’un fichier XML.  
  
 Dans les fichiers de code source, les commentaires de documentation peuvent précéder les définitions suivantes :  
  
-   Défini par l’utilisateur tape, comme un [classe](../../../visual-basic/language-reference/statements/class-statement.md) ou [interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Membres, par exemple un champ, [événement](../../../visual-basic/language-reference/statements/event-statement.md), [propriété](../../../visual-basic/language-reference/statements/property-statement.md), [fonction](../../../visual-basic/language-reference/statements/function-statement.md), ou [sous-routine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Pour utiliser le fichier XML généré avec Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) la fonctionnalité, soit le nom de fichier du fichier XML de la même que l’assembly que vous souhaitez prendre en charge. Assurez-vous que le fichier XML est dans le même répertoire que l’assembly afin que lorsque l’assembly est référencé dans le projet Visual Studio, le fichier .xml soit également recherché. Fichiers de documentation XML ne sont pas requis pour qu’IntelliSense fonctionne pour le code dans un projet ou dans des projets référencés par un projet.  
  
 Sauf si vous compilez avec `/target:module`, le fichier XML contient les balises `<assembly></assembly>`. Ces balises spécifient le nom du fichier contenant le manifeste d’assembly pour le fichier de sortie de la compilation.  
  
 Consultez [balises de commentaire XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) pour savoir comment générer la documentation à partir de commentaires dans votre code.  
  
|Pour définir - doc dans Visual Studio des environnement de développement intégré|  
|---|  
|1.  Sélectionnez un projet dans l' **Explorateur de solutions**. Dans le menu **Projet**, cliquez sur **Propriétés**. <br />2.  Cliquez sur l’onglet **Compiler**.<br />3.  Définissez la valeur de la **fichier de documentation XML de générer** boîte.|  
  
## <a name="example"></a>Exemple  
 Consultez [documenter votre Code avec XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) pour obtenir un exemple.  
  
## <a name="see-also"></a>Voir aussi  
 [Compilateur de ligne de commande de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Documentation de votre code avec le langage XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)

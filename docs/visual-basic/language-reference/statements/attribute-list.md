---
title: Liste d'attributs (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 2399ec1342280df101e2818399e0f41f10d9606d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818412"
---
# <a name="attribute-list-visual-basic"></a>Liste d'attributs (Visual Basic)
Spécifie les attributs à appliquer à un élément de programmation déclaré. Les attributs multiples sont séparés par des virgules. Voici la syntaxe pour un attribut.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Composants  
|||
|---|---|
|`attributemodifier`|Requis pour les attributs appliqués au début d’un fichier source. Peut être [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) ou [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).|
|`attributename`| Obligatoire. Nom de l'attribut.|
|`attributearguments`|Facultatif. Liste d’arguments de position pour cet attribut. Plusieurs arguments sont séparés par des virgules.|
|`attributeinitializer`|Optionnel. Liste d’initialiseurs de variable ou une propriété pour cet attribut. Les initialiseurs multiples sont séparées par des virgules.|
  
## <a name="remarks"></a>Notes  
 Vous pouvez appliquer un ou plusieurs attributs à presque n’importe quel élément de programmation (types, procédures, propriétés et ainsi de suite). Les attributs apparaissent dans les métadonnées de votre assembly, et ils peuvent vous aider à annoter votre code ou de spécifier l’utilisation d’un élément de programmation particulier. Vous pouvez appliquer des attributs définis par Visual Basic et .NET Framework, et vous pouvez définir vos propres attributs.  

 Pour plus d’informations sur l’utilisation d’attributs, consultez [vue d’ensemble des attributs](../../../visual-basic/programming-guide/concepts/attributes/index.md). Pour plus d’informations sur les noms d’attribut, consultez [noms d’éléments déclarés](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Règles  
  
-   **Sélection élective.** Vous pouvez appliquer des attributs aux éléments de programmation plus déclarés. Pour appliquer un ou plusieurs attributs, placez un *bloc d’attributs* au début de la déclaration d’élément. Chaque entrée dans la liste d’attributs Spécifie un attribut que vous souhaitez appliquer, et le modificateur et les arguments que vous utilisez pour cet appel de l’attribut.  
  
-   **Crochets pointus.** Si vous fournissez une liste d’attributs, vous devez le placer entre crochets pointus («`<`« et »`>`»).  
  
-   **Partie de la déclaration.** L’attribut doit faire partie de la déclaration d’élément, pas une instruction séparée. Vous pouvez utiliser la séquence de continuation de ligne (« `_`») pour étendre l’instruction de déclaration sur plusieurs lignes de code source.  
  
-   **Modificateurs.** Un modificateur d’attribut (`Assembly` ou `Module`) est requis sur chaque attribut appliqué à un élément de programmation au début d’un fichier source. Les modificateurs d’attribut ne sont pas autorisés sur les attributs appliqués aux éléments qui ne sont pas au début d’un fichier source.  
  
-   **Arguments.** Tous les arguments positionnels d’un attribut doivent précéder les initialiseurs de variable ou une propriété.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant applique le <xref:System.Runtime.InteropServices.DllImportAttribute> attribut à une définition squelette d’une `Function` procédure.  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> Indique que la procédure attribuée représente un point d’entrée dans une bibliothèque de liens dynamiques (DLL) non managée. L’attribut fournit le nom de la DLL comme un argument positionnel et les autres informations que les initialiseurs de variable.  
  
## <a name="see-also"></a>Voir aussi

- [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)
- [\<mot clé> du module](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Vue d’ensemble des attributs](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Guide pratique pour diviser et combiner des instructions dans le code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

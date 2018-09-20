---
title: '&lt;inclure&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: da7a6c15c558fc56dbc6a874d4a28c4434f67668
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46473185"
---
# <a name="ltincludegt-visual-basic"></a>&lt;inclure&gt; (Visual Basic)
Fait référence à un autre fichier qui décrit les types et membres dans votre code source.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>Paramètres  
 `filename`  
 Obligatoire. Nom du fichier contenant la documentation. Le nom de fichier peut être qualifié avec un chemin. Placez `filename` dans des guillemets doubles ( » «).  
  
 `tagpath`  
 Obligatoire. Chemin des balises contenues dans `filename` qui mène à la balise `name`. Placez le chemin d’accès entre guillemets doubles ( » «).  
  
 `name`  
 Obligatoire. Le spécificateur de nom dans la balise qui précède les commentaires. `Name` aura un `id`.  
  
 `id`  
 Obligatoire. ID de la balise qui précède les commentaires. Mettez l’ID entre guillemets simples (' ').  
  
## <a name="remarks"></a>Notes  
 Utilisez le `<include>` balise pour faire référence à des commentaires dans un autre fichier qui décrivent les types et membres dans votre code source. Il s’agit d’une solution alternative au placement direct des commentaires de la documentation dans votre fichier de code source.  
  
 Le `<include>` balise utilise la recommandation de la Version 1.0 W3C XML Path Language (XPath). Plus d’informations pour savoir comment personnaliser votre `<include>` utilisation est disponible à l’adresse http://www.w3.org/TR/xpath.  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le `<include>` balise pour importer des commentaires de documentation de membre à partir d’un fichier appelé `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 Le format de la `commentFile.xml` se présente comme suit.  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Étiquettes XML pour les commentaires](../../../visual-basic/language-reference/xmldoc/index.md)

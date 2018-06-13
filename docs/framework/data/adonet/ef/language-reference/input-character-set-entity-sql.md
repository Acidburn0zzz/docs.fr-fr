---
title: Jeu de caractères en entrée (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
ms.openlocfilehash: 5e7886215cac2d9363a9ed68cd03a0fce4374055
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764695"
---
# <a name="input-character-set-entity-sql"></a>Jeu de caractères en entrée (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] accepte les caractères UNICODE encodés en UTF-16.  
  
 Les littéraux de chaîne peuvent contenir tout caractère UTF-16 placé entre guillemets simples. Par exemple, N'文字列リテラル'. Lorsque les littéraux de chaîne sont comparés, les valeurs UTF-16 d'origine sont utilisées. Par exemple, N'ABC est différent dans les pages de code du japonais et du latin.  
  
 Les commentaires peuvent contenir tout caractère UTF-16.  
  
 Les identificateurs placés dans une séquence d'échappement peuvent contenir tout caractère UTF-16 placé entre crochets. Par exemple, [エスケープされた識別子]. La comparaison d'identificateurs UTF-16 placés dans une séquence d'échappement ne respecte pas la casse. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] traite les versions des lettres qui apparaissent identiques mais qui proviennent de pages de codes différentes comme des caractères différents. Par exemple, [ABC] est équivalent à [abc] si les caractères correspondants proviennent de la même page de codes. Toutefois, si ces deux mêmes identificateurs utilisent des pages de codes différentes, ils ne sont pas équivalents.  
  
 L'espace blanc correspond à tout caractère d'espace blanc UTF-16.  
  
 Un saut de ligne est tout caractère normalisé de saut de ligne UTF-16. Par exemple, '\n' et'\r\n' sont considérés comme des caractères de saut de ligne, mais '\r' n'est pas un caractère de saut de ligne.  
  
 Les mots clés, les expressions et la ponctuation peuvent être tout caractère UTF-16 qui est normalisé en latin. Par exemple, SELECT dans une page de codes pour le japonais est un mot clé valide.  
  
 Les mots clés, les expressions et la ponctuation peuvent être uniquement des caractères latins. `SELECT` dans une page de codes japonaise n'est pas un mot clé. +, -, *, /, =, (, ), ‘, [, ] et toute autre construction de langage non citée ici ne peuvent être que des caractères latins.  
  
 Les identificateurs simples ne peuvent être que des caractères latins. Cela évite l'ambiguïté pendant la comparaison, car les valeurs d'origine sont comparées. Par exemple, ABC est différent dans la page de code du japonais et celle du latin.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble d’Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)

---
title: -removeintchecks
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25a14ffaca6e61c6e3306f8ff58de441e2ba2ade
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="-removeintchecks"></a>-removeintchecks
Active la vérification des opérations sur les entiers ou désactivez les erreurs de dépassement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Arguments  
  
|Terme|Définition|  
|---|---|  
|`+` &#124; `-`|Facultatif. La `-removeintchecks-` option, le compilateur à vérifier tous les calculs d’entier pour les erreurs de dépassement de capacité. La valeur par défaut est `-removeintchecks-`.<br /><br /> Spécification de `-removeintchecks` ou `-removeintchecks+` empêche la vérification des erreurs et peuvent effectuer des calculs d’entier plus rapides. Toutefois, sans vérification des erreurs, et si les capacités de type données sont dépassées, des résultats incorrects peuvent être stockées sans déclencher d’une erreur.|  
  
|Pour définir des - removeintchecks dans l’environnement de développement intégré Visual Studio|  
|---|  
|1.  Sélectionnez un projet dans l' **Explorateur de solutions**. Dans le menu **Projet**, cliquez sur **Propriétés**. <br />2.  Cliquez sur l’onglet **Compiler**.<br />3.  Cliquez sur le bouton **Avancées** .<br />4.  Modifier la valeur de la **supprimer les contrôles de dépassement de capacité d’entier** boîte.|  
  
## <a name="example"></a>Exemple  
 Le code suivant compile `Test.vb` et désactive la vérification des erreurs de dépassement de capacité d’entier.  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Compilateur de ligne de commande de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Exemples de lignes de commande de compilation](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

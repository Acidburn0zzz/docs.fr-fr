---
title: Expressions lambda implicitement typées
description: Découvrez pourquoi vous ne pouvez pas utiliser une déclaration de variable implicitement typée pour déclarer une expression lambda.
ms.date: 06/20/2016
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.openlocfilehash: f06c55f51c30c941d6d507ac8e2edd95c5152742
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="implicitly-typed-lambda-expressions"></a>Expressions lambda implicitement typées

Je n’utilise pas `var` pour déclarer cette arborescence d’expression. Vous ne pouvez pas utiliser une déclaration de variable implicitement typée pour déclarer une expression lambda,
car cela crée un problème de logique circulaire pour le compilateur. La déclaration `var` indique au compilateur de déterminer le type de la variable à partir du type de l’expression située à droite de l’opérateur d’assignation. Une expression lambda n’a pas de type au moment de la compilation, mais elle peut être convertie en n’importe quel type d’expression ou de délégué correspondant. Quand vous assignez une expression lambda à une variable d’un type de délégué ou d’expression, vous indiquez au compilateur de convertir l’expression lambda en une expression ou un délégué qui corresponde à la signature de la variable assignée. Le compilateur doit tenter de faire correspondre ce qui se trouve à droite de l’assignation avec ce qui se trouve à sa gauche. 

Les deux côtés de l’assignation ne peuvent pas indiquer au compilateur d’examiner l’objet situé de l’autre côté de l’opérateur d’assignation et de vérifier si le type correspond.

Pour plus d’informations sur ce comportement du langage C#, lisez [cet article](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (téléchargement PDF)



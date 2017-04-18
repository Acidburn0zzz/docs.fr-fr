---
title: "Valeur de type &quot;&lt;NomType1&gt;« ne peut pas être converti en »&lt;NomType2&gt;&quot; (plusieurs références de fichier) | Documents Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 732291ce9c4b83bb9fc7e83fbbc2a8da9748db59
ms.lasthandoff: 03/13/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a>Valeur de type '&lt;NomType1&gt;« ne peut pas être converti en »&lt;NomType2&gt;' (plusieurs références de fichier)
Valeur de type '\<NomType1 >' ne peut pas être convertie en '\<NomType2 > ». Incompatibilité de type peut résulter de la combinaison d’une référence de fichier pour '\<filepath1 >' dans le projet '\<projectname1 >' avec une référence de fichier pour '\<filepath2 >' dans le projet '\<projectname2 > ». Si les deux assemblys sont identiques, essayez de remplacer ces deux références pour qu’elles se situent au même emplacement.  
  
 Dans une situation où un projet fait plusieurs références de fichier à un assembly, le compilateur ne peut pas garantir qu’un type peut être converti vers un autre.  
  
 Chaque référence de fichier Spécifie un chemin d’accès et le nom du fichier de sortie d’un projet (en général un fichier DLL). Le compilateur ne peut pas garantir que les fichiers de sortie proviennent de la même source ou qu’ils représentent la même version du même assembly. Par conséquent, il ne peut pas garantir que les types dans les références différentes sont du même type ou même que l’un peut être converti à l’autre.  
  
 Vous pouvez utiliser une référence de fichier unique si vous savez que les assemblys référencés ont la même identité d’assembly. L’ *identité de l’assembly* comprend le nom de l’assembly, sa version, sa clé publique (le cas échéant) et sa culture. Ces informations identifient de manière unique l’assembly.  
  
 **ID d’erreur :** BC30961  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Si les assemblys référencés ont la même identité d’assembly, supprimez ou remplacez une des références de fichier afin qu’il soit uniquement une référence de fichier unique.  
  
-   Si les assemblys référencés n’ont pas la même identité d’assembly, puis modifiez votre code afin qu’il ne tente pas de convertir un type dans un à un type dans l’autre.  
  
## <a name="see-also"></a>Voir aussi  
 [Conversions de type dans Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Gestion des références dans un projet](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)   
 [NIB Comment : ajouter ou supprimer des références à l’aide de la boîte de dialogue Ajouter une référence](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)

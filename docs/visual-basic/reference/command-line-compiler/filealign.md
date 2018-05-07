---
title: /filealign-
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9c854060e5254cedc6c1004ac3e4f25fbdbbd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="-filealign"></a>/filealign-
Spécifie où les sections du fichier de sortie doivent être alignées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>Arguments  
 `number`  
 Obligatoire. Une valeur qui spécifie l’alignement des sections dans le fichier de sortie. Les valeurs valides sont 512, 1024, 2048, 4096 et 8192. Ces valeurs sont exprimées en octets.  
  
## <a name="remarks"></a>Notes  
 Vous pouvez utiliser la `-filealign` option pour spécifier l’alignement des sections dans votre fichier de sortie. Sont des blocs de mémoire contiguë dans un fichier exécutable Portable (PE) qui contient du code ou des données. Le `-filealign` option vous permet de compiler votre application avec un alignement non standard ; la plupart des développeurs n’avez pas besoin d’utiliser cette option.  
  
 Chaque section est alignée sur une limite qui est un multiple de la `-filealign` valeur. Il n’existe aucune valeur fixe par défaut. Si `-filealign` n’est pas spécifié, le compilateur sélectionne la valeur par défaut au moment de la compilation.  
  
 En spécifiant la taille de section, vous pouvez modifier la taille du fichier de sortie. Il peut être utile de modifier la taille de la section pour les programmes qui sont exécutés sur des appareils de petite taille.  
  
> [!NOTE]
>  Le `-filealign` option n’est pas disponible dans l’environnement de développement Visual Studio ; il est disponible uniquement lors de la compilation à partir de la ligne de commande.  
  
## <a name="see-also"></a>Voir aussi  
 [Compilateur de ligne de commande de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)

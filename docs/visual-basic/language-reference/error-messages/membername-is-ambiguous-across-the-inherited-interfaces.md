---
title: "'<membername>' est ambigu dans les interfaces héritées '<interfacename1>' et '<interfacename2>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 4415608bcfca63b43b3d9ebf17ce622ccd418775
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820843"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a>«\<nom_membre >' est ambigu dans les interfaces héritées'\<nom_interface1 >' et '\<nom_interface2 > »
L’interface hérite de deux ou plusieurs membres portant le même nom plusieurs interfaces.  
  
 **ID d’erreur :** BC30685  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Castez la valeur de l’interface de base que vous souhaitez utiliser. par exemple :  
  
    ```  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>Voir aussi

- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)

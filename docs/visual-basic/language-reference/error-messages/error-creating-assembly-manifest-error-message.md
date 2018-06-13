---
title: 'Erreur de création du manifeste d’assembly : &lt;message d’erreur&gt;'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: b3ea5b502abd318c34d957bf7f540602c53c9e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588299"
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>Erreur de création du manifeste d’assembly : &lt;message d’erreur&gt;
Le compilateur Visual Basic appelle l’utilitaire Assembly Linker (Al.exe, également appelé Alink) pour générer un assembly avec un manifeste. L'éditeur de liens a signalé une erreur dans la phase de préémission de création de l'assembly.  
  
 Cela peut être dû à des problèmes avec le fichier de clé ou le conteneur de clé indiqué. Pour signer un assembly, vous devez fournir un fichier de clé valide contenant des informations relatives aux clés publiques et privées. Pour différer la signature d’un assembly, vous devez cocher la case **Différer la signature uniquement** et fournir un fichier de clé valide contenant des informations de clés publiques. La clé privée n'est pas nécessaire quand la signature d'un assembly est différée. Pour plus d’informations, consultez [Guide pratique pour signer un assembly avec un nom fort](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
 **ID d’erreur :** BC30140  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Examinez le message d’erreur entre guillemets et consultez la rubrique [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). pour l’erreur AL1019 davantage d’explications et conseils  
  
2.  Si l'erreur persiste, rassemblez des informations sur ses circonstances et avertissez les services de support technique Microsoft.  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : signer un assembly avec un nom fort](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Page Signature, Concepteur de projet](/visualstudio/ide/reference/signing-page-project-designer)  
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Nous contacter](/visualstudio/ide/talk-to-us)

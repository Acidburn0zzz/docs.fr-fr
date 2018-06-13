---
title: Constructeur &#39; &lt;nom&gt; &#39; ne peut pas s’appeler lui-même
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 069de813a0426230e19cddf14c3b83d40a602a41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588994"
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a>Constructeur &#39; &lt;nom&gt; &#39; ne peut pas s’appeler lui-même
A `Sub New` procédure dans une classe ou une structure s’appelle elle-même.  
  
 Est de l’objectif d’un constructeur pour initialiser une instance d’une classe ou structure lors de sa création. Une classe ou structure peut avoir plusieurs constructeurs fournies ont tous des listes de paramètres différentes. Un constructeur est autorisé à appeler un autre constructeur pour effectuer ses fonctionnalités en plus de son propre. Ne peut pas s’appeler lui-même un constructeur, mais en fait il entraînerait une récurrence infinie si autorisé.  
  
 **ID d’erreur :** BC30298  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Vérifiez la liste des paramètres du constructeur appelé. Il doit être différent de celui du constructeur qui effectue l’appel.  
  
2.  Si vous ne souhaitez pas appeler un autre constructeur, supprimez le `Sub New` intégralité de l’appel.  
  
## <a name="see-also"></a>Voir aussi  
 [Durée de vie d’un objet : création et destruction des objets](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)

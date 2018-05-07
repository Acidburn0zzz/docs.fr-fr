---
title: Instances d'objets par défaut fournies par My.Forms et My.WebServices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 421995684201ec48d5e8aff9b0ed7640efd1e4b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Instances d'objets par défaut fournies par My.Forms et My.WebServices (Visual Basic)
Le [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) et [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objets fournissent l’accès aux formulaires, sources de données et services Web XML utilisés par votre application. Pour ce faire, ils fournissent des collections de *instances par défaut* de chacun de ces objets.  
  
## <a name="default-instances"></a>Instances par défaut  
 Une instance par défaut est une instance de la classe qui est fournie par le runtime et ne doit pas être déclaré et instancié à l’aide de la `Dim` et `New` instructions. L’exemple suivant montre comment déclarer et instancier une instance d’un <xref:System.Windows.Forms.Form> classe appelée `Form1`, et la façon dont vous êtes maintenant en mesure d’obtenir une instance par défaut de ce <xref:System.Windows.Forms.Form> classe via `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 Le `My.Forms` objet retourne une collection d’instances par défaut pour chaque `Form` classe qui existe dans votre projet. De même, `My.WebServices` fournit une instance par défaut de la classe proxy pour chaque service Web que vous avez créé une référence à dans votre application.  
  
## <a name="see-also"></a>Voir aussi  
 [My.Forms (objet)](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.WebServices (objet)](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [Comment My dépend du type de projet](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)

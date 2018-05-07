---
title: 'Comment : faire pivoter, refléter et incliner des images'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 7f580b4d3016f1ecedc33302fe57caeec5698aeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Comment : faire pivoter, refléter et incliner des images
Vous pouvez faire pivoter, refléter et incliner une image en spécifiant des points de destination pour les angles supérieur gauche, supérieur droit et inférieur gauche de l’image d’origine. Les trois points de destination déterminent une transformation affine qui mappe l’image rectangulaire d’origine à un parallélogramme.  
  
## <a name="example"></a>Exemple  
 Par exemple, supposons que l’image d’origine est un rectangle avec le coin supérieur gauche à (0, 0), coin supérieur droit à (100, 0) et l’angle inférieur gauche à (0, 50). Supposons maintenant vous mappiez ces trois points aux points de destination comme suit.  
  
|Point d’origine|Point de destination|  
|--------------------|-----------------------|  
|Angle supérieur gauche (0, 0)|(200, 20)|  
|Coin supérieur droit (100, 0)|(110, 100)|  
|Inférieur gauche (0, 50)|(250, 30)|  
  
 L’illustration suivante montre l’image d’origine et l’image mappée au parallélogramme. L’image d’origine ont été inégale, reflétée, pivoté et traduit. L’axe des abscisses le long du bord supérieur de l’image d’origine sont mappé à la ligne traversant (200, 20) et (110, 100). L’axe des y le long du bord gauche de l’image d’origine sont mappé à la ligne traversant (200, 20) et (250, 30).  
  
 ![Bandes](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 L’illustration suivante montre une transformation similaire appliquée à une image photographique.  
  
 ![Transformés Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 L’illustration suivante montre une transformation similaire appliquée à un métafichier.  
  
 ![Transformés métafichier](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 L’exemple suivant produit les images présentées dans la première illustration.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 L’exemple précédent est conçu pour une utilisation avec Windows Forms et nécessite <xref:System.Windows.Forms.PaintEventArgs> `e`, qui est un paramètre de la <xref:System.Windows.Forms.Control.Paint> Gestionnaire d’événements. Veillez à remplacer `Stripes.bmp` avec le chemin d’accès à une image qui est valide sur votre système.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des images, bitmaps, icônes et métafichiers](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

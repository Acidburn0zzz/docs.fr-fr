---
title: 'Procédure : appliquer une correction gamma à un dégradé'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 7290b7901714e9b71bda3f85f930f5331b8fd4ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077327"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>Procédure : appliquer une correction gamma à un dégradé
Vous pouvez activer la correction gamma pour un pinceau dégradé linéaire en définissant le pinceau <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propriété `true`. Vous pouvez désactiver la correction gamma en définissant le <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> propriété `false`. La correction du gamma est désactivée par défaut.  
  
## <a name="example"></a>Exemple  
 L’exemple crée un pinceau dégradé linéaire et utilise ce pinceau pour remplir les deux rectangles. Le premier est rempli sans correction gamma, et le deuxième rectangle est rempli avec une correction gamma.  
  
 L’illustration suivante montre les deux rectangles remplis. Le rectangle supérieur, ce qui n’a pas de correction gamma, apparaît foncé au milieu. Le rectangle en bas, ce qui a une correction gamma, semble intensité plus régulière.  
  
 ![Gradient](./media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 L’exemple précédent est conçu pour une utilisation avec Windows Forms et nécessite <xref:System.Windows.Forms.PaintEventArgs> `e`, qui est un paramètre de la <xref:System.Windows.Forms.Control.Paint> Gestionnaire d’événements.  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [Utilisation d'un pinceau à dégradé pour remplir des formes](using-a-gradient-brush-to-fill-shapes.md)

---
title: 'Comment : dessiner une ellipse remplie dans un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: b892670031e795ecd27b194cdf2cf818f4af6254
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521431"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a>Comment : dessiner une ellipse remplie dans un Windows Form
Cet exemple dessine une ellipse pleine dans un formulaire.  
  
## <a name="example"></a>Exemple  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Vous ne pouvez pas appeler cette méthode le <xref:System.Windows.Forms.Form.Load> Gestionnaire d’événements. Le contenu dessiné ne sera pas redessiné si le formulaire est redimensionné ou masqué par une autre forme. Pour que votre contenu soit automatiquement repeint, vous devez substituer la <xref:System.Windows.Forms.Control.OnPaint%2A> (méthode).  
  
## <a name="robust-programming"></a>Programmation fiable  
 Vous devez toujours appeler <xref:System.IDisposable.Dispose%2A> sur tous les objets qui consomment des ressources système, telles que <xref:System.Drawing.Brush> et <xref:System.Drawing.Graphics> objets.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphiques et dessins dans Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Mise en route de la programmation graphique](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Fusion alpha de lignes et de remplissages](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [Utilisation d'un pinceau pour remplir des formes](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)

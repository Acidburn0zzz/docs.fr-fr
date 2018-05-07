---
title: "Comment : étirer un ToolStripTextBox pour remplir la largeur restante d'un ToolStrip (Windows Forms)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: bd58cbd109b8e3dd04c6a284dc6926e95830fb61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Comment : étirer un ToolStripTextBox pour remplir la largeur restante d'un ToolStrip (Windows Forms)
Lorsque vous définissez la <xref:System.Windows.Forms.ToolStrip.Stretch%2A> propriété d’un <xref:System.Windows.Forms.ToolStrip> le contrôle à `true`, le contrôle remplit son conteneur de bout en bout et peut être redimensionné lorsque son conteneur est redimensionné. Dans cette configuration, vous pouvez s’avérer utile d’étendre un élément dans le contrôle, comme un <xref:System.Windows.Forms.ToolStripTextBox>, pour remplir l’espace disponible et redimensionner lorsque le contrôle est redimensionné. Cette extension est utile, par exemple, si vous souhaitez obtenir une apparence et un comportement similaire à la barre d’adresses dans Microsoft® Internet Explorer.  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant fournit une classe dérivée de <xref:System.Windows.Forms.ToolStripTextBox> appelée `ToolStripSpringTextBox`. Cette classe substitue le <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> méthode pour calculer la largeur disponible du parent <xref:System.Windows.Forms.ToolStrip> contrôle une fois que la largeur combinée de tous les autres éléments a été soustrait. Cet exemple de code fournit également une <xref:System.Windows.Forms.Form> classe et un `Program` pour illustrer le nouveau comportement.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Cet exemple nécessite :  
  
-   Références aux assemblys System, System.Drawing et System.Windows.Forms.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [Architecture du contrôle ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Guide pratique pour utiliser la propriété Spring dans un StatusStrip de manière interactive](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)

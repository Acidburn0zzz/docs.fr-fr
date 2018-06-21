---
title: 'Comment : copier des pixels pour réduire le scintillement dans les Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: dc5f05ff4ea9f3c2b828cbe37860e1bd241fc604
ms.sourcegitcommit: 3d42e1d73e21c35c540dd4adbea23efcbe1b8b0a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36270433"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Comment : copier des pixels pour réduire le scintillement dans les Windows Forms
Lorsque vous animez un graphique simple, les utilisateurs peuvent parfois être scintillement ou autres effets visuels indésirables. Un pour limiter ce problème consiste à utiliser un processus « bitblt » sur le graphique. BitBlt représente le « bloc de bits transfert » des données de couleur à partir d’un rectangle d’origine de pixels à un rectangle de destination de pixels.  
  
 Avec Windows Forms, le processus bitblt s’effectue à l’aide de la <xref:System.Drawing.Graphics.CopyFromScreen%2A> méthode de la <xref:System.Drawing.Graphics> classe. Dans les paramètres de la méthode, vous spécifiez la source et destination (en tant que points), la taille de la zone à copier et l’objet graphics utilisé pour dessiner la nouvelle forme.  
  
 Dans l’exemple ci-dessous, une forme est dessinée sur le formulaire dans son <xref:System.Windows.Forms.Control.Paint> Gestionnaire d’événements. Ensuite, la <xref:System.Drawing.Graphics.CopyFromScreen%2A> méthode est utilisée pour dupliquer la forme.  
  
> [!NOTE]
>  Définition du formulaire <xref:System.Windows.Forms.Control.DoubleBuffered%2A> propriété `true` permettront à code de graphiques dans le <xref:System.Windows.Forms.Control.Paint> événement est de double tampon. Alors que cela ne disposent pas des gains de performances visible lorsque vous utilisez le code ci-dessous, le problème est à prendre en compte lorsque vous travaillez avec le code de manipulation de graphiques plus complexe.  
  
## <a name="example"></a>Exemple  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Le code ci-dessus est exécuté sous la forme <xref:System.Windows.Forms.Control.Paint> Gestionnaire d’événements afin que les graphiques persistent si le formulaire est redessiné. Par conséquent, n’appelez pas de méthodes graphiques dans le <xref:System.Windows.Forms.Form.Load> Gestionnaire d’événements, car le contenu dessiné ne sera pas redessiné si le formulaire est redimensionné ou masqué par une autre forme.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [Graphiques et dessins dans Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Utilisation d'un stylet pour dessiner des lignes et des formes](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)

---
title: 'Procédure : Créer et définir un convertisseur personnalisé pour le contrôle ToolStrip dans les Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: a70503dd4def19dd303a7362c9ca4d92f1419ff6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538503"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Procédure : Créer et définir un convertisseur personnalisé pour le contrôle ToolStrip dans les Windows Forms
<xref:System.Windows.Forms.ToolStrip> contrôles de bénéficier d’une assistance simple pour les thèmes et styles. Vous pouvez obtenir totalement l’aspect et le comportement (aspect) en définissant le <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propriété ou le <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propriété à un convertisseur personnalisé.  
  
 Vous pouvez assigner des convertisseurs à chaque individu <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, ou <xref:System.Windows.Forms.StatusStrip> contrôle, ou vous pouvez utiliser la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> affecter tous les objets en définissant le <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> propriété <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Retourne <xref:System.Windows.Forms.ToolStripRenderMode.Custom> uniquement si la valeur de <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> n’est pas `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Pour créer un convertisseur personnalisé  
  
1.  Étendre la <xref:System.Windows.Forms.ToolStripRenderer> classe.  
  
2.  Implémentez le rendu personnalisé souhaité en substituant approprié *sur...* membres  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Pour définir le convertisseur personnalisé pour être le rendu en cours  
  
1.  Pour définir le convertisseur personnalisé pour un <xref:System.Windows.Forms.ToolStrip>, définissez le <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propriété le convertisseur personnalisé.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  Ou pour définir le convertisseur personnalisé pour toutes les <xref:System.Windows.Forms.ToolStrip> classes contenues dans votre application : Définir le <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propriété au convertisseur personnalisé et affectez le <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> propriété <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [Vue d’ensemble du contrôle ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [Architecture du contrôle ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [Résumé de la technologie ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)

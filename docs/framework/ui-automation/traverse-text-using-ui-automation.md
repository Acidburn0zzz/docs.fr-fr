---
title: Accéder au texte à l'aide d'UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
ms.openlocfilehash: d73ae4ca11d6f5417bb5cb768eae4e586538bd92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154789"
---
# <a name="traverse-text-using-ui-automation"></a>Accéder au texte à l'aide d'UI Automation
> [!NOTE]
>  Cette documentation s'adresse aux développeurs .NET Framework qui souhaitent utiliser les classes [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] managées définies dans l'espace de noms <xref:System.Windows.Automation>. Pour plus d’informations sur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consultez [Windows Automation API : UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Cette rubrique montre comment utiliser [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] pour parcourir le contenu textuel d’un document par incréments <xref:System.Windows.Automation.Text.TextUnit> .  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant montre comment parcourir le contenu d’un fournisseur de texte UI Automation. La méthode <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> déplace les points de terminaison <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> et <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> de <xref:System.Windows.Automation.Text.TextPatternRange>. Cette plage de texte est généralement une plage dégénérée représentant le point d’insertion du texte.  
  
> [!NOTE]
>  Dans la mesure où seuls les objets incorporés basés sur du texte sont considérés comme faisant partie du flux de texte, les objets incorporés tels que les images n’affectent pas `Move` ou sa valeur de retour.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 Toute méthode utilisant <xref:System.Windows.Automation.Text.TextUnit> est différée au prochain <xref:System.Windows.Automation.Text.TextUnit> le plus long pris en charge, si le <xref:System.Windows.Automation.Text.TextUnit> concerné n’est pas pris en charge par le contrôle.  
  
## <a name="see-also"></a>Voir aussi

- [Vue d'ensemble de TextPattern d'UI Automation](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)
- [Ajouter du contenu à une zone de texte à l'aide d'UI Automation](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)
- [Rechercher et mettre un texte en surbrillance à l'aide d'UI Automation](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
- [Vue d'ensemble des modèles de contrôle UI Automation](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Modèles de contrôle UI Automation pour les clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)

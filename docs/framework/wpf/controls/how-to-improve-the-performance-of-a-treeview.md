---
title: "Comment : améliorer les performances d'un contrôle TreeView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 75f17c770af89f08fedfd3c8193a916901fe6f79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552751"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Comment : améliorer les performances d'un contrôle TreeView
Si un <xref:System.Windows.Controls.TreeView> contient de nombreux éléments, la quantité de temps de chargement peut entraîner un délai important dans l’interface utilisateur. Vous pouvez améliorer le temps de chargement en définissant le `VirtualizingStackPanel.IsVirtualizing` propriété attachée `true`.  L’interface utilisateur peut également être lente à réagir lorsqu’un utilisateur fait défiler le <xref:System.Windows.Controls.TreeView> à l’aide de la roulette de la souris ou en faisant glisser le curseur d’une barre de défilement. Vous pouvez améliorer les performances de la <xref:System.Windows.Controls.TreeView> lorsque l’utilisateur fait défiler en définissant le `VirtualizingStackPanel.VirtualizationMode` propriété attachée <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Exemple  
  
## <a name="description"></a>Description  
L’exemple suivant crée un <xref:System.Windows.Controls.TreeView> qui définit le `VirtualizingStackPanel.IsVirtualizing` propriété attachée à la valeur true et la `VirtualizingStackPanel.VirtualizationMode` propriété attachée <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> optimiser ses performances.  
  
## <a name="code"></a>Code  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 L’exemple suivant montre les données que l’exemple précédent utilise.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)

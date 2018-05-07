---
title: "Comment : positionner les éléments enfants d'une grille"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 62508deee1b10b4a1287360f971b3699e57d4243
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a>Comment : positionner les éléments enfants d'une grille
Cet exemple montre comment utiliser la méthode get et définir des méthodes qui sont définis dans <xref:System.Windows.Controls.Grid> pour positionner des éléments enfants.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant définit un parent <xref:System.Windows.Controls.Grid> élément (`grid1`) qui a trois colonnes et trois lignes. Un enfant <xref:System.Windows.Shapes.Rectangle> élément (`rect1`) est ajouté à la <xref:System.Windows.Controls.Grid> position de colonne zéro, position de ligne zéro. <xref:System.Windows.Controls.Button> les éléments représentent des méthodes qui peuvent être appelées pour repositionner le <xref:System.Windows.Shapes.Rectangle> élément dans le <xref:System.Windows.Controls.Grid>. Lorsqu’un utilisateur clique sur un bouton, la méthode associée est activée.  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 L’exemple de code-behind suivant gère les méthodes que le bouton <xref:System.Windows.Controls.Primitives.ButtonBase.Click> déclenchent des événements. L’exemple écrit ces appels de méthode <xref:System.Windows.Controls.TextBlock> éléments liée de l’utilisation des méthodes get pour sortir les nouvelles valeurs de propriété sous forme de chaînes.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Controls.Grid>  
 [Vue d’ensemble de Panel](../../../../docs/framework/wpf/controls/panels-overview.md)

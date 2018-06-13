---
title: "Comment : utiliser les propriétés jointes d'une zone de dessin pour positionner des éléments enfants"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 886440304dc1bebdcfae66676254bef7ac35457d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552372"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>Comment : utiliser les propriétés jointes d'une zone de dessin pour positionner des éléments enfants
Cet exemple montre comment utiliser les propriétés jointes de <xref:System.Windows.Controls.Canvas> pour positionner des éléments enfants.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant ajoute quatre <xref:System.Windows.Controls.Button> éléments en tant qu’éléments enfants d’un parent <xref:System.Windows.Controls.Canvas>. Chaque élément enfant représente une propriété attachée distincte de <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, et <xref:System.Windows.Controls.Canvas.Top%2A>. Chaque <xref:System.Windows.Controls.Button> est positionné par rapport au parent <xref:System.Windows.Controls.Canvas> et en fonction de sa valeur de propriété assignée.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.Canvas.Bottom%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 <xref:System.Windows.Controls.Canvas.Right%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Button>  
 [Vue d’ensemble de Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Rubriques de guide pratique](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)  
 [Vue d'ensemble des propriétés jointes](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)

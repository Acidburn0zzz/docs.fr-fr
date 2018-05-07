---
title: 'Comment : implémenter un ornement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: f5b0ed080a413546a3b985055858e209f9f347eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-an-adorner"></a>Comment : implémenter un ornement
Cet exemple montre une implémentation d’ornement minimale.  
  
## <a name="notes-for-implementers"></a>Notes pour les implémenteurs  
 Il est important de noter que les ornements n’incluent aucun comportement de rendu inhérent ; il appartient donc à l’implémenteur d’un ornement de vérifier son rendu.   Une méthode courante de l’implémentation du comportement de rendu consiste à remplacer le <xref:System.Windows.UIElement.OnRender%2A> méthode et l’utilisation d’un ou plusieurs <xref:System.Windows.Media.DrawingContext> objets pour restituer les visuels de l’ornement en fonction des besoins (comme indiqué dans cet exemple).  
  
## <a name="example"></a>Exemple  
  
### <a name="description"></a>Description  
 Un ornement personnalisé est créé en implémentant une classe qui hérite de l’abstraite <xref:System.Windows.Documents.Adorner> classe.  L’ornement d’exemple orne simplement les angles d’un <xref:System.Windows.UIElement> avec des cercles en substituant la <xref:System.Windows.UIElement.OnRender%2A> (méthode).  
  
### <a name="code"></a>Code  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble des ornements](../../../../docs/framework/wpf/controls/adorners-overview.md)

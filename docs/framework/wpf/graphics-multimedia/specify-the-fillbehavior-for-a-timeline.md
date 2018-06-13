---
title: 'Comment : spécifier le FillBehavior pour une chronologie ayant atteint la fin de sa période active'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 947be09140dc2d1d5e130ccb74472d8dce3408cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563478"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Comment : spécifier le FillBehavior pour une chronologie ayant atteint la fin de sa période active
Cet exemple montre comment spécifier le <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> pour inactifs <xref:System.Windows.Media.Animation.Timeline> d’une propriété animée.  
  
## <a name="example"></a>Exemple  
 Le <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propriété d’un <xref:System.Windows.Media.Animation.Timeline> détermine ce qui se passe à la valeur d’une propriété animée lorsqu’il n’est pas en cours d’animation, autrement dit, lorsque la <xref:System.Windows.Media.Animation.Timeline> est inactif, mais son parent <xref:System.Windows.Media.Animation.Timeline> est active ou d’une période d’attente. Par exemple, une propriété animée reste à sa fin valeur une fois l’animation se termine ou qu’il le fait revenir à la valeur qu’elle avait avant le démarrage de l’animation ?  
  
 L’exemple suivant utilise un <xref:System.Windows.Media.Animation.DoubleAnimation> pour animer la <xref:System.Windows.FrameworkElement.Width%2A> de deux rectangles. Chaque rectangle utilise un autre <xref:System.Windows.Media.Animation.Timeline> objet.  
  
 Un <xref:System.Windows.Media.Animation.Timeline> a un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> qui a la valeur <xref:System.Windows.Media.Animation.FillBehavior.Stop>, ce qui entraîne la largeur du rectangle à revenir à son non animée valeur lorsque le <xref:System.Windows.Media.Animation.Timeline> se termine. L’autre <xref:System.Windows.Media.Animation.Timeline> a un <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> de <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, ce qui entraîne la largeur reste à sa fin valeur lorsque le <xref:System.Windows.Media.Animation.Timeline> se termine.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Pour obtenir un exemple complet, consultez [Galerie d’exemples d’Animation](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [Vue d’ensemble de l’animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Animation et minutage](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Rubriques de guide pratique](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)

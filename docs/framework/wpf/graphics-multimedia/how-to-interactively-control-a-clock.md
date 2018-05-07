---
title: 'Comment : contrôler une horloge de façon interactive'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 63e72c48afd9b72a6b334ccdc234d08cef7288f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-interactively-control-a-clock"></a>Comment : contrôler une horloge de façon interactive
A <xref:System.Windows.Media.Animation.Clock> l’objet <xref:System.Windows.Media.Animation.ClockController> propriété permet interactivement Démarrer, suspendre, reprendre, rechercher, avancer l’horloge à sa période de remplissage et arrêter l’horloge. Que l’horloge racine d’arborescence de minutage peut être contrôlée de manière interactive.  
  
> [!NOTE]
>  Il existe des autres méthodes de manière interactive les animations de contrôle qui ne nécessitent pas vous permet de travailler directement avec des horloges : vous pouvez également utiliser des plans conceptuels. Storyboards sont pris en charge dans le balisage et le code. Pour obtenir un exemple, consultez [animer une propriété à l’aide d’un Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) ou [vue d’ensemble de l’Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Dans l’exemple suivant, plusieurs boutons sont utilisés pour contrôler de façon interactive une horloge d’animation.  
  
## <a name="example"></a>Exemple  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>Voir aussi  
 [Animer une propriété à l’aide d’une table de montage séquentiel](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Vue d’ensemble de l’animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)

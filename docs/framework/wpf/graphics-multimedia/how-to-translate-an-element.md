---
title: 'Procédure : Translater un élément'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 9c1b873a89820e85efb99789f483c4832fb23cf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231186"
---
# <a name="how-to-translate-an-element"></a>Procédure : Translater un élément
Cet exemple montre comment Translater (déplacer) un élément en utilisant un <xref:System.Windows.Media.TranslateTransform>.  
  
 Le <xref:System.Windows.Media.TranslateTransform> classe est particulièrement utile pour déplacer des éléments à l’intérieur des panneaux qui ne prennent pas en charge le positionnement absolu. Par exemple, en appliquant un <xref:System.Windows.Media.TranslateTransform> à la <xref:System.Windows.UIElement.RenderTransform%2A> propriété d’un élément, vous pouvez déplacer un élément dans un <xref:System.Windows.Controls.StackPanel> ou <xref:System.Windows.Controls.DockPanel>.  
  
 Utilisez le <xref:System.Windows.Media.TranslateTransform.X%2A> propriété de la <xref:System.Windows.Media.TranslateTransform> pour spécifier la quantité, en pixels, pour déplacer l’élément le long de l’axe des abscisses. Utilisez le <xref:System.Windows.Media.TranslateTransform.Y%2A> propriété pour spécifier la quantité, en pixels, pour déplacer l’élément le long de l’axe des ordonnées. Enfin, appliquez le <xref:System.Windows.Media.TranslateTransform> à la <xref:System.Windows.UIElement.RenderTransform%2A> propriété de l’élément.  
  
 L’exemple suivant utilise un <xref:System.Windows.Media.TranslateTransform> pour déplacer un élément de 50 pixels vers les droite et de 50 pixels vers le bas.  
  
## <a name="example"></a>Exemple  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Pour voir l’exemple complet, consultez la page [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252) (Exemple de transformations 2D).  
  
## <a name="see-also"></a>Voir aussi

- [Vue d'ensemble des transformations](transforms-overview.md)

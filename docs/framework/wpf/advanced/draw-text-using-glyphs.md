---
title: Dessiner du texte à l'aide de glyphes
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: e2b35eb6df140551d5db7d597826df53e37182fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="draw-text-using-glyphs"></a>Dessiner du texte à l'aide de glyphes
Cette rubrique explique comment utiliser le plus bas niveau <xref:System.Windows.Documents.Glyphs> objet pour afficher le texte dans [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Exemple  
 Les exemples suivants montrent comment définir des propriétés pour un <xref:System.Windows.Documents.Glyphs> dans l’objet [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Le <xref:System.Windows.Documents.Glyphs> objet représente la sortie d’un <xref:System.Windows.Media.GlyphRun> dans [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Ces exemples supposent que les polices Arial, Courrier New et Times New Roman sont installées dans le dossier C:\WINDOWS\Fonts sur l’ordinateur local.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 Cet exemple montre comment définir les autres propriétés de <xref:System.Windows.Documents.Glyphs> dans des objets [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>Voir aussi  
 [Typographie dans WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)

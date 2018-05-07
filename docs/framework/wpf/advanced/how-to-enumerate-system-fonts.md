---
title: 'Comment : énumérer des polices système'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: 7fc996a2d3ba7042fce70afc20be5d64042c2b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-system-fonts"></a>Comment : énumérer des polices système
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment énumérer les polices dans la collection de polices système. Le nom de famille de polices de chaque <xref:System.Windows.Media.FontFamily> dans <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> est ajouté en tant qu’élément à une zone de liste déroulante.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Si plusieurs versions de la même famille de polices résident dans le même répertoire, le [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] police énumération sans corrélation retourne la version la plus récente de la police. Si les informations de version ne fournissent pas de résolution, la police avec l’horodatage le plus récent est retournée. Si les informations d’horodatage sont équivalentes, le fichier de polices qui apparaît en premier dans l’ordre alphabétique est retourné.

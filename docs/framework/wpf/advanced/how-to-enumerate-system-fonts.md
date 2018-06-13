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
ms.locfileid: "33543753"
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="a481d-102">Comment : énumérer des polices système</span><span class="sxs-lookup"><span data-stu-id="a481d-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="a481d-103">Exemple</span><span class="sxs-lookup"><span data-stu-id="a481d-103">Example</span></span>  
 <span data-ttu-id="a481d-104">L’exemple suivant montre comment énumérer les polices dans la collection de polices système.</span><span class="sxs-lookup"><span data-stu-id="a481d-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="a481d-105">Le nom de famille de polices de chaque <xref:System.Windows.Media.FontFamily> dans <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> est ajouté en tant qu’élément à une zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a481d-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="a481d-106">Si plusieurs versions de la même famille de polices résident dans le même répertoire, le [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] police énumération sans corrélation retourne la version la plus récente de la police.</span><span class="sxs-lookup"><span data-stu-id="a481d-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="a481d-107">Si les informations de version ne fournissent pas de résolution, la police avec l’horodatage le plus récent est retournée.</span><span class="sxs-lookup"><span data-stu-id="a481d-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="a481d-108">Si les informations d’horodatage sont équivalentes, le fichier de polices qui apparaît en premier dans l’ordre alphabétique est retourné.</span><span class="sxs-lookup"><span data-stu-id="a481d-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>

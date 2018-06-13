---
title: "Comment : créer une forme à l'aide d'un StreamGeometry"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 54819f62b262227017e12b2066a0747107b68900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560365"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a>Comment : créer une forme à l'aide d'un StreamGeometry
<xref:System.Windows.Media.StreamGeometry> est une alternative légère à <xref:System.Windows.Media.PathGeometry> pour créer des formes géométriques. Utilisez un <xref:System.Windows.Media.StreamGeometry> lorsque vous devez décrire une géométrie complexe, mais ne souhaitez pas que la surcharge de prendre en charge la liaison de données, les animations ni les modifications. Par exemple, en raison de son efficacité, la <xref:System.Windows.Media.StreamGeometry> classe est un bon choix pour décrire des ornements.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise la syntaxe d’attribut pour créer un triangulaire <xref:System.Windows.Media.StreamGeometry> dans [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Pour plus d’informations sur <xref:System.Windows.Media.StreamGeometry> la syntaxe d’attribut, consultez la [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise un <xref:System.Windows.Media.StreamGeometry> pour définir un triangle dans le code. L’exemple crée d’abord un <xref:System.Windows.Media.StreamGeometry>, puis obtient un <xref:System.Windows.Media.StreamGeometryContext> et l’utilise pour décrire le triangle.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée une méthode qui utilise un <xref:System.Windows.Media.StreamGeometry> et <xref:System.Windows.Media.StreamGeometryContext> pour définir une forme géométrique en fonction des paramètres spécifiés.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.StreamGeometryContext>  
 [Créer une forme à l’aide d’un PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)  
 [Vue d’ensemble de Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)

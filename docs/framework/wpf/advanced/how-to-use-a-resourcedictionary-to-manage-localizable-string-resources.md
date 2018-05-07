---
title: Guide pratique pour utiliser un ResourceDictionary pour gérer des ressources de type chaîne localisables
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: 76ff3f688b5d3e7122254990076edb21fe6ae119
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Guide pratique pour utiliser un ResourceDictionary pour gérer des ressources de type chaîne localisables
Cet exemple montre comment utiliser un <xref:System.Windows.ResourceDictionary> pour empaqueter des ressources de type chaîne localisables pour les applications Windows Presentation Foundation (WPF).  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Pour utiliser un ResourceDictionary pour gérer des ressources de type chaîne localisables  
  
1.  Créer un <xref:System.Windows.ResourceDictionary> qui contient les chaînes que vous souhaitez localiser. Le code suivant fournit un exemple.  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     Ce code définit une ressource de chaîne, `localizedMessage`, de type <xref:System.String>, à partir de la <xref:System> espace de noms dans mscorlib.dll.  
  
2.  Ajouter le <xref:System.Windows.ResourceDictionary> à votre application, utilisez le code suivant.  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  Utilisez la ressource de chaîne à partir du balisage, à l’aide de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] comme suit.  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  Utilisez la ressource de chaîne à partir du code-behind, à l’aide de code semblable au suivant.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  Localisez l’application. Pour plus d’informations, consultez [localiser une Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).

---
title: 'Comment : accéder à une Page'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 896287376979d40816e3937fff77b38bf71a62f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-navigate-to-a-page"></a>Comment : accéder à une Page
Cet exemple illustre plusieurs méthodes dans lequel une page peut être accède à un <xref:System.Windows.Navigation.NavigationWindow>.  
  
## <a name="example"></a>Exemple  
 Il est possible pour un <xref:System.Windows.Navigation.NavigationWindow> pour accéder à une page à l’aide d’une des opérations suivantes :  
  
-   La propriété <xref:System.Windows.Navigation.NavigationWindow.Source%2A>.  
  
-   Méthode <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] peut être relatif ou absolu. Pour plus d’informations, consultez [URI à en-tête pack dans WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.NavigationService>

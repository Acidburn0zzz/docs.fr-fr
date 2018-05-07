---
title: 'Comment : obtenir et définir la fenêtre principale de l’Application'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: ae70b482eba8fb4e0bf587def06bb90d751a4312
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Comment : obtenir et définir la fenêtre principale de l’Application
Cet exemple montre comment obtenir et définir la fenêtre d’application principale.  
  
## <a name="example"></a>Exemple  
 La première <xref:System.Windows.Window> qui est instancié dans un Windows Presentation Foundation (WPF) application est automatiquement définie par <xref:System.Windows.Application> en tant que fenêtre d’application principale. La première <xref:System.Windows.Window> pour être instancié sera certainement la fenêtre qui est spécifiée comme le démarrage [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (voir <xref:System.Windows.Application.StartupUri%2A>).  
  
 Le premier <xref:System.Windows.Window> peut également être instancié à l’aide de code. Par exemple ouvre une fenêtre pendant le démarrage de l’application, comme suit :  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 Parfois, le premier instancié <xref:System.Windows.Window> n’est pas réellement dans la fenêtre principale de l’application par exemple, un écran de démarrage. Dans ce cas, vous pouvez spécifier la fenêtre principale de l’application à l’aide de la balise, comme suit :  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Si la fenêtre principale est spécifiée automatiquement ou manuellement, vous pouvez obtenir la fenêtre principale à partir de <xref:System.Windows.Application.MainWindow%2A> utilisant le code suivant, comme suit :  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]

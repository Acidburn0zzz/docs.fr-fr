---
title: "Comment : effectuer une liaison à un service Web"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d1b81949d6d91420c828564debd311af47dfdfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-web-service"></a>Comment : effectuer une liaison à un service Web
Cet exemple montre comment lier des objets retournés par les appels de méthode de service Web.  
  
## <a name="example"></a>Exemple  
 Cet exemple utilise le [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) pour récupérer la liste des langues prises en charge par un document spécifié.  
  
 Avant d’appeler un service Web, vous devez créer une référence à celui-ci. Pour créer une référence Web au service MTPS à l’aide [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], procédez comme suit :  
  
1.  Ouvrez votre projet dans [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  
  
2.  À partir de la **projet** menu, cliquez sur **ajouter une référence Web**.  
  
3.  Dans la boîte de dialogue, définissez la **URL** à [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4.  Appuyez sur **accédez** , puis **ajouter une référence**.  
  
 Ensuite, vous appelez la méthode de service Web et définir le <xref:System.Windows.FrameworkElement.DataContext%2A> de la fenêtre à l’objet retourné ou le contrôle approprié. Le **GetContent** méthode du service MTPS prend une référence à la **getContentRequest** objet. Par conséquent, l’exemple suivant définit tout d’abord un objet de demande :  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Après le <xref:System.Windows.FrameworkElement.DataContext%2A> a été défini, vous pouvez créer des liaisons pour les propriétés de l’objet qui le <xref:System.Windows.FrameworkElement.DataContext%2A> a la valeur. Dans cet exemple, le <xref:System.Windows.FrameworkElement.DataContext%2A> est défini sur le **getContentResponse** objet retourné par la **GetContent** (méthode). Dans l’exemple suivant, la <xref:System.Windows.Controls.ItemsControl> et les affiche le **paramètres régionaux** les valeurs de **availableVersionsAndLocales** de **getContentResponse**.  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Pour plus d’informations sur la structure des **getContentResponse**, consultez [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la liaison de données](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Vue d'ensemble des sources de liaison](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Rendre des données disponibles pour la liaison en XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)

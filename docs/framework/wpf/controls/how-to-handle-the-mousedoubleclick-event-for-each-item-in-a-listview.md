---
title: "Comment : gérer l'événement MouseDoubleClick pour chaque élément d'un ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: f9a1e91051a7f86bf78cb08a3d58e57541ae4987
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Comment : gérer l'événement MouseDoubleClick pour chaque élément d'un ListView
Pour gérer un événement pour un élément dans un <xref:System.Windows.Controls.ListView>, vous devez ajouter un gestionnaire d’événements à chaque <xref:System.Windows.Controls.ListViewItem>. Lorsqu’un <xref:System.Windows.Controls.ListView> est lié à une source de données, vous ne créez pas explicitement un <xref:System.Windows.Controls.ListViewItem>, mais vous pouvez gérer l’événement pour chaque élément en ajoutant un <xref:System.Windows.EventSetter> à un style d’un <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée une propriété <xref:System.Windows.Controls.ListView> et crée un <xref:System.Windows.Style> pour ajouter un gestionnaire d’événements dans chaque <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 L’exemple suivant gère le <xref:System.Windows.Controls.Control.MouseDoubleClick> événement.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Bien qu’il soit plus courante consiste à lier un <xref:System.Windows.Controls.ListView> à une source de données, vous pouvez utiliser un style pour ajouter un gestionnaire d’événements dans chaque <xref:System.Windows.Controls.ListViewItem> dans un non-liés aux données <xref:System.Windows.Controls.ListView> que vous créiez explicitement une <xref:System.Windows.Controls.ListViewItem>.  Pour plus d’informations sur créés explicitement et implicitement <xref:System.Windows.Controls.ListViewItem> contrôles, consultez <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Xml.XmlElement>  
 [Vue d’ensemble de la liaison de données](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Application d’un style et création de modèles](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Effectuer une liaison à des données XML à l’aide d’un XMLDataProvider et de requêtes XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [Vue d’ensemble de ListView](../../../../docs/framework/wpf/controls/listview-overview.md)

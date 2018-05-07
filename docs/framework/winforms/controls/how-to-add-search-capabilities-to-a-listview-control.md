---
title: 'Comment : ajouter des fonctions de recherche à un contrôle ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: 2049638998f7a8d099e14fab9c95384a49c67833
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>Comment : ajouter des fonctions de recherche à un contrôle ListView
Souvent, lorsque vous travaillez sur une longue liste d’éléments dans un <xref:System.Windows.Forms.ListView> (contrôle), que vous souhaitez offrir des fonctionnalités de recherche à l’utilisateur. Le <xref:System.Windows.Forms.ListView> contrôle offre cette possibilité de deux manières différentes : correspondance de texte et de recherche d’emplacement.  
  
 Le <xref:System.Windows.Forms.ListView.FindItemWithText%2A> méthode permet de vous permet d’effectuer une recherche de texte sur un <xref:System.Windows.Forms.ListView> en mode liste ou détails, étant donné une chaîne de recherche un facultative et les index. En revanche, le <xref:System.Windows.Forms.ListView.FindNearestItem%2A> méthode vous permet de trouver un élément dans un <xref:System.Windows.Forms.ListView> en mode icône ou mosaïque, étant donné un jeu de coordonnées x et y et une direction à rechercher.  
  
### <a name="to-find-an-item-using-text"></a>Pour rechercher un élément à l’aide de texte  
  
1.  Créer un <xref:System.Windows.Forms.ListView> avec la <xref:System.Windows.Forms.ListView.View%2A> propriété la valeur <xref:System.Windows.Forms.View.Details> ou <xref:System.Windows.Forms.View.List>, puis remplissez le <xref:System.Windows.Forms.ListView> avec des éléments.  
  
2.  Appelez le <xref:System.Windows.Forms.ListView.FindItemWithText%2A> méthode, en passant le texte de l’élément que vous souhaitez rechercher.  
  
3.  L’exemple de code suivant montre comment créer un base <xref:System.Windows.Forms.ListView>, remplir avec des éléments et utiliser l’entrée de texte de l’utilisateur pour rechercher un élément dans la liste.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>Pour rechercher un élément à l’aide des coordonnées x et y  
  
1.  Créer un <xref:System.Windows.Forms.ListView> avec la <xref:System.Windows.Forms.View> propriété la valeur <xref:System.Windows.Forms.View.SmallIcon> ou <xref:System.Windows.Forms.View.LargeIcon>, puis remplissez le <xref:System.Windows.Forms.ListView> avec des éléments.  
  
2.  Appelez le <xref:System.Windows.Forms.ListView.FindNearestItem%2A> méthode, en passant les coordonnées x - et y-souhaitée et la direction que vous souhaitez rechercher.  
  
3.  L’exemple de code suivant montre comment créer une icône de base <xref:System.Windows.Forms.ListView>, remplir avec des éléments, puis capturez la <xref:System.Windows.Forms.Control.MouseDown> pour rechercher l’élément le plus proche dans la direction des événements.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [Contrôle ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Vue d’ensemble du contrôle ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Guide pratique pour ajouter et supprimer des éléments avec le contrôle ListView Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)

---
title: Guide pratique pour changer la propriété FlowDirection d'un contenu par programmation
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 88beba371a9dd8ea54dabe8f541b4a01773982cb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>Guide pratique pour changer la propriété FlowDirection d'un contenu par programmation
Cet exemple montre comment modifier par programmation la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propriété d’un <xref:System.Windows.Controls.FlowDocumentReader>.  
  
## <a name="example"></a>Exemple  
 Deux <xref:System.Windows.Controls.Button> éléments sont créés, chacun représentant l’une des valeurs possibles de <xref:System.Windows.FlowDirection>. Lorsqu’un clic est effectué, la valeur de propriété associée est appliquée au contenu d’un <xref:System.Windows.Controls.FlowDocumentReader> nommé `tf1`.  La valeur de propriété est également écrites dans un <xref:System.Windows.Controls.TextBlock> nommé `txt1`.  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>Exemple  
 Les événements associés aux clics de bouton définis au-dessus sont gérés dans un fichier de code-behind c#.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]

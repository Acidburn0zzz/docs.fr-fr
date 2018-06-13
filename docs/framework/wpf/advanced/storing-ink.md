---
title: Stockage de l'encre
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: d3d33be5e8b5cf9dd7e32a52dfc258aa934c5c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546095"
---
# <a name="storing-ink"></a>Stockage de l'encre
Le <xref:System.Windows.Ink.StrokeCollection.Save%2A> méthodes fournissent la prise en charge pour le stockage d’encre comme Ink Serialized Format (ISF). Les constructeurs pour la <xref:System.Windows.Ink.StrokeCollection> classe prennent en charge pour la lecture des données de l’encre.  
  
## <a name="ink-storage-and-retrieval"></a>Stockage d’encre et de récupération  
 Cette section explique comment stocker et récupérer d’encre dans le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] plateforme.  
  
 L’exemple suivant implémente un gestionnaire d’événements de clic de bouton qui présente une boîte de dialogue Enregistrer l’utilisateur et enregistre l’encre d’un <xref:System.Windows.Controls.InkCanvas> dans un fichier.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 L’exemple suivant implémente un gestionnaire d’événements de clic de bouton qui présente à l’utilisateur avec une boîte de dialogue Ouvrir le fichier et lit l’encre du fichier dans un <xref:System.Windows.Controls.InkCanvas> élément.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Controls.InkCanvas>  
 [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)

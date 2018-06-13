---
title: 'Comment : définir une portée de nom'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: 689c8187fcf17ef48a73bc5a6fc4928f3be1a078
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559713"
---
# <a name="how-to-define-a-name-scope"></a>Comment : définir une portée de nom
Pour animer avec <xref:System.Windows.Media.Animation.Storyboard> dans le code, vous devez créer un <xref:System.Windows.NameScope> et enregistrer les noms des objets cibles avec l’élément qui possède cette portée de nom. Dans l’exemple suivant, un <xref:System.Windows.NameScope> est créée pour `myMainPanel`. Deux boutons, `button1` et `button2`, sont ajoutées dans le panneau de configuration et leurs noms enregistrés. Plusieurs animations et un <xref:System.Windows.Media.Animation.Storyboard> sont créés. La table de montage séquentiel <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> méthode est utilisée pour démarrer les animations.  
  
 Étant donné que `button1`, `button2`, et `myMainPanel` partagent tous la même portée de nom, l’un d’eux peut être utilisé avec le <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> méthode pour démarrer les animations.  
  
## <a name="example"></a>Exemple  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a>Voir aussi  
 [Animer une propriété à l’aide d’une table de montage séquentiel](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Vue d’ensemble de l’animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)

---
title: 'Procédure : Créer un bouton comportant une image'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: cfebe53047531ecddde42a3a0596dfd949629ecd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682060"
---
# <a name="how-to-create-a-button-that-has-an-image"></a>Procédure : Créer un bouton comportant une image
Cet exemple montre comment inclure une image sur un <xref:System.Windows.Controls.Button>.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée deux <xref:System.Windows.Controls.Button> contrôles. Un <xref:System.Windows.Controls.Button> contient du texte et l’autre contient une image. L’image est dans un dossier appelé données, qui sont un sous-dossier du dossier du projet de l’exemple. Lorsqu’un utilisateur clique sur le <xref:System.Windows.Controls.Button> qui a l’image, l’arrière-plan et le texte de l’autre <xref:System.Windows.Controls.Button> modifier.  
  
 Cet exemple crée <xref:System.Windows.Controls.Button> contrôle à l’aide du balisage, mais utilise le code pour écrire la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestionnaires d’événements.  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>Voir aussi
- [Contrôles](../../../../docs/framework/wpf/controls/index.md)
- [Bibliothèque de contrôles](../../../../docs/framework/wpf/controls/control-library.md)

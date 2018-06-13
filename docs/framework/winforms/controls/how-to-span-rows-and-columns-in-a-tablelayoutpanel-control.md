---
title: 'Comment : étendre des lignes et des colonnes dans un contrôle TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a78286be8ef64212d945b3cb11a2963d5a1b2e79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535345"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Comment : étendre des lignes et des colonnes dans un contrôle TableLayoutPanel
Contrôles dans un <xref:System.Windows.Forms.TableLayoutPanel> contrôle peut s’étendre sur les lignes et colonnes adjacentes.  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnalisation des paramètres de développement dans Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-span-columns-and-rows"></a>Pour couvrir des colonnes et lignes  
  
1.  Faites glisser un <xref:System.Windows.Forms.TableLayoutPanel> contrôle depuis la **boîte à outils** vers votre formulaire.  
  
2.  Faites glisser un <xref:System.Windows.Forms.Button> contrôler à partir de la **boîte à outils** dans la cellule supérieure gauche de la <xref:System.Windows.Forms.TableLayoutPanel> contrôle.  
  
3.  Définir le <xref:System.Windows.Forms.Button> du contrôle **ColumnSpan** propriété **2**. Notez que le <xref:System.Windows.Forms.Button> contrôle couvre les première et deuxième colonnes.  
  
4.  Définir le <xref:System.Windows.Forms.Button> du contrôle **RowSpan** propriété **2**. Notez que le <xref:System.Windows.Forms.Button> contrôle s’étend sur les première et deuxième lignes.  
  
5.  Définir le <xref:System.Windows.Forms.Button> du contrôle **ColumnSpan** propriété **1**. Notez que le <xref:System.Windows.Forms.Button> contrôle se déplace dans la première colonne et couvre les première et deuxième lignes.  
  
## <a name="see-also"></a>Voir aussi  
 [TableLayoutPanel, contrôle](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)

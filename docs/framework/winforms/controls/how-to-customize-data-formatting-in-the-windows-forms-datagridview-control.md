---
title: 'Comment : personnaliser la mise en forme des données dans le contrôle DataGridView Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: da016bf659f9eef06074f52e5b716e73d514e48b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a>Comment : personnaliser la mise en forme des données dans le contrôle DataGridView Windows Forms
L'exemple de code suivant montre comment implémenter un gestionnaire pour l'événement <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> qui modifie le mode d'affichage des cellules en fonction de leurs colonnes et de leurs valeurs.  
  
 Les cellules de la colonne `Balance` qui contiennent des nombres négatifs ont un arrière-plan rouge. Vous pouvez également appliquer la mise en forme « Monnaie » à ces cellules pour afficher les valeurs négatives entre parenthèses. Pour plus d’informations, consultez [Comment : mettre en forme des données dans le contrôle DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
 Les cellules de la colonne `Priority` affichent des images au lieu des valeurs de cellules textuelles correspondantes. La propriété <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> de <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> sert à obtenir la valeur de la cellule textuelle et à définir la valeur d'affichage d'image correspondante.  
  
## <a name="example"></a>Exemple  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Cet exemple nécessite :  
  
-   des références aux assemblys System, System.Drawing et System.Windows.Forms ;  
  
-   des images <xref:System.Drawing.Bitmap> nommées `highPri.bmp`, `mediumPri.bmp` et `lowPri.bmp` résidant dans le même répertoire que le fichier exécutable.  
  
 Pour plus d’informations sur la création de cet exemple à partir de la ligne de commande pour Visual Basic ou Visual c#, consultez [génération à partir de la ligne de commande](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [de ligne de commande avec csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Vous pouvez également générer cet exemple dans Visual Studio en collant le code dans un nouveau projet.  Consultez également la page [Comment : compiler et exécuter un exemple complet de code Windows Forms à l’aide de Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Drawing.Bitmap>  
 [Affichage des données dans le contrôle DataGridView Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Guide pratique pour mettre en forme des données dans le contrôle DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [Styles de cellules dans le contrôle DataGridView Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Mise en forme de données dans le contrôle DataGridView Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)

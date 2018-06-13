---
title: Guide pratique pour afficher le composant PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: d8765187522f8becf24b519434b7c170c1c755b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532185"
---
# <a name="how-to-display-the-printdialog-component"></a>Guide pratique pour afficher le composant PrintDialog
Le <xref:System.Windows.Forms.PrintDialog> composant est la boîte de dialogue d’impression Windows standard que la plupart de vos utilisateurs seront familiers. Étant donné que vos utilisateurs seront immédiatement à l’aise avec elle, il serait utile pour pouvoir utiliser le <xref:System.Windows.Forms.PrintDialog> composant.  
  
### <a name="to-display-the-printdialog-component"></a>Pour afficher le composant PrintDialog  
  
-   Appelez le <xref:System.Windows.Forms.Form.ShowDialog%2A> méthode à partir du code de votre application.  
  
     Une fois le composant affiché, les utilisateurs interagissent avec lui et définissent les propriétés du travail d’impression. Celles-ci sont enregistrées dans le <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` classe (et le <xref:System.Drawing.Printing.PageSettings> classe, si l’utilisateur accède à la [PageSetupDialog (composant)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) via la <xref:System.Windows.Forms.PrintDialog> composant) associé à ce travail d’impression. Vous pouvez ensuite faire des appels aux propriétés qu’elles définissent pour déterminer les caractéristiques du travail d’impression.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour créer des travaux d’impression Windows Forms standard](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [Guide pratique pour capturer une entrée d’utilisateur à partir d’un composant PrintDialog au moment de l’exécution](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [PrintPreviewDialog, contrôle](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [PrintDialog, composant](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [Prise en charge de l’impression dans les Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Contrôles Windows Forms](../../../../docs/framework/winforms/controls/index.md)

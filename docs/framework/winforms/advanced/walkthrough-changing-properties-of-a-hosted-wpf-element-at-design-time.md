---
title: "Procédure pas à pas : modification des propriétés d'un élément WPF hébergé au moment du design"
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: 15cab9266af5840aa4b37a62b71bd5010b7a859a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535640"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a>Procédure pas à pas : modification des propriétés d'un élément WPF hébergé au moment du design
Cette procédure pas à pas montre comment modifier les valeurs de propriétés d'un contrôle Windows Presentation Foundation (WPF) hébergé sur un Windows Form.  
  
 Lors de cette procédure pas à pas, vous allez exécuter les tâches suivantes :  
  
-   créer le projet ;  
  
-   créer le contrôle WPF ;  
  
-   héberger les contrôles WPF sur un Windows Form ;  
  
-   utiliser le Concepteur WPF pour Visual Studio pour modifier les valeurs de propriétés.  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Prérequis  
 Pour exécuter cette procédure pas à pas, vous devez disposer des composants suivants :  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>Création du projet  
 La première étape consiste à créer le projet Windows Forms.  
  
> [!NOTE]
>  Lors de l'hébergement de contenu WPF, seuls les projets Visual Basic et C# sont pris en charge.  
  
#### <a name="to-create-the-project"></a>Pour créer le projet  
  
-   Créer un nouveau projet d’Application de Windows Forms dans Visual Basic ou Visual c# nommé `WpfHost`.  
  
## <a name="creating-the-wpf-control"></a>Création du contrôle WPF  
 Après avoir ajouté un contrôle WPF au projet, vous pouvez le disposer sur le formulaire.  
  
#### <a name="to-create-wpf-controls"></a>Pour créer des contrôles WPF  
  
1.  Ajoutez un nouveau <xref:System.Windows.Controls.UserControl> WPF au projet. Utilisez le nom par défaut pour le type de contrôle, `UserControl1.xaml`. Pour plus d’informations, consultez [procédure pas à pas : création de nouveau contenu WPF sur les formulaires Windows au moment du Design](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Dans le **propriétés** fenêtre, définissez la valeur de la <xref:System.Windows.Controls.Control.Background%2A> propriété `Blue`.  
  
3.  Générez le projet.  
  
## <a name="changing-property-values-on-the-wpf-control"></a>Modification de valeurs de propriétés sur le contrôle WPF  
 Le Smart Tag <xref:System.Windows.Forms.Integration.ElementHost> facilite la modification des propriétés du contenu WPF hébergé à l'aide du Concepteur WPF.  
  
#### <a name="to-host-a-wpf-control"></a>Pour héberger un contrôle WPF  
  
1.  Ouvrez `Form1` dans le Concepteur Windows Forms.  
  
2.  Dans le **boîte à outils**, dans le **contrôles utilisateur WPF** onglet, double-cliquez sur `UserControl1` pour créer une instance de `UserControl1` sur le formulaire.  
  
     L'instance de `UserControl1` est hébergée dans un nouveau contrôle <xref:System.Windows.Forms.Integration.ElementHost> nommé `elementHost1`.  
  
3.  Dans le **tâches ElementHost** panneau des balises actives, sélectionnez **modifier le contenu hébergé**.  
  
     UserControl1.xaml s'ouvre dans le Concepteur WPF.  
  
4.  Dans le **propriétés** fenêtre, définissez la valeur de la <xref:System.Windows.Controls.Control.Background%2A> propriété `Red`.  
  
5.  Regénérez le projet.  
  
6.  Ouvrez `Form1` dans le Concepteur Windows Forms.  
  
     L'instance de `UserControl1` possède un arrière-plan rouge.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Guide pratique pour ancrer et arrimer des contrôles enfants dans un contrôle TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Guide pratique pour aligner un contrôle sur les bords des formulaires au moment du design](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [Procédure pas à pas : organisation des contrôles dans les Windows Forms à l’aide des lignes d’alignement](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Migration et interopérabilité](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Utilisation de contrôles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Concevoir en XAML dans Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)

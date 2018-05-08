---
title: Styles et modèles ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 0ed9d134a055e5b411ab105b72706839e2f216c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="progressbar-styles-and-templates"></a>Styles et modèles ProgressBar
Cette rubrique décrit les styles et modèles pour la <xref:System.Windows.Controls.ProgressBar> contrôle. Vous pouvez modifier la valeur par défaut <xref:System.Windows.Controls.ControlTemplate> pour donner une apparence unique au contrôle. Pour plus d’informations, consultez [Personnalisation de l’apparence d’un contrôle existant en créant un ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="progressbar-parts"></a>Parties de la barre de progression  
 Le tableau suivant répertorie les composants nommés pour le <xref:System.Windows.Controls.ProgressBar> contrôle.  
  
|Élément|Type|Description|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|Objet qui indique la progression.|  
|PART_Track|<xref:System.Windows.FrameworkElement>|Objet qui définit le chemin d’accès de l’indicateur de progression.|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|Objet qui embellit la barre de progression.|  
  
## <a name="progressbar-states"></a>États de la barre de progression  
 Le tableau suivant répertorie les états visuels pour le <xref:System.Windows.Controls.ProgressBar> contrôle.  
  
|Nom VisualState|Nom VisualStateGroup|Description|  
|----------------------|---------------------------|-----------------|  
|Déterminé|CommonStates|<xref:System.Windows.Controls.ProgressBar> signale la progression en fonction de la <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> propriété.|  
|Indéterminé|CommonStates|<xref:System.Windows.Controls.ProgressBar> signale la progression générale avec un modèle extensible.|  
|Valide|ValidationStates|Le contrôle utilise le <xref:System.Windows.Controls.Validation> classe et le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `false`.|  
|InvalidFocused|ValidationStates|Le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `true` a le contrôle a le focus.|  
|InvalidUnfocused|ValidationStates|Le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `true` a le contrôle n’a pas le focus.|  
  
## <a name="progressbar-controltemplate-example"></a>ProgressBar ControlTemplate, exemple  
 L’exemple suivant montre comment définir un <xref:System.Windows.Controls.ControlTemplate> pour la <xref:System.Windows.Controls.ProgressBar> contrôle.  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 L’exemple précédent utilise une ou plusieurs des ressources suivantes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Pour voir l’exemple complet, consultez [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041) (Exemple de style avec ControlTemplates).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Styles et modèles Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Personnalisation des contrôles](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Application d’un style et création de modèles](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personnalisation de l’apparence d’un contrôle existant en créant un ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)

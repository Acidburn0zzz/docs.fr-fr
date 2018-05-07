---
title: 'Comment : contrôler quand le texte TextBox met à jour la source'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 52f3a8d3a5d78a211367722b3042eb50f6ac36d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Comment : contrôler quand le texte TextBox met à jour la source
Cette rubrique explique comment utiliser le <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propriété pour contrôler le minutage des mises à jour de la source de liaison. La rubrique utilise le <xref:System.Windows.Controls.TextBox> contrôle comme exemple.  
  
## <a name="example"></a>Exemple  
 L’élément de langage <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> propriété a une valeur par défaut <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valeur <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Cela signifie que si une application possède un <xref:System.Windows.Controls.TextBox> avec une limite de données <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> propriété, le texte que vous tapez dans le <xref:System.Windows.Controls.TextBox> ne met pas à jour la source jusqu'à ce que le <xref:System.Windows.Controls.TextBox> perd le focus (par exemple, lorsque vous cliquez en dehors de la <xref:System.Windows.Controls.TextBox>).  
  
 Si vous souhaitez que la source de mise à jour en cours de frappe, définissez le <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> de la liaison à <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Dans l’exemple suivant, les lignes en surbrillance du code qui montrent la `Text` propriétés des deux le <xref:System.Windows.Controls.TextBox> et <xref:System.Windows.Controls.TextBlock> sont liés à la même propriété source. Le <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propriété de la <xref:System.Windows.Controls.TextBox> liaison est définie sur <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 Par conséquent, le <xref:System.Windows.Controls.TextBlock> montre le même texte (car la source change) que l’utilisateur entre du texte dans le <xref:System.Windows.Controls.TextBox>, comme illustré par la capture d’écran suivante de l’exemple :  
  
 ![Capture d’écran : exemple de liaison de données simple](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Si vous disposez d’une boîte de dialogue ou un formulaire modifiables par l’utilisateur et que vous souhaitez différer les mises à jour de la source jusqu'à ce que l’utilisateur a fini de modifier les champs et clique sur « OK », vous pouvez définir le <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valeur de vos liaisons à <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, comme dans l’exemple suivant :  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Lorsque vous définissez la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valeur <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, la valeur source change uniquement lorsque l’application appelle la <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> (méthode). L’exemple suivant montre comment appeler <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> pour `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  Vous pouvez utiliser la même technique pour les propriétés d’autres contrôles, mais n’oubliez pas que la plupart des autres propriétés ont une valeur par défaut <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valeur <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Pour plus d’informations, consultez le <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> page de propriétés.  
  
> [!NOTE]
>  Le <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> propriété porte sur la source des mises à jour et par conséquent concerne uniquement les <xref:System.Windows.Data.BindingMode.TwoWay> ou <xref:System.Windows.Data.BindingMode.OneWayToSource> liaisons. Pour <xref:System.Windows.Data.BindingMode.TwoWay> et <xref:System.Windows.Data.BindingMode.OneWayToSource> liaisons, l’objet source doit fournir des notifications de modification de propriété. Vous pouvez consulter les exemples figurant dans cette rubrique pour plus d’informations. Vous pouvez également consulter la page [Implémenter la notification des modifications de propriétés](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Rubriques de guide pratique](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

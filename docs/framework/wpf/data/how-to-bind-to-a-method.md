---
title: 'Comment : effectuer une liaison à une méthode'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 58e243812f9c2dcb65dc37bfd50d9bcfb124e4f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-to-a-method"></a>Comment : effectuer une liaison à une méthode
L’exemple suivant montre comment lier une méthode à l’aide de <xref:System.Windows.Data.ObjectDataProvider>.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, `TemperatureScale` est une classe qui possède une méthode `ConvertTemp`, qui prend deux paramètres (`TempType)`, un de type `double` et l’autre de type `enum`) et convertit la valeur donnée d’une échelle de température à une autre. Dans l’exemple suivant, un <xref:System.Windows.Data.ObjectDataProvider> est utilisé pour instancier le `TemperatureScale` objet. La méthode `ConvertTemp` est appelée avec deux paramètres spécifiés.  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Maintenant que la méthode est disponible en tant que ressource, vous pouvez effectuer la liaison à ses résultats. Dans l’exemple suivant, la <xref:System.Windows.Controls.TextBox.Text%2A> propriété de la <xref:System.Windows.Controls.TextBox> et <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> de la <xref:System.Windows.Controls.ComboBox> sont liées aux deux paramètres de la méthode. Cela permet aux utilisateurs de spécifier la température à convertir et l’échelle de température à partir de laquelle effectuer la conversion. Notez que <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> a la valeur `true` étant donné que nous créons une liaison avec le <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> propriété de la <xref:System.Windows.Data.ObjectDataProvider> instance et pas les propriétés de l’objet encapsulé par le <xref:System.Windows.Data.ObjectDataProvider> (le `TemperatureScale` objet).  
  
 Le <xref:System.Windows.Controls.ContentControl.Content%2A> du dernier <xref:System.Windows.Controls.Label> met à jour lorsque l’utilisateur modifie le contenu de la <xref:System.Windows.Controls.TextBox> ou la sélection de la <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Le convertisseur `DoubleToString` prend une valeur double et la convertit en une chaîne dans le <xref:System.Windows.Data.IValueConverter.Convert%2A> direction (à partir de la source de liaison à la cible de liaison, qui est la <xref:System.Windows.Controls.TextBox.Text%2A> propriété) et convertit un `string` à un `double` dans le <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direction.  
  
 Le `InvalidationCharacterRule` est un <xref:System.Windows.Controls.ValidationRule> qui vérifie les caractères non valides. Le modèle d’erreur par défaut, qui est une bordure rouge autour de le <xref:System.Windows.Controls.TextBox>, apparaît pour signaler aux utilisateurs la valeur d’entrée n’est pas une valeur double.  
  
## <a name="see-also"></a>Voir aussi  
 [Rubriques de guide pratique](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Effectuer une liaison à une énumération](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)

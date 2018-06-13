---
title: x:XData, type XAML intrinsèque
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 3a16379fd6104342529723bf6d0bc9fb4762cf92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565361"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData, type XAML intrinsèque
Active le positionnement des îlots de données XML dans une production XAML. Éléments XML `x:XData` ne doivent pas être traités par les processeurs XAML comme s’ils faisaient partie de l’espace de noms XAML par défaut d’agissant ou tout autre espace de noms XAML. `x:XData` peut contenir arbitraire XML bien formé.  
  
## <a name="xaml-object-element-usage"></a>Utilisation d'éléments objet XAML  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>Valeurs XAML  
  
|||  
|-|-|  
|`elementDataRoot`|L’élément racine unique de l’îlot de données incorporé. La plupart des consommateurs éventuels, XML qui ne dispose pas d’une racine unique est considéré comme non valide. En particulier, une racine unique est obligatoire si le `x:XData` est destiné à une source de données XML WPF ou bien d’autres technologies qui utilisent des sources XML pour la liaison de données.|  
|`[elementData]`|Facultatif. Code XML qui représente les données XML. N’importe quel nombre d’éléments peut être contenu comme données d’élément et les éléments imbriqués peuvent être contenus dans d’autres éléments ; Toutefois, les règles générales de XML s’appliquent.|  
  
## <a name="remarks"></a>Notes  
 Les éléments XML dans un `x:XData` objet peut déclarer de nouveau tous les espaces de noms possibles et les préfixes le conteneur XMLDOM dans les données.  
  
 L’accès par programme aux données XML et le `x:XData` type XAML intrinsèque est possible dans les Services XAML .NET Framework via la <xref:System.Windows.Markup.XData> classe.  
  
## <a name="wpf-usage-notes"></a>Notes d’utilisation WPF  
 Le `x:XData` objet est principalement utilisé comme un objet enfant d’un <xref:System.Windows.Data.XmlDataProvider>, ou bien, comme l’objet enfant de la <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> propriété (en XAML, cela est exprimé en général dans la syntaxe d’élément de propriété).  
  
 Généralement, les données doivent redéfinir l’espace de noms XML base dans l’îlot de données en tant que nouvel espace de noms XML par défaut (défini sur une chaîne vide). C’est plus facile pour les îlots de données simples, car le <xref:System.Windows.Data.Binding.XPath%2A> expressions sont utilisées pour référencer et lier les données peuvent éviter l’inclusion de préfixes. Les îlots de données plus complexes peuvent définir plusieurs préfixes pour les données et utiliser un préfixe spécifique pour l’espace de noms XML à la racine. Dans ce cas, tous les <xref:System.Windows.Data.Binding.XPath%2A> références d’expression doivent inclure le préfixe mappé en l’espace de noms approprié. Pour plus d’informations, consultez [Vue d’ensemble de la liaison de données](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Techniquement, `x:XData` peut être utilisé en tant que le contenu de n’importe quelle propriété de type <xref:System.Xml.Serialization.IXmlSerializable>. Toutefois, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> est la seule implémentation apparente.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Data.XmlDataProvider>  
 [Vue d’ensemble de la liaison de données](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Binding, extension de balisage](../../../docs/framework/wpf/advanced/binding-markup-extension.md)

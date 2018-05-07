---
title: Limitations de sérialisation de XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: cbe8d517b8794f6aae7190457a077422d235acb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Limitations de sérialisation de XamlWriter.Save
Le [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A> peut être utilisé pour sérialiser le contenu d’un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application en tant qu’un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] fichier. Toutefois, il existe quelques limitations importantes dans ce qui peut être sérialisé. Ces restrictions et certaines considérations d’ordre général sont abordées dans cette rubrique.  
  
 
  
<a name="Run_Time__Not_Design_Time_Representation"></a>   
## <a name="run-time-not-design-time-representation"></a>Représentation au moment de l’exécution, et non du design  
 La philosophie de base de ce qui est sérialisé par un appel à <xref:System.Windows.Markup.XamlWriter.Save%2A> est que le résultat sera une représentation de l’objet sérialisé, au moment de l’exécution. Plusieurs propriétés au moment du design de l’original [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] fichier est peut-être déjà optimisé ou perdu au moment qui le [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] est chargé en tant qu’objets en mémoire et ne sont pas conservées lorsque vous appelez <xref:System.Windows.Markup.XamlWriter.Save%2A> à sérialiser. Le résultat sérialisé est une représentation effective de l’arborescence logique construite de l’application, mais pas nécessairement du [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] d’origine qui l’a produite. Ces questions rendent extrêmement difficile à utiliser le <xref:System.Windows.Markup.XamlWriter.Save%2A> sérialisation dans le cadre d’une étendue [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aire de conception.  
  
<a name="Serialization_is_Self_Contained"></a>   
## <a name="serialization-is-self-contained"></a>La sérialisation est autonome  
 La sortie sérialisée de <xref:System.Windows.Markup.XamlWriter.Save%2A> est autonome ; tout ce qui est sérialisé est contenu dans un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page unique, avec un seul élément racine et aucune référence externe autre que [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]. Par exemple, si votre page référence des ressources d’application, celles-ci apparaissent comme un composant de la page en cours de sérialisation.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## <a name="extension-references-are-dereferenced"></a>Les références d’extension sont déréférencées  
 Les références d’objets communes effectuées dans divers formats d’extension de balisage, tels que `StaticResource` ou `Binding`, seront déréférencées par le processus de sérialisation. Ils ont été déjà déréférencés au moment où les objets en mémoire ont été créés par l’exécution de l’application, et le <xref:System.Windows.Markup.XamlWriter.Save%2A> logique ne revisite pas sur la version d’origine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] à restaurer de telles références dans la sortie sérialisée. Ceci peut forcer l’utilisation d’une valeur liée aux données ou obtenue par des ressources comme dernière valeur utilisée par la représentation au moment de l’exécution, avec seulement une possibilité limitée ou indirecte de distinguer cette valeur des autres valeurs définies localement. Les images sont également sérialisées en tant que références d’objets en images telles qu’elles existent dans le projet, plutôt que comme des références sources d’origine, perdant ainsi le nom de fichier ou le [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] référencé à l’origine. Même les ressources déclarées au sein de la même page sont sérialisées à l’endroit où elles étaient référencées, au lieu d’être conservées en tant que clé d’une collection de ressources.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## <a name="event-handling-is-not-preserved"></a>La gestion des événements n’est pas conservée  
 Lorsque les gestionnaires d’événements qui sont ajoutés via [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sont sérialisés, ils ne sont pas conservés. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sans code-behind (et sans le mécanisme x:Code associé) n’a aucun moyen de sérialiser la logique procédurale du runtime. Étant donné que la sérialisation est autonome et limitée à l’arborescence logique, il n’existe aucun mécanisme permettant de stocker les gestionnaires d’événements. Par conséquent, les attributs de gestionnaire d’événements, l’attribut lui-même et la valeur de chaîne qui nomme le gestionnaire sont supprimés de la sortie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Scénarios réalistes d’utilisation de XAMLWriter.Save  
 Si les limitations énumérées ici sont importantes, il reste toutefois plusieurs scénarios appropriés pour l’utilisation de <xref:System.Windows.Markup.XamlWriter.Save%2A> pour la sérialisation.  
  
-   Sortie de vecteurs ou de graphiques : la sortie de la zone de rendu peut être utilisée pour reproduire les mêmes vecteurs ou graphiques lors du rechargement.  
  
-   Documents dynamiques et au format RTF : le texte, ainsi que toutes les mises en forme et imbrications des éléments qu’ils contiennent sont conservés dans la sortie. Ceci peut être utile pour les mécanismes qui se rapprochent de la fonctionnalité de Presse-papiers.  
  
-   Conservation des données d’objets métier : si vous avez stocké des données dans des éléments personnalisés, tels que des données [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], tant que vos objets métier suivent les règles [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de base telles que la fourniture de constructeurs personnalisés et la conversion de valeurs de propriété par référence, ces objets métier peuvent être conservés après la sérialisation.

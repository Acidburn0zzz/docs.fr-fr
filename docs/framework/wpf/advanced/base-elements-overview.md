---
title: Vue d'ensemble des éléments de base
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: bcfcb87d0ddf5181a47d459e821bacd9b9f6b61c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541831"
---
# <a name="base-elements-overview"></a>Vue d'ensemble des éléments de base
Un pourcentage élevé de classes dans [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] est dérivé de quatre classes souvent appelées classes d’éléments de base dans la documentation du [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]. Ces classes sont <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>, et <xref:System.Windows.FrameworkContentElement>. Le <xref:System.Windows.DependencyObject> classe est également liée, car il s’agit d’une classe de base commune des deux <xref:System.Windows.UIElement> et <xref:System.Windows.ContentElement>  
 
  
<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>API d’élément de base dans les classes WPF  
 Les deux <xref:System.Windows.UIElement> et <xref:System.Windows.ContentElement> sont dérivés de <xref:System.Windows.DependencyObject>, par le biais des voies quelque peu différentes. Le fractionnement à ce niveau est consacrée un <xref:System.Windows.UIElement> ou <xref:System.Windows.ContentElement> sont utilisés dans une interface utilisateur et de leur utilité dans une application. <xref:System.Windows.UIElement> a également <xref:System.Windows.Media.Visual> dans sa hiérarchie de classe, qui est une classe qui expose la prise en charge de graphiques de niveau inférieur sous-jacent le [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual> Fournit une infrastructure de rendu en définissant des régions d’écran rectangulaires indépendantes. Dans la pratique, <xref:System.Windows.UIElement> est pour les éléments qui prendra en charge un plus grand modèle d’objet sont destinés à effectuer le rendu et mise en page dans des régions qui peut être décrit comme régions d’écran rectangulaires, et où le modèle de contenu est délibérément plus ouvert pour autoriser un autre combinaisons d’éléments. <xref:System.Windows.ContentElement> ne dérive pas de <xref:System.Windows.Media.Visual>; son modèle un <xref:System.Windows.ContentElement> doit être consommé par autre chose, tel qu’un lecteur ou une visionneuse qui interprète les éléments ensuite et produire le <xref:System.Windows.Media.Visual> pour [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] à consommer. Certaines <xref:System.Windows.UIElement> classes sont destinés à être des hôtes de contenu : ils fournissent l’hébergement et le rendu d’un ou plusieurs <xref:System.Windows.ContentElement> classes (<xref:System.Windows.Controls.DocumentViewer> est un exemple d’une telle classe). <xref:System.Windows.ContentElement> est utilisé comme classe de base pour les éléments avec des modèles objet un peu plus petits et que plus le texte, les informations d’adresses ou le contenu de document qui peuvent être hébergés dans un <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Niveau de framework et niveau principal  
 <xref:System.Windows.UIElement> sert de classe de base pour <xref:System.Windows.FrameworkElement>, et <xref:System.Windows.ContentElement> sert de classe de base pour <xref:System.Windows.FrameworkContentElement>. La raison de ce niveau suivant de classes est de prendre en charge un niveau principal WPF qui est distinct d’un niveau de framework WPF, cette division existant aussi dans la manière dont les [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] sont réparties entre les assemblys PresentationCore et PresentationFramework. Le niveau de framework WPF représente une solution plus complète pour les besoins d’application de base, y compris l’implémentation du gestionnaire de présentation pour les présentations. Le niveau principal WPF offre un moyen d’utiliser la majeure partie de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sans utiliser la charge mémoire de l’assembly supplémentaire. La distinction entre ces niveaux est très rarement importante pour la plupart des scénarios de développement d’applications standard et, en général, nous vous conseillons de considérer les [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dans leur ensemble et de ne pas vous soucier de la différence entre le niveau de framework WPF et le niveau principal WPF. Vous devez pouvoir être renseigné sur les distinctions de niveau si votre conception d’applications choisit de remplacer de nombreuses fonctionnalités au niveau framework WPF, par exemple si votre solution globale possède déjà ses propres implémentations de composition d’[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] et de mise en page.  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Choisir de quel élément dériver  
 La méthode la plus pratique pour créer une classe personnalisée qui étend [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste à dériver de l’une des classes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] où vous récupérez le plus de fonctionnalités possibles que vous désirez par le biais de la hiérarchie de classes existante. Cette section répertorie les fonctionnalités qui sont fournies avec trois des plus importantes classes d’élément pour vous aider à décider de quelle classe hériter.  
  
 Si vous implémentez un contrôle, qui est réellement une des causes plus courantes pour dériver d’un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (classe), vous souhaiterez probablement dériver d’une classe qui est un contrôle pratique, une classe de base de famille de contrôle, ou au moins de la <xref:System.Windows.Controls.Control> classe de base. Pour obtenir de l’aide et des exemples pratiques, consultez [Vue d’ensemble de la création de contrôles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Si vous ne créez pas de contrôle mais que vous avez besoin de dériver d’une classe plus haute dans la hiérarchie, les sections suivantes sont prévues pour vous servir de guide des caractéristiques définies dans chaque classe d’élément de base.  
  
 Si vous créez une classe qui dérive de <xref:System.Windows.DependencyObject>, vous héritez des fonctionnalités suivantes :  
  
-   <xref:System.Windows.DependencyObject.GetValue%2A> et <xref:System.Windows.DependencyObject.SetValue%2A> prise en charge et la prise en charge du système de propriétés Général.  
  
-   Capacité d’utiliser les propriétés de dépendance et les propriétés jointes implémentées comme propriétés de dépendance.  
  
 Si vous créez une classe qui dérive de <xref:System.Windows.UIElement>, vous héritez de la fonctionnalité suivante en plus de celle fournie par <xref:System.Windows.DependencyObject>:  
  
-   Prise en charge de base pour les valeurs de propriété animées. Pour plus d’informations, consultez [Vue d’ensemble de l’animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Prise en charge de base des événements d’entrée et prise en charge des commandes. Pour plus d’informations, consultez [Vue d’ensemble des entrées](../../../../docs/framework/wpf/advanced/input-overview.md) et [Vue d’ensemble des commandes](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
-   Méthodes virtuelles qui peuvent être substituées pour fournir des informations à un système de disposition.  
  
 Si vous créez une classe qui dérive de <xref:System.Windows.FrameworkElement>, vous héritez de la fonctionnalité suivante en plus de celle fournie par <xref:System.Windows.UIElement>:  
  
-   Prise en charge des styles et des tables de montage séquentiel. Pour plus d’informations, consultez <xref:System.Windows.Style> et [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
-   Prise en charge de la liaison de données. Pour plus d’informations, consultez [Vue d’ensemble de la liaison de données](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Prise en charge des références de ressource dynamique. Pour plus d’informations, consultez [Ressources XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Prise en charge de l’héritage de la valeur de propriété, et d’autres indicateurs dans les métadonnées qui aident à faire part des conditions traitant des propriétés aux services de framework, comme la liaison de données, les styles ou l’implémentation du framework de disposition. Pour plus d’informations, consultez [Métadonnées de propriété de framework](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Le concept de l’arborescence logique. Pour plus d’informations, consultez [Arborescences dans WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
-   Prise en charge pour l’implémentation pratique de niveau infrastructure WPF de système de disposition, y compris un <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> remplacement qui peut détecter des modifications aux propriétés qui influencent la disposition.  
  
 Si vous créez une classe qui dérive de <xref:System.Windows.ContentElement>, vous héritez de la fonctionnalité suivante en plus de celle fournie par <xref:System.Windows.DependencyObject>:  
  
-   Prise en charge des animations. Pour plus d’informations, consultez [Vue d’ensemble de l’animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Prise en charge de base des événements d’entrée et prise en charge des commandes. Pour plus d’informations, consultez [Vue d’ensemble des entrées](../../../../docs/framework/wpf/advanced/input-overview.md) et [Vue d’ensemble des commandes](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 Si vous créez une classe qui dérive de <xref:System.Windows.FrameworkContentElement>, vous obtenez la fonctionnalité suivante en plus de celles fournie par <xref:System.Windows.ContentElement>:  
  
-   Prise en charge des styles et des tables de montage séquentiel. Pour plus d’informations, consultez <xref:System.Windows.Style> et [vue d’ensemble de l’Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Prise en charge de la liaison de données. Pour plus d’informations, consultez [Vue d’ensemble de la liaison de données](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Prise en charge des références de ressource dynamique. Pour plus d’informations, consultez [Ressources XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Prise en charge de l’héritage de la valeur de propriété, et d’autres indicateurs dans les métadonnées qui aident à faire part des conditions traitant des propriétés aux services de framework, comme la liaison de données, les styles ou l’implémentation du framework de disposition. Pour plus d’informations, consultez [Métadonnées de propriété de framework](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Vous n’héritez pas de l’accès aux modifications du système de disposition (tel que <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Les implémentations de système de disposition sont uniquement disponibles sur <xref:System.Windows.FrameworkElement>. Toutefois, vous héritez une <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> remplacement qui peut détecter les modifications apportées aux propriétés qui influencent la disposition et les signalent aux hôtes de contenu.  
  
 Les modèles de contenu sont documentés pour diverses classes. Le modèle de contenu pour une classe est l’un des facteurs dont vous devez tenir compte si vous souhaitez rechercher une classe appropriée à partir de laquelle dériver. Pour plus d’informations, consultez [Modèle de contenu WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Autres classes de base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> Fournit la prise en charge pour le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modèle thread et Active tous les objets créés pour [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications à associer à un <xref:System.Windows.Threading.Dispatcher>. Même si vous ne dérivez pas de <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>, ou <xref:System.Windows.Media.Visual>, vous devez envisager de dériver à partir de <xref:System.Windows.Threading.DispatcherObject> afin d’obtenir cette prise en charge du modèle thread. Pour plus d’informations, consultez [Modèle de thread](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
### <a name="visual"></a>Élément visuel  
 <xref:System.Windows.Media.Visual> implémente le concept d’un objet 2D qui requiert généralement une présentation visuelle dans une zone rectangulaire à peu près. Le rendu réel d’un <xref:System.Windows.Media.Visual> se produit dans d’autres classes (il n’est pas autonome), mais la <xref:System.Windows.Media.Visual> classe fournit un type connu qui est utilisé par le processus de rendu à différents niveaux. <xref:System.Windows.Media.Visual> implémente le test de positionnement, mais il n’expose pas les événements qui signalent les résultats positifs du test de positionnement (ils se trouvent dans <xref:System.Windows.UIElement>). Pour plus d’informations, consultez [Programmation de la couche visuelle](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable> simule l’immuabilité dans un objet mutable en fournissant les moyens permettant de générer des copies de l’objet lorsqu’un objet immuable est requis ou souhaité pour des raisons de performances. Le <xref:System.Windows.Freezable> type fournit une base commune pour certains éléments graphiques tels que les géométries et les pinceaux, ainsi que les animations. En particulier, un <xref:System.Windows.Freezable> n’est pas un <xref:System.Windows.Media.Visual>; il peut contenir des propriétés qui deviennent des sous-propriétés lorsque le <xref:System.Windows.Freezable> est appliqué pour remplir une valeur de propriété d’un autre objet, et ces sous-propriétés peuvent affecter le rendu. Pour plus d’informations, consultez [Vue d’ensemble des objets Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> est un <xref:System.Windows.Freezable> classe dérivée qui ajoute spécifiquement la couche de contrôle d’animation et quelques membres utilitaires afin que les propriétés actuellement animées puissent être distinguées distinguées des propriétés.  
  
### <a name="control"></a>Contrôle  
 <xref:System.Windows.Controls.Control> est la classe de base prévue pour le type d’objet appelé tantôt contrôle ou composant, selon la technologie. En général, les classes de contrôle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sont des classes qui représentent directement un contrôle d’interface utilisateur ou qui participent étroitement à la composition de contrôle. La fonctionnalité principale qui <xref:System.Windows.Controls.Control> active est la création de modèles de contrôle.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Controls.Control>  
 [Vue d’ensemble des propriétés de dépendance](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Vue d’ensemble de la création de contrôles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [Architecture de WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)

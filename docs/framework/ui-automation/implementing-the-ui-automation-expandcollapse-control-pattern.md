---
title: Implémentation du modèle de contrôle ExpandCollapse d'UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, ExpandCollapse control pattern
- ExpandCollapse control pattern
- control patterns, ExpandCollapse
ms.assetid: 1dbabb8c-0d68-47c1-a35e-1c01cb01af26
ms.openlocfilehash: ff07f5264ccb3ec699e3676a2e9ba64443b2875f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211658"
---
# <a name="implementing-the-ui-automation-expandcollapse-control-pattern"></a>Implémentation du modèle de contrôle ExpandCollapse d'UI Automation
> [!NOTE]
>  Cette documentation s'adresse aux développeurs .NET Framework qui souhaitent utiliser les classes [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] managées définies dans l'espace de noms <xref:System.Windows.Automation>. Pour plus d’informations sur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consultez [Windows Automation API : UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Cette rubrique présente les conventions et directives à respecter pour implémenter <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>, notamment les informations sur les propriétés, les méthodes et les événements. Des liens vers des références supplémentaires sont répertoriés à la fin de la vue d'ensemble.  
  
 Le modèle de contrôle <xref:System.Windows.Automation.ExpandCollapsePattern> est utilisé pour prendre en charge les contrôles qui peuvent être visuellement développés pour afficher davantage de contenu et réduits pour masquer le contenu. Pour obtenir des exemples de contrôles qui implémentent ce modèle de contrôle, consultez [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Conventions et recommandations en matière d'implémentation  
 Quand vous implémentez le modèle de contrôle ExpandCollapse, notez les conventions et directives suivantes :  
  
-   Les contrôles d'agrégat, générés avec des objets enfants qui fournissent la fonctionnalité de développement/réduction à l'interface utilisateur, doivent prendre en charge le modèle de contrôle <xref:System.Windows.Automation.ExpandCollapsePattern> même si leurs éléments enfants ne le font pas. Par exemple, un contrôle zone de liste déroulante est généré avec une combinaison de contrôles zone de liste, de contrôles bouton et de contrôles d'édition, mais seule la zone de liste déroulante parente doit prendre en charge <xref:System.Windows.Automation.ExpandCollapsePattern>.  
  
    > [!NOTE]
    >  Le contrôle de menu, qui est un agrégat d'objets MenuItem individuels, fait exception à cette règle. Les objets MenuItem peuvent prendre en charge le modèle de contrôle <xref:System.Windows.Automation.ExpandCollapsePattern> , mais le contrôle Menu parent ne le peut pas. Une exception semblable s'applique aux contrôles Tree et Tree Item.  
  
-   Quand l' <xref:System.Windows.Automation.ExpandCollapseState> d'un contrôle est défini sur <xref:System.Windows.Automation.ExpandCollapseState.LeafNode>, toute fonctionnalité <xref:System.Windows.Automation.ExpandCollapsePattern> est actuellement inactive pour le contrôle et la seule information qui peut être obtenue à l'aide de ce modèle de contrôle est l' <xref:System.Windows.Automation.ExpandCollapseState>. Si des objets enfants sont ajoutés par la suite, l' <xref:System.Windows.Automation.ExpandCollapseState> change et la fonctionnalité <xref:System.Windows.Automation.ExpandCollapsePattern> est activée.  
  
-   <xref:System.Windows.Automation.ExpandCollapseState> fait référence à la visibilité des objets enfants immédiats uniquement ; Il ne fait pas référence à la visibilité de tous les objets descendants.  
  
-   La fonctionnalité de développement/réduction est propre au contrôle. Voici des exemples de ce comportement.  
  
    -   Le menu personnel d'Office peut être un MenuItem à trois états (<xref:System.Windows.Automation.ExpandCollapseState.Expanded>, <xref:System.Windows.Automation.ExpandCollapseState.Collapsed> et <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>) où le contrôle spécifie l'état à adopter quand un <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> ou <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> est appelé.  
  
    -   L'appel d' <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> sur un TreeItem peut afficher tous les descendants ou seulement les enfants immédiats.  
  
    -   Si l'appel d' <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> ou de <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> sur un contrôle maintient l'état de ses descendants, un événement de modification de la visibilité doit être envoyé, et non un événement de modification d'état. Si le contrôle parent ne maintient pas l'état de ses descendants quand il est réduit, le contrôle peut détruire tous les descendants qui ne sont plus visibles et déclencher un événement détruit, ou bien il peut modifier l' <xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A> pour chaque descendant et déclencher un événement de modification de la visibilité.  
  
-   Pour assurer la navigation, il est souhaitable qu'un objet se trouve dans l'arborescence [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (avec l'état de visibilité approprié), quel que soit l' <xref:System.Windows.Automation.ExpandCollapseState>de ses parents. Si des descendants sont générés à la demande, il est possible qu'ils n'apparaissent dans l'arborescence [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] qu'après leur premier affichage ou que quand ils sont visibles.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-iexpandcollapseprovider"></a>Membres nécessaires pour IExpandCollapseProvider  
 Les propriétés et méthodes suivantes sont nécessaires à l'implémentation d' <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.  
  
|Membres requis|Type de membre|Notes|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A>|Propriété|Aucun.|  
|<xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A>|Méthode|Aucun.|  
|<xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A>|Méthode|Aucun.|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|Événement|Aucun événement n'est associé à ce contrôle ; utilisez ce délégué générique.|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Exceptions  
 Les fournisseurs doivent lever les exceptions suivantes.  
  
|Type d'exception|Condition|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Soit <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> ou <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> est appelée lorsque le <xref:System.Windows.Automation.ExpandCollapseState>  =  <xref:System.Windows.Automation.ExpandCollapseState.LeafNode>.|  
  
## <a name="see-also"></a>Voir aussi

- [Vue d'ensemble des modèles de contrôle UI Automation](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Prendre en charge des modèles de contrôle dans un fournisseur UI Automation](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Modèles de contrôle UI Automation pour les clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Naviguer entre les éléments UI Automation avec TreeWalker](../../../docs/framework/ui-automation/navigate-among-ui-automation-elements-with-treewalker.md)
- [Vue d’ensemble de l’arborescence UI Automation](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Utiliser la mise en cache dans UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)

---
title: ToolBar, contrôle (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 3f0a1b6a7f83753ccae1a129528ed320a2613122
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723033"
---
# <a name="toolbar-control-windows-forms"></a>ToolBar, contrôle (Windows Forms)
> [!NOTE]
>  Le contrôle <xref:System.Windows.Forms.ToolStrip> remplace le contrôle `ToolBar` et lui ajoute des fonctionnalités ; toutefois, le contrôle `ToolBar` est conservé pour la compatibilité descendante et l'utilisation future si tel est votre choix.  
  
 Le contrôle Windows Forms `ToolBar` est utilisé sur les formulaires comme barre de contrôle affichant une rangée de menus déroulants et de boutons bitmap qui activent des commandes. Ainsi, un clic sur un bouton de barre d'outils revient à choisir une commande de menu. Vous pouvez configurer les boutons pour qu'ils apparaissent et se comportent comme des boutons de commande, des menus déroulants ou des séparateurs. En règle générale, une barre d'outils contient des boutons et des menus qui correspondent à des éléments dans la structure de menu de l'application et fournissent un accès rapide aux commandes et aux fonctions les plus fréquemment utilisées d'une application.  
  
> [!NOTE]
>  La propriété <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> du contrôle `ToolBar` prend une instance de la classe <xref:System.Windows.Forms.ContextMenu> comme référence. Vous devez faire attention à la référence que vous passez lors de l'implémentation de ce genre de bouton sur les barres d'outils de votre application, car la propriété accepte tout objet qui hérite de la classe <xref:System.Windows.Forms.Menu>.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Vue d’ensemble du contrôle ToolBar](toolbar-control-overview-windows-forms.md)  
 Présente les concepts généraux du contrôle `ToolBar`, qui vous permet de concevoir des barres d'outils personnalisées avec lesquelles les utilisateurs peuvent travailler.  
  
 [Guide pratique pour Ajouter des boutons à un contrôle de barre d’outils](how-to-add-buttons-to-a-toolbar-control.md)  
 Décrit comment ajouter des boutons à un contrôle `ToolBar`.  
  
 [Guide pratique pour Définir une icône pour un bouton de barre d’outils](how-to-define-an-icon-for-a-toolbar-button.md)  
 Décrit comment afficher des icônes dans les boutons d'un contrôle `ToolBar`.  
  
 [Guide pratique pour Déclencher des événements de Menu pour les boutons de barre d’outils](how-to-trigger-menu-events-for-toolbar-buttons.md)  
 Explique comment écrire du code pour interpréter le bouton sur lequel l'utilisateur clique dans un contrôle `ToolBar`.  
  
 Voir également [Guide pratique pour Définir une icône pour un bouton de barre d’outils à l’aide du concepteur](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [Comment : Ajouter des boutons à un contrôle de barre d’outils à l’aide du concepteur](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).  
  
## <a name="reference"></a>Référence  
 Classe <xref:System.Windows.Forms.ToolBar>  
 Fournit des informations de référence sur la classe et ses membres.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Contrôles à utiliser dans les Windows Forms](controls-to-use-on-windows-forms.md)  
 Fournit une liste complète de contrôles Windows Forms, avec des liens vers des informations sur leur utilisation.  
  
 [Contrôle ToolStrip](toolstrip-control-windows-forms.md)  
 Décrit les barres d’outils qui peuvent héberger des menus, des contrôles et des contrôles utilisateur dans les applications Windows Forms.

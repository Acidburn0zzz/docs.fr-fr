---
title: 'Procédure : hériter de la classe UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 5e9bdb6d6628b1c696b7944dc0ea1f4c974c8172
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311407"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a>Procédure : hériter de la classe UserControl
Pour combiner les fonctionnalités d’un ou de plusieurs contrôles Windows Forms avec du code personnalisé, vous pouvez créer un *contrôle utilisateur*. Les contrôles utilisateur allient le développement rapide de contrôles, les fonctionnalités des contrôles Windows Forms standard et la polyvalence des propriétés et méthodes personnalisées. Lorsque vous créez un contrôle utilisateur, un concepteur visible, sur lequel vous pouvez placer des contrôles Windows Forms standard, s’affiche. Ces contrôles conservent toutes leurs fonctionnalités inhérentes, ainsi que l’apparence et le comportement de contrôles standard. Une fois que ces contrôles sont générés dans le contrôle utilisateur, ils ne sont toutefois plus disponibles par le biais du code. Le contrôle utilisateur effectue sa propre peinture et gère également toutes les fonctionnalités de base associées aux contrôles.  
  
> [!NOTE]
>  Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-user-control"></a>Pour créer un contrôle utilisateur  
  
1. Créez un projet de **bibliothèque de contrôles Windows**.  
  
     Un projet est créé avec un contrôle utilisateur vide.  
  
2. Faites glisser des contrôles de l’onglet **Windows Forms** de la **boîte à outils** vers votre concepteur.  
  
3. Positionnez et concevez ces contrôles comme vous souhaitez qu’ils apparaissent dans le contrôle utilisateur final. Si vous souhaitez permettre aux développeurs d’accéder aux contrôles constitutifs, vous devez les déclarer publics ou exposer de manière sélective les propriétés du contrôle constitutif. Pour plus d’informations, consultez [Guide pratique pour Exposer les propriétés des contrôles constitutifs](how-to-expose-properties-of-constituent-controls.md).  
  
4. Implémentez les méthodes ou propriétés personnalisées que votre contrôle intégrera.  
  
5. Appuyez sur F5 pour générer le projet et exécuter votre contrôle dans le **Conteneur de test UserControl**. Pour plus d'informations, voir [Procédure : Tester le comportement au moment de l’exécution d’un UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
## <a name="see-also"></a>Voir aussi

- [Variétés de contrôles personnalisés](varieties-of-custom-controls.md)
- [Procédure : hériter de la classe Control](how-to-inherit-from-the-control-class.md)
- [Procédure : hériter de contrôles Windows Forms existants](how-to-inherit-from-existing-windows-forms-controls.md)
- [Procédure : créer des contrôles pour Windows Forms](how-to-author-controls-for-windows-forms.md)
- [Dépannage des gestionnaires d'événements hérités dans Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Procédure : tester le comportement au moment de l’exécution d’un UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

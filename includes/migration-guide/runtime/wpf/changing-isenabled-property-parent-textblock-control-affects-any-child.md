---
ms.openlocfilehash: 38dd0b33202b8e8f1708ebec689333bd5367c93f
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760682"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>La modification de la propriété IsEnabled du parent d’un contrôle TextBlock affecte tous les contrôles enfants

|   |   |
|---|---|
|Détails|À compter du.NET Framework 4.6.2, la modification de la propriété <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> du parent d’un contrôle <xref:System.Windows.Controls.TextBlock?displayProperty=name> affecte tous les contrôles enfants (comme les liens hypertexte et les boutons) du contrôle <xref:System.Windows.Controls.TextBlock?displayProperty=name>. Dans le .NET Framework 4.6.1 et antérieur, les contrôles à l’intérieur d’une <xref:System.Windows.Controls.TextBlock?displayProperty=name> ne reflétaient pas toujours l’état de la propriété <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> du parent de <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Suggestion|Aucun. Cette modification est conforme au comportement attendu pour les contrôles à l’intérieur d’un contrôle <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Portée|Mineur|
|Version|4.6.2|
|Type|Runtime|
|API affectées|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|


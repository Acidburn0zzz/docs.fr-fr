---
title: Utilisation de doubles tampons d'enregistrements
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 9b09210eba0ac3a141219a7cdbff15f22c6ed003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="using-double-buffering"></a>Utilisation de doubles tampons d'enregistrements
Vous pouvez utiliser des graphiques de double tampon pour réduire le scintillement dans vos applications qui contiennent des opérations de peinture complexes. Le .NET Framework contient une prise en charge intégrée de double tampon, ou vous pouvez gérer et restituer manuellement des graphiques.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Graphiques mis deux fois en mémoire tampon](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 Introduit la double mise en mémoire tampon concept et les plans .NET Framework prise en charge.  
  
 [Guide pratique pour réduire le scintillement des graphiques à l’aide de la double mise en mémoire tampon pour les formulaires et les contrôles](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Montre comment utiliser la valeur par défaut de double tampon prise en charge dans le .NET Framework.  
  
 [Guide pratique pour gérer manuellement des graphiques mis en mémoire tampon](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 Montre comment gérer le mécanisme de double tampon dans les applications.  
  
 [Guide pratique pour restituer manuellement des graphiques mis en mémoire tampon](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 Montre comment restituer des graphiques de double tampon.  
  
## <a name="reference"></a>Référence  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 Méthode de contrôle qui active le mécanisme de double tampon.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 Fournit des méthodes pour créer des mémoires tampon de graphiques.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Fournit l’accès au contexte graphique mis en mémoire tampon pour un domaine d’application.

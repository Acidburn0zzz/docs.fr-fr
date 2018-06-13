---
title: 'Comment : créer des figures à partir de lignes, de courbes et de formes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: 222245fa4b3b593e0a38752a8cb991a12e469698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521854"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Comment : créer des figures à partir de lignes, de courbes et de formes
Pour créer une figure, construisez un <xref:System.Drawing.Drawing2D.GraphicsPath>, puis appeler les méthodes, telles que <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> et <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, pour ajouter des primitives au chemin d’accès.  
  
## <a name="example"></a>Exemple  
 Les exemples de code suivants créent des chemins d’accès qui comportent des figures :  
  
-   Le premier exemple crée un chemin d’accès qui a une seule figure. La figure se compose d’un seul arc. L’arc a un angle de balayage de – 180 degrés, qui est dans le sens inverse dans le système de coordonnées par défaut.  
  
-   Le deuxième exemple crée un chemin d’accès qui a deux chiffres. La première représente un arc suivi d’une ligne. La deuxième figure est une ligne suivie d’une courbe de suivi d’une ligne. La première figure est laissée ouverte, et la deuxième figure est fermée.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Les exemples précédents sont conçus pour une utilisation avec Windows Forms, et ils nécessitent <xref:System.Windows.Forms.PaintEventArgs> `e`, qui est un paramètre de la <xref:System.Windows.Forms.Control.Paint> Gestionnaire d’événements.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Génération et dessin de tracés](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [Utilisation d'un stylet pour dessiner des lignes et des formes](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)

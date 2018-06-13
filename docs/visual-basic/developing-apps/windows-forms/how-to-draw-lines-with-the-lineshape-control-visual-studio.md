---
title: 'Comment : dessiner des lignes avec le contrôle LineShape (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 5e1a837578aab4b4609a58ffee46406b022b8f97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587343"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="08a96-102">Comment : dessiner des lignes avec le contrôle LineShape (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="08a96-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="08a96-103">Vous pouvez utiliser la <xref:Microsoft.VisualBasic.PowerPacks.LineShape> contrôle pour dessiner une ligne horizontale, verticale ou diagonale sur un formulaire ou un conteneur, à la fois au moment du design et au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="08a96-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="08a96-104">**Remarque** votre ordinateur peut afficher des noms différents ou des emplacements de l’utilisateur de Visual Studio pour les éléments d’interface dans les instructions suivantes.</span><span class="sxs-lookup"><span data-stu-id="08a96-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="08a96-105">L’édition de Visual Studio dont vous disposez et les paramètres que vous utilisez déterminent ces éléments.</span><span class="sxs-lookup"><span data-stu-id="08a96-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="08a96-106">Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="08a96-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="08a96-107">Pour dessiner une ligne au moment du design</span><span class="sxs-lookup"><span data-stu-id="08a96-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="08a96-108">Faites glisser le <xref:Microsoft.VisualBasic.PowerPacks.LineShape> contrôler à partir de la **Visual Basic PowerPacks** onglet dans le **boîte à outils** faire glisser vers un formulaire ou un contrôle conteneur.</span><span class="sxs-lookup"><span data-stu-id="08a96-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="08a96-109">Faites glisser la poignée et déplacez les poignées pour redimensionner et positionner la ligne.</span><span class="sxs-lookup"><span data-stu-id="08a96-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="08a96-110">Vous pouvez également redimensionner et repositionner la ligne en modifiant le `X1`, `X2`, `Y1`, et `Y2` propriétés dans le **propriétés** fenêtre.</span><span class="sxs-lookup"><span data-stu-id="08a96-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="08a96-111">Dans le **propriétés** fenêtre, vous pouvez également définir des propriétés supplémentaires telles que `BorderStyle` ou `BorderColor` pour modifier l’apparence de la ligne.</span><span class="sxs-lookup"><span data-stu-id="08a96-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="08a96-112">Pour dessiner une ligne en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="08a96-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="08a96-113">Dans le menu **Projet**, cliquez sur **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="08a96-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="08a96-114">Dans le **ajouter une référence** boîte de dialogue, sélectionnez **Microsoft.VisualBasic.PowerPacks.VS**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="08a96-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="08a96-115">Dans le **éditeur de Code**, ajoutez une `Imports` ou `using` instruction en haut du module :</span><span class="sxs-lookup"><span data-stu-id="08a96-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="08a96-116">Ajoutez le code suivant dans une procédure `Event` :</span><span class="sxs-lookup"><span data-stu-id="08a96-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="08a96-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08a96-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [<span data-ttu-id="08a96-118">Introduction aux contrôles Line et Shape</span><span class="sxs-lookup"><span data-stu-id="08a96-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="08a96-119">Guide pratique : dessiner des formes avec les contrôles OvalShape et RectangleShape</span><span class="sxs-lookup"><span data-stu-id="08a96-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)

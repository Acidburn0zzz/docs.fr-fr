---
title: "Vue d'ensemble du contrôle NumericUpDown (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 067a8862ee991213e584819e1cf99eddde06e2bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="numericupdown-control-overview-windows-forms"></a><span data-ttu-id="300a2-102">Vue d'ensemble du contrôle NumericUpDown (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="300a2-102">NumericUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="300a2-103">Le <xref:System.Windows.Forms.NumericUpDown> contrôle se présente comme une combinaison d’une zone de texte et une paire de flèches sur lesquelles l’utilisateur peut cliquer pour ajuster une valeur.</span><span class="sxs-lookup"><span data-stu-id="300a2-103">The <xref:System.Windows.Forms.NumericUpDown> control looks like a combination of a text box and a pair of arrows that the user can click to adjust a value.</span></span> <span data-ttu-id="300a2-104">Le contrôle affiche et définit une valeur numérique unique à partir d’une liste de choix de valeurs numériques fixes.</span><span class="sxs-lookup"><span data-stu-id="300a2-104">The control displays and sets a single numeric value from a list of fixed numeric-value choices.</span></span> <span data-ttu-id="300a2-105">L’utilisateur peut augmenter et diminuer le nombre par le haut et vers le bas flèches, en appuyant sur les touches de direction haut et bas ou en tapant un nombre dans la zone de texte du contrôle.</span><span class="sxs-lookup"><span data-stu-id="300a2-105">The user can increase and decrease the number by clicking the up and down arrows, by pressing the UP and DOWN ARROW keys, or by typing a number in the text box part of the control.</span></span> <span data-ttu-id="300a2-106">En cliquant sur la flèche haut déplace le numéro de la valeur maximale ; en cliquant sur la touche de direction bas déplace le nombre vers la valeur minimale.</span><span class="sxs-lookup"><span data-stu-id="300a2-106">Clicking the UP ARROW key moves the number toward the maximum; clicking the DOWN ARROW key moves the number toward the minimum.</span></span>  
  
 <span data-ttu-id="300a2-107">En raison de ses fonctionnalités polyvalentes, ce contrôle est, par exemple, un choix évident, si vous souhaitez créer un contrôle de volume pour une application de lecteur de musique.</span><span class="sxs-lookup"><span data-stu-id="300a2-107">Because of its versatile functionality, this control is an obvious choice, for example, if you want to create a volume control for a music player application.</span></span> <span data-ttu-id="300a2-108">Le <xref:System.Windows.Forms.NumericUpDown> contrôle est utilisé dans de nombreuses applications du Panneau de configuration Windows.</span><span class="sxs-lookup"><span data-stu-id="300a2-108">The <xref:System.Windows.Forms.NumericUpDown> control is used in many Windows Control Panel applications.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="300a2-109">Méthodes et propriétés de clé</span><span class="sxs-lookup"><span data-stu-id="300a2-109">Key Properties and Methods</span></span>  
 <span data-ttu-id="300a2-110">Les nombres affichés dans la zone de texte du contrôle peuvent être dans divers formats, y compris hexadécimales.</span><span class="sxs-lookup"><span data-stu-id="300a2-110">The numbers displayed in the control's text box can be in a variety of formats, including hexadecimal.</span></span> <span data-ttu-id="300a2-111">Pour plus d’informations, consultez [Comment : mettre en forme le contrôle NumericUpDown Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).</span><span class="sxs-lookup"><span data-stu-id="300a2-111">For more information, see [How to: Set the Format for the Windows Forms NumericUpDown Control](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).</span></span> <span data-ttu-id="300a2-112">Les principales propriétés du contrôle sont <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (valeur par défaut 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (valeur par défaut 0), et <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (valeur par défaut 1).</span><span class="sxs-lookup"><span data-stu-id="300a2-112">The key properties of the control are <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (default value 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (default value 0), and <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (default value 1).</span></span> <span data-ttu-id="300a2-113">Le <xref:System.Windows.Forms.NumericUpDown.Value%2A> propriété définit le nombre actuellement sélectionné dans le contrôle.</span><span class="sxs-lookup"><span data-stu-id="300a2-113">The <xref:System.Windows.Forms.NumericUpDown.Value%2A> property sets the current number selected in the control.</span></span> <span data-ttu-id="300a2-114">Le <xref:System.Windows.Forms.NumericUpDown.Increment%2A> propriété définit le montant que le nombre est ajusté par lorsque l’utilisateur clique sur un haut ou flèche vers le bas.</span><span class="sxs-lookup"><span data-stu-id="300a2-114">The <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property sets the amount that the number is adjusted by when the user clicks an up or down arrow.</span></span> <span data-ttu-id="300a2-115">Lorsque le focus quitte le contrôle, toute valeur entrée est validée sur les valeurs numériques minimales et maximales.</span><span class="sxs-lookup"><span data-stu-id="300a2-115">When focus moves off the control, any typed input will be validated against the minimum and maximum numeric values.</span></span> <span data-ttu-id="300a2-116">Vous pouvez augmenter la vitesse à laquelle le contrôle se déplace à travers les nombres, lorsque l’utilisateur appuie continuellement sur le haut ou flèche bas, avec la <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="300a2-116">You can increase the speed that the control moves through numbers, when the user continuously presses the up or down arrow, with the <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> property.</span></span> <span data-ttu-id="300a2-117">Les principales méthodes du contrôle sont <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> et <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.</span><span class="sxs-lookup"><span data-stu-id="300a2-117">The key methods of the control are <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="300a2-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="300a2-118">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 [<span data-ttu-id="300a2-119">NumericUpDown, contrôle</span><span class="sxs-lookup"><span data-stu-id="300a2-119">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="300a2-120">Guide pratique pour définir le format du contrôle NumericUpDown Windows Forms</span><span class="sxs-lookup"><span data-stu-id="300a2-120">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [<span data-ttu-id="300a2-121">TextBox, contrôle</span><span class="sxs-lookup"><span data-stu-id="300a2-121">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)

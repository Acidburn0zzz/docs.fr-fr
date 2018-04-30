---
title: Collecte d'encre
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f3effe358ba2d7accf1b0eea3493f63cfea6598
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2018
---
# <a name="collecting-ink"></a><span data-ttu-id="b5fdd-102">Collecte d'encre</span><span class="sxs-lookup"><span data-stu-id="b5fdd-102">Collecting Ink</span></span>
<span data-ttu-id="b5fdd-103">La collecte d’encre numérique fait partie des principales fonctionnalités de la plateforme [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md).</span><span class="sxs-lookup"><span data-stu-id="b5fdd-103">The [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="b5fdd-104">Cette rubrique décrit les méthodes de collecte d’encre dans Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="b5fdd-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b5fdd-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="b5fdd-105">Prerequisites</span></span>  
 <span data-ttu-id="b5fdd-106">Pour utiliser les exemples suivants, vous devez d’abord installer [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] et [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5fdd-106">To use the following examples, you must first install [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="b5fdd-107">Vous devez également comprendre comment écrire des applications pour [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5fdd-107">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="b5fdd-108">Pour plus d’informations sur la prise en main de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consultez [procédure pas à pas : Ma première application de bureau WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="b5fdd-108">For more information about getting started with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="using-the-inkcanvas-element"></a><span data-ttu-id="b5fdd-109">Utilisation de l’élément InkCanvas</span><span class="sxs-lookup"><span data-stu-id="b5fdd-109">Using the InkCanvas Element</span></span>  
 <span data-ttu-id="b5fdd-110">Le <xref:System.Windows.Controls.InkCanvas> élément fournit le moyen le plus simple pour collecter de l’encre dans [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5fdd-110">The <xref:System.Windows.Controls.InkCanvas> element provides the easiest way to collect ink in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="b5fdd-111">Le <xref:System.Windows.Controls.InkCanvas> élément est similaire à la [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) de l’objet à partir de la [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] et les versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-111">The <xref:System.Windows.Controls.InkCanvas> element is similar to the [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) object from the [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] and earlier versions.</span></span>  
  
 <span data-ttu-id="b5fdd-112">Utilisez un <xref:System.Windows.Controls.InkCanvas> élément pour recevoir et afficher l’entrée d’encre.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-112">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="b5fdd-113">Généralement, vous entrez de l’encre à l’aide d’un stylet qui interagit avec un digitaliseur pour produire des traits d’encre.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-113">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="b5fdd-114">En outre, vous pouvez utiliser une souris à la place du stylet.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-114">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="b5fdd-115">Les traits créés sont représentés en tant que <xref:System.Windows.Ink.Stroke> objets et elles peuvent être manipulées par programme et par l’utilisateur d’entrée.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-115">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="b5fdd-116">Le <xref:System.Windows.Controls.InkCanvas> permet aux utilisateurs de sélectionner, modifier ou supprimer une existante <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-116">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>  
  
 <span data-ttu-id="b5fdd-117">En utilisant XAML, il est aussi facile d’installer la collecte d’encre que d’ajouter un élément `InkCanvas` à votre arborescence.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-117">By using XAML, you can set up ink collection as easily as adding an `InkCanvas` element to your tree.</span></span> <span data-ttu-id="b5fdd-118">L’exemple suivant ajoute une <xref:System.Windows.Controls.InkCanvas> à une valeur par défaut [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] projet créé dans [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5fdd-118">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] project created in [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].</span></span>  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 <span data-ttu-id="b5fdd-119">L’élément `InkCanvas` peut également contenir des éléments enfants, ce qui permet d’ajouter des fonctions d’annotation manuscrite à quasiment tout type d’élément XAML.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-119">The `InkCanvas` element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="b5fdd-120">Par exemple, pour ajouter des fonctionnalités pour l’écriture manuscrite à un élément de texte, fait simplement en un enfant d’un <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-120">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 <span data-ttu-id="b5fdd-121">Il est tout aussi simple d’ajouter une prise en charge pour baliser une image avec de l’encre.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-121">Adding support for marking up an image with ink is just as easy.</span></span>  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a><span data-ttu-id="b5fdd-122">Modes InkCollection</span><span class="sxs-lookup"><span data-stu-id="b5fdd-122">InkCollection Modes</span></span>  
 <span data-ttu-id="b5fdd-123">Le <xref:System.Windows.Controls.InkCanvas> prend en charge différents modes d’entrée via sa <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-123">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>  
  
### <a name="manipulating-ink"></a><span data-ttu-id="b5fdd-124">Manipulation d’encre</span><span class="sxs-lookup"><span data-stu-id="b5fdd-124">Manipulating Ink</span></span>  
 <span data-ttu-id="b5fdd-125">Le <xref:System.Windows.Controls.InkCanvas> prend en charge de nombreuses opérations de modification de l’encre.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-125">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="b5fdd-126">Par exemple, <xref:System.Windows.Controls.InkCanvas> prend en charge l’arrière du stylet effacer sans code supplémentaire est nécessaire pour ajouter les fonctionnalités à l’élément.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-126">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase with no additional code needed to add the functionality to the element.</span></span>  
  
#### <a name="selection"></a><span data-ttu-id="b5fdd-127">Sélection</span><span class="sxs-lookup"><span data-stu-id="b5fdd-127">Selection</span></span>  
 <span data-ttu-id="b5fdd-128">Paramètre de mode de sélection est aussi simple que le paramètre de la <xref:System.Windows.Controls.InkCanvasEditingMode> propriété **sélectionnez**.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-128">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span> <span data-ttu-id="b5fdd-129">Le code suivant définit le mode de modification en fonction de la valeur d’un <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="b5fdd-129">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a><span data-ttu-id="b5fdd-130">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="b5fdd-130">DrawingAttributes</span></span>  
 <span data-ttu-id="b5fdd-131">Utilisez le <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> propriété à modifier l’apparence des traits d’encre.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-131">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="b5fdd-132">Par exemple, le <xref:System.Windows.Ink.DrawingAttributes.Color%2A> membre <xref:System.Windows.Ink.DrawingAttributes> définit la couleur de rendu <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-132">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="b5fdd-133">L’exemple suivant fait passer la couleur des traits sélectionnés en rouge.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-133">The following example changes the color of the selected strokes to red.</span></span>  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a><span data-ttu-id="b5fdd-134">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="b5fdd-134">DefaultDrawingAttributes</span></span>  
 <span data-ttu-id="b5fdd-135">Le <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propriété fournit l’accès aux propriétés telles que la hauteur, largeur et la couleur des traits à créer dans un <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-135">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="b5fdd-136">Une fois que vous modifiez le <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, tous les futurs traits entrés dans le <xref:System.Windows.Controls.InkCanvas> sont rendus avec les nouvelles valeurs de propriété.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-136">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>  
  
 <span data-ttu-id="b5fdd-137">Outre la modification la <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> dans le fichier code-behind, vous pouvez utiliser la syntaxe XAML pour la spécification <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> propriétés.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-137">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span> <span data-ttu-id="b5fdd-138">Le code XAML suivant montre comment définir le <xref:System.Windows.Ink.DrawingAttributes.Color%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-138">The following XAML code demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="b5fdd-139">Pour utiliser ce code, créez un projet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] intitulé « HelloInkCanvas » dans Visual Studio 2005.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-139">To use this code, create a new [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] project called "HelloInkCanvas" in Visual Studio 2005.</span></span> <span data-ttu-id="b5fdd-140">Remplacez le code du fichier Window1.xaml par le code suivant.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-140">Replace the code in the Window1.xaml file with the following code.</span></span>  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="b5fdd-141">Ensuite, ajoutez les gestionnaires d’événements de bouton suivants au fichier code-behind, dans la classe Window1.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-141">Next, add the following button event handlers to the code behind file, inside the Window1 class.</span></span>  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 <span data-ttu-id="b5fdd-142">Après avoir copié ce code, appuyez sur **F5** dans Microsoft Visual Studio 2005 pour exécuter le programme dans le débogueur.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-142">After copying this code, press **F5** in Microsoft Visual Studio 2005 to run the program in the debugger.</span></span>  
  
 <span data-ttu-id="b5fdd-143">Notez comment la <xref:System.Windows.Controls.StackPanel> place les boutons sur le <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-143">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="b5fdd-144">Si vous tentez d’encre en haut des boutons, le <xref:System.Windows.Controls.InkCanvas> collecte et restitue l’encre derrière les boutons.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-144">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="b5fdd-145">Il s’agit, car les boutons sont des frères de la <xref:System.Windows.Controls.InkCanvas> par opposition aux enfants.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-145">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="b5fdd-146">De même, les boutons sont plus haut dans l’ordre de plan ; l’encre est donc restituée derrière eux.</span><span class="sxs-lookup"><span data-stu-id="b5fdd-146">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5fdd-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5fdd-147">See Also</span></span>  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>

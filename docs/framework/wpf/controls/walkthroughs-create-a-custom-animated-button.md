---
title: "Procédures pas à pas : création d'un bouton animé personnalisé"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 10d723f8a685d76cc739ac88770aad3e1de982ca
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2018
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="e5d11-102">Procédures pas à pas : création d'un bouton animé personnalisé</span><span class="sxs-lookup"><span data-stu-id="e5d11-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="e5d11-103">Comme son nom l’indique, Windows Presentation Foundation (WPF) est idéal pour les présentations variées pour les clients.</span><span class="sxs-lookup"><span data-stu-id="e5d11-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="e5d11-104">Ces procédures pas à pas vous montrent comment personnaliser l’apparence et le comportement d’un bouton (y compris les animations).</span><span class="sxs-lookup"><span data-stu-id="e5d11-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="e5d11-105">Cette personnalisation s’effectue à l’aide d’un style et un modèle afin que vous pouvez appliquer ce bouton personnalisé facilement à des boutons dans votre application.</span><span class="sxs-lookup"><span data-stu-id="e5d11-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="e5d11-106">L’illustration suivante montre le bouton personnalisé que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="e5d11-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="e5d11-107">![Le bouton personnalisé que vous allez créer](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="e5d11-107">![The customized button that you will create](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="e5d11-108">Les graphiques vectoriels qui définissent l’apparence du bouton sont créés à l’aide de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5d11-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="e5d11-109"> est semblable au format HTML mais il est plus puissante et extensible.</span><span class="sxs-lookup"><span data-stu-id="e5d11-109"> is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="e5d11-110"> peut être entré manuellement à l’aide de Microsoft Visual Studio ou le bloc-notes, ou vous pouvez utiliser un outil de conception visuelle tels que Microsoft Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="e5d11-110"> can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="e5d11-111">Expression Blend fonctionne en créant sous-jacent [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de code, afin que les deux méthodes créent les mêmes graphiques.</span><span class="sxs-lookup"><span data-stu-id="e5d11-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5d11-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e5d11-112">In This Section</span></span>  
 [<span data-ttu-id="e5d11-113">Créer un bouton à l'aide de Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="e5d11-113">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="e5d11-114">Montre comment créer des boutons ayant un comportement personnalisé en utilisant les fonctionnalités du Concepteur de Microsoft Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="e5d11-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="e5d11-115">Créer un bouton avec XAML</span><span class="sxs-lookup"><span data-stu-id="e5d11-115">Create a Button by Using XAML</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="e5d11-116">Montre comment créer des boutons ayant un comportement personnalisé à l’aide de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] et Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e5d11-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e5d11-117">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e5d11-117">Related Sections</span></span>  
 [<span data-ttu-id="e5d11-118">Application d’un style et création de modèles</span><span class="sxs-lookup"><span data-stu-id="e5d11-118">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 <span data-ttu-id="e5d11-119">Décrit comment styles et modèles peuvent être utilisées pour déterminer l’apparence et le comportement des contrôles.</span><span class="sxs-lookup"><span data-stu-id="e5d11-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="e5d11-120">Vue d’ensemble de l’animation</span><span class="sxs-lookup"><span data-stu-id="e5d11-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="e5d11-121">Décrit la façon dont les objets peuvent être animées à l’aide de la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation et système de minuterie.</span><span class="sxs-lookup"><span data-stu-id="e5d11-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="e5d11-122">Vue d’ensemble de la peinture avec des couleurs unies ou des dégradés</span><span class="sxs-lookup"><span data-stu-id="e5d11-122">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="e5d11-123">Décrit comment utiliser des objets de pinceau pour peindre avec des couleurs unies, des dégradés linéaires et des dégradés radiaux.</span><span class="sxs-lookup"><span data-stu-id="e5d11-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="e5d11-124">Vue d’ensemble des effets bitmap</span><span class="sxs-lookup"><span data-stu-id="e5d11-124">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="e5d11-125">Décrit les effets bitmap pris en charge par [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] et explique comment les appliquer.</span><span class="sxs-lookup"><span data-stu-id="e5d11-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>

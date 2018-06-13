---
title: Styles et modèles DocumentViewer
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: 217fa0ff7b8c34de817a269effbf64311bbea7f2
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457236"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="21efe-102">Styles et modèles DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="21efe-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="21efe-103">Cette rubrique décrit les styles et modèles pour la <xref:System.Windows.Controls.DocumentViewer> contrôle.</span><span class="sxs-lookup"><span data-stu-id="21efe-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="21efe-104">Vous pouvez modifier la valeur par défaut <xref:System.Windows.Controls.ControlTemplate> pour donner une apparence unique au contrôle.</span><span class="sxs-lookup"><span data-stu-id="21efe-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="21efe-105">Pour plus d’informations, consultez [Personnalisation de l’apparence d’un contrôle existant en créant un ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="21efe-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="21efe-106">Composants de DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="21efe-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="21efe-107">Le tableau suivant répertorie les composants nommés pour le <xref:System.Windows.Controls.DocumentViewer> contrôle.</span><span class="sxs-lookup"><span data-stu-id="21efe-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="21efe-108">Élément</span><span class="sxs-lookup"><span data-stu-id="21efe-108">Part</span></span>|<span data-ttu-id="21efe-109">Type</span><span class="sxs-lookup"><span data-stu-id="21efe-109">Type</span></span>|<span data-ttu-id="21efe-110">Description</span><span class="sxs-lookup"><span data-stu-id="21efe-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="21efe-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="21efe-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="21efe-112">Le contenu et la zone de défilement.</span><span class="sxs-lookup"><span data-stu-id="21efe-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="21efe-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="21efe-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="21efe-114">La zone de recherche, en bas par défaut.</span><span class="sxs-lookup"><span data-stu-id="21efe-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="21efe-115">États de DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="21efe-115">DocumentViewer States</span></span>  
 <span data-ttu-id="21efe-116">Le tableau suivant répertorie les états visuels pour le <xref:System.Windows.Controls.DocumentViewer> contrôle.</span><span class="sxs-lookup"><span data-stu-id="21efe-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="21efe-117">Nom VisualState</span><span class="sxs-lookup"><span data-stu-id="21efe-117">VisualState Name</span></span>|<span data-ttu-id="21efe-118">Nom VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="21efe-118">VisualStateGroup Name</span></span>|<span data-ttu-id="21efe-119">Description</span><span class="sxs-lookup"><span data-stu-id="21efe-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="21efe-120">Valide</span><span class="sxs-lookup"><span data-stu-id="21efe-120">Valid</span></span>|<span data-ttu-id="21efe-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21efe-121">ValidationStates</span></span>|<span data-ttu-id="21efe-122">Le contrôle utilise le <xref:System.Windows.Controls.Validation> classe et le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `false`.</span><span class="sxs-lookup"><span data-stu-id="21efe-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="21efe-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="21efe-123">InvalidFocused</span></span>|<span data-ttu-id="21efe-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21efe-124">ValidationStates</span></span>|<span data-ttu-id="21efe-125">Le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `true` a le contrôle a le focus.</span><span class="sxs-lookup"><span data-stu-id="21efe-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="21efe-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="21efe-126">InvalidUnfocused</span></span>|<span data-ttu-id="21efe-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21efe-127">ValidationStates</span></span>|<span data-ttu-id="21efe-128">Le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriété jointe est `true` a le contrôle n’a pas le focus.</span><span class="sxs-lookup"><span data-stu-id="21efe-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="21efe-129">DocumentViewer ControlTemplate, exemple</span><span class="sxs-lookup"><span data-stu-id="21efe-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="21efe-130">L’exemple suivant montre comment définir un <xref:System.Windows.Controls.ControlTemplate> pour la <xref:System.Windows.Controls.DocumentViewer> contrôle.</span><span class="sxs-lookup"><span data-stu-id="21efe-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="21efe-131">L’exemple précédent utilise une ou plusieurs des ressources suivantes.</span><span class="sxs-lookup"><span data-stu-id="21efe-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="21efe-132">Pour voir l’exemple complet, consultez [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) (Exemple de style avec ControlTemplates).</span><span class="sxs-lookup"><span data-stu-id="21efe-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21efe-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21efe-133">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="21efe-134">Styles et modèles Control</span><span class="sxs-lookup"><span data-stu-id="21efe-134">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="21efe-135">Personnalisation des contrôles</span><span class="sxs-lookup"><span data-stu-id="21efe-135">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="21efe-136">Application d’un style et création de modèles</span><span class="sxs-lookup"><span data-stu-id="21efe-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="21efe-137">Personnalisation de l’apparence d’un contrôle existant en créant un ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="21efe-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)

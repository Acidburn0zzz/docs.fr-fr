---
title: PresentationOptions:Freeze, attribut
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: 896f7b24599b68f178d2a006e5ddc07278564bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546069"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="a4538-102">PresentationOptions:Freeze, attribut</span><span class="sxs-lookup"><span data-stu-id="a4538-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="a4538-103">Définit le <xref:System.Windows.Freezable.IsFrozen%2A> l’état `true` sur le contenant <xref:System.Windows.Freezable> élément.</span><span class="sxs-lookup"><span data-stu-id="a4538-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="a4538-104">Comportement par défaut un <xref:System.Windows.Freezable> sans le `PresentationOptions:Freeze` attribut spécifié est que <xref:System.Windows.Freezable.IsFrozen%2A> est `false` au moment du chargement et général en fonction <xref:System.Windows.Freezable> comportement lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="a4538-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a4538-105">Utilisation d'attributs XAML</span><span class="sxs-lookup"><span data-stu-id="a4538-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a4538-106">Valeurs XAML</span><span class="sxs-lookup"><span data-stu-id="a4538-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="a4538-107">Un préfixe d’espace de noms XML, qui peut être n’importe quelle chaîne de préfixe valide, conformément à la spécification XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="a4538-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="a4538-108">Le préfixe `PresentationOptions` est utilisé à des fins d’identification dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="a4538-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="a4538-109">Un élément qui instancie toute classe dérivée de <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="a4538-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4538-110">Notes</span><span class="sxs-lookup"><span data-stu-id="a4538-110">Remarks</span></span>  
 <span data-ttu-id="a4538-111">Le `Freeze` attribut est le seul attribut ou élément de programmation défini dans le `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` espace de noms XML.</span><span class="sxs-lookup"><span data-stu-id="a4538-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="a4538-112">Le `Freeze` attribut existe dans cet espace de noms spécial spécifiquement afin qu’il peut être désigné comme pouvant être ignoré, à l’aide de [mc : attribut Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) dans le cadre des déclarations d’élément racine.</span><span class="sxs-lookup"><span data-stu-id="a4538-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="a4538-113">La raison qui `Freeze` doit pouvoir être ignoré n’étant donné que tous les [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implémentations de processeur sont en mesure de figer un <xref:System.Windows.Freezable> au moment du chargement ; cette fonctionnalité n’est pas dans le cadre de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] spécification.</span><span class="sxs-lookup"><span data-stu-id="a4538-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="a4538-114">La possibilité de traiter la `Freeze` attribut spécifiquement créé dans le [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processeur traite [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pour les applications compilées.</span><span class="sxs-lookup"><span data-stu-id="a4538-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="a4538-115">L’attribut n’est pas pris en charge par n’importe quelle classe, et la syntaxe d’attribut n’est pas extensible ou modifiable.</span><span class="sxs-lookup"><span data-stu-id="a4538-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="a4538-116">Si vous implémentez votre propre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processeur, vous pouvez choisir du comportement de gel en parallèle la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processeur lors du traitement de la `Freeze` de l’attribut <xref:System.Windows.Freezable> éléments au moment du chargement.</span><span class="sxs-lookup"><span data-stu-id="a4538-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="a4538-117">Toute valeur pour le `Freeze` attribut autre que `true` (non sensible à la casse) génère une erreur de temps de chargement.</span><span class="sxs-lookup"><span data-stu-id="a4538-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="a4538-118">(En spécifiant la `Freeze` sous la forme `false` n’est pas une erreur, mais qui est déjà le paramètre par défaut, par conséquent, pour `false` n’exécute aucune opération).</span><span class="sxs-lookup"><span data-stu-id="a4538-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4538-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4538-119">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="a4538-120">Vue d’ensemble des objets Freezable</span><span class="sxs-lookup"><span data-stu-id="a4538-120">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="a4538-121">mc:Ignorable, attribut</span><span class="sxs-lookup"><span data-stu-id="a4538-121">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)

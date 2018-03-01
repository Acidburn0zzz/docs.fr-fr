---
title: Vue d'ensemble du composant ImageList (Windows Forms)
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
- ImageList
helpviewer_keywords:
- collection controls [Windows Forms], images
- icon list control
- ImageList component [Windows Forms], about ImageList component
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a913de1a6808c7e600a4f28ed58dedf93506466b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="imagelist-component-overview-windows-forms"></a><span data-ttu-id="e0d43-102">Vue d'ensemble du composant ImageList (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e0d43-102">ImageList Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e0d43-103">Le composant Windows Forms <xref:System.Windows.Forms.ImageList> sert à stocker des images, qui peuvent ensuite être affichées par des contrôles.</span><span class="sxs-lookup"><span data-stu-id="e0d43-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is used to store images, which can then be displayed by controls.</span></span> <span data-ttu-id="e0d43-104">Une liste d'images vous permet d'écrire du code pour un catalogue d'images unique et cohérent.</span><span class="sxs-lookup"><span data-stu-id="e0d43-104">An image list allows you to write code for a single, consistent catalog of images.</span></span> <span data-ttu-id="e0d43-105">Par exemple, vous pouvez faire pivoter les images affichées par un contrôle <xref:System.Windows.Forms.Button> simplement en modifiant la propriété <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> ou <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> du bouton.</span><span class="sxs-lookup"><span data-stu-id="e0d43-105">For example, you can rotate images displayed by a <xref:System.Windows.Forms.Button> control simply by changing the button's <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> or <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> property.</span></span> <span data-ttu-id="e0d43-106">Vous pouvez aussi associer la même liste d'images à plusieurs contrôles.</span><span class="sxs-lookup"><span data-stu-id="e0d43-106">You can also associate the same image list with multiple controls.</span></span> <span data-ttu-id="e0d43-107">Par exemple, si vous utilisez à la fois un contrôle <xref:System.Windows.Forms.ListView> et un contrôle <xref:System.Windows.Forms.TreeView> pour afficher la même liste de fichiers, la modification de l'icône d'un fichier dans la liste d'images provoque l'affichage de la nouvelle icône dans les deux vues.</span><span class="sxs-lookup"><span data-stu-id="e0d43-107">For example, if you are using both a <xref:System.Windows.Forms.ListView> control and a <xref:System.Windows.Forms.TreeView> control to display the same list of files, changing a file's icon in the image list will cause the new icon to appear in both views.</span></span>  
  
## <a name="using-imagelist-with-controls"></a><span data-ttu-id="e0d43-108">Utilisation d'ImageList avec des contrôles</span><span class="sxs-lookup"><span data-stu-id="e0d43-108">Using ImageList with Controls</span></span>  
 <span data-ttu-id="e0d43-109">Vous pouvez utiliser une liste d'images avec n'importe quel contrôle ayant une propriété `ImageList` ou, dans le cas du contrôle <xref:System.Windows.Forms.ListView>, les propriétés <xref:System.Windows.Forms.ListView.SmallImageList%2A> et <xref:System.Windows.Forms.ListView.LargeImageList%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0d43-109">You can use an image list with any control that has an `ImageList` property — or in the case of the <xref:System.Windows.Forms.ListView> control, <xref:System.Windows.Forms.ListView.SmallImageList%2A> and <xref:System.Windows.Forms.ListView.LargeImageList%2A> properties.</span></span> <span data-ttu-id="e0d43-110">Les contrôles qui peuvent être associés à une liste d'images sont, entre autres, les contrôles <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> et <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="e0d43-110">The controls that can be associated with an image list include: the <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, and <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="e0d43-111">Pour associer la liste d'images à un contrôle, affectez comme valeur de la propriété `ImageList` du contrôle le nom du composant <xref:System.Windows.Forms.ImageList>.</span><span class="sxs-lookup"><span data-stu-id="e0d43-111">To associate the image list with a control, set the control's `ImageList` property to the name of the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="e0d43-112">Principales propriétés</span><span class="sxs-lookup"><span data-stu-id="e0d43-112">Key Properties</span></span>  
 <span data-ttu-id="e0d43-113">La principale propriété du composant <xref:System.Windows.Forms.ImageList> est <xref:System.Windows.Forms.ImageList.Images%2A>, qui contient les images devant être utilisées par le contrôle associé.</span><span class="sxs-lookup"><span data-stu-id="e0d43-113">The key property of the <xref:System.Windows.Forms.ImageList> component is <xref:System.Windows.Forms.ImageList.Images%2A>, which contains the pictures to be used by the associated control.</span></span> <span data-ttu-id="e0d43-114">Chaque image est accessible par sa valeur d'index ou par sa clé.</span><span class="sxs-lookup"><span data-stu-id="e0d43-114">Each individual image can be accessed by its index value or by its key.</span></span> <span data-ttu-id="e0d43-115">La propriété <xref:System.Windows.Forms.ImageList.ColorDepth%2A> détermine le nombre de couleurs avec lesquelles les images sont affichées.</span><span class="sxs-lookup"><span data-stu-id="e0d43-115">The <xref:System.Windows.Forms.ImageList.ColorDepth%2A> property determines the number of colors that the images are rendered with.</span></span> <span data-ttu-id="e0d43-116">Les images sont toutes affichées à la même taille, définie par la propriété <xref:System.Windows.Forms.ImageList.ImageSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0d43-116">The images will all be displayed at the same size, set by the <xref:System.Windows.Forms.ImageList.ImageSize%2A> property.</span></span> <span data-ttu-id="e0d43-117">Les images plus grandes seront ajustées.</span><span class="sxs-lookup"><span data-stu-id="e0d43-117">Images that are larger will be scaled to fit.</span></span>  
  
 <span data-ttu-id="e0d43-118">Si vous utilisez [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], vous avez accès à une grande bibliothèque d'images standard utilisables dans votre application.</span><span class="sxs-lookup"><span data-stu-id="e0d43-118">If you are using [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you have access to a large library of standard images that you can use in your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d43-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0d43-119">See Also</span></span>  
 <xref:System.Windows.Forms.ImageList>  
 [<span data-ttu-id="e0d43-120">Guide pratique pour ajouter ou supprimer des images avec le composant ImageList Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0d43-120">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)

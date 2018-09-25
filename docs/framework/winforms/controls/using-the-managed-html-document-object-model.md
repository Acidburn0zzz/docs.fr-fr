---
title: Utilisation du modèle objet de document HTML managé
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: 7800311895d1c0fac43577076226a68712164f60
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081758"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="6f85b-102">Utilisation du modèle objet de document HTML managé</span><span class="sxs-lookup"><span data-stu-id="6f85b-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="6f85b-103">Le modèle d’objet de document (DOM) HTML managé fournit un wrapper basé sur le [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] pour les classes HTML exposées par Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6f85b-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="6f85b-104">Utilisez ces classes pour manipuler des pages HTML hébergées dans le <xref:System.Windows.Forms.WebBrowser> contrôle, ou pour créer de nouvelles pages à partir du début.</span><span class="sxs-lookup"><span data-stu-id="6f85b-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f85b-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6f85b-105">In This Section</span></span>  
 [<span data-ttu-id="6f85b-106">Guide pratique pour accéder au modèle DOM (Document Object Model) HTML managé</span><span class="sxs-lookup"><span data-stu-id="6f85b-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="6f85b-107">Décrit comment obtenir une instance valide de <xref:System.Windows.Forms.HtmlDocument> à partir d’une application Windows Forms ou une <xref:System.Windows.Forms.UserControl> hébergée dans Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6f85b-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="6f85b-108">Guide pratique pour accéder à la source HTML dans le modèle objet de document HTML managé</span><span class="sxs-lookup"><span data-stu-id="6f85b-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="6f85b-109">Décrit comment obtenir la source HTML d’origine, non modifiée et comment obtenir la source « live » qui reflète l’état actuel du DOM.</span><span class="sxs-lookup"><span data-stu-id="6f85b-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="6f85b-110">Guide pratique pour modifier des styles d'un élément dans le modèle objet de document HTML managé</span><span class="sxs-lookup"><span data-stu-id="6f85b-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="6f85b-111">Décrit comment manipuler les styles, qui sont utilisés pour contrôler l’affichage d’éléments.</span><span class="sxs-lookup"><span data-stu-id="6f85b-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="6f85b-112">Accès aux frames dans le modèle objet de document HTML managé</span><span class="sxs-lookup"><span data-stu-id="6f85b-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="6f85b-113">Décrit les cadres et des jeux de frames et indique comment accéder au DOM d’un frame.</span><span class="sxs-lookup"><span data-stu-id="6f85b-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="6f85b-114">Accès aux membres non exposés sur le modèle objet de document HTML managé</span><span class="sxs-lookup"><span data-stu-id="6f85b-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="6f85b-115">Décrit comment accéder aux membres du modèle DOM sous-jacent qui n’ont pas un équivalent managé.</span><span class="sxs-lookup"><span data-stu-id="6f85b-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6f85b-116">Référence</span><span class="sxs-lookup"><span data-stu-id="6f85b-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="6f85b-117">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6f85b-117">Related Sections</span></span>  
 [<span data-ttu-id="6f85b-118">WebBrowser, contrôle</span><span class="sxs-lookup"><span data-stu-id="6f85b-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f85b-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f85b-119">See Also</span></span>  
 [<span data-ttu-id="6f85b-120">Sur le modèle d’objet DHTML</span><span class="sxs-lookup"><span data-stu-id="6f85b-120">About the DHTML Object Model</span></span>](https://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)

---
title: 'Procédure : Créer un bouton comportant une image'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: cfebe53047531ecddde42a3a0596dfd949629ecd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682060"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="19d6d-102">Procédure : Créer un bouton comportant une image</span><span class="sxs-lookup"><span data-stu-id="19d6d-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="19d6d-103">Cet exemple montre comment inclure une image sur un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="19d6d-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19d6d-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="19d6d-104">Example</span></span>  
 <span data-ttu-id="19d6d-105">L’exemple suivant crée deux <xref:System.Windows.Controls.Button> contrôles.</span><span class="sxs-lookup"><span data-stu-id="19d6d-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="19d6d-106">Un <xref:System.Windows.Controls.Button> contient du texte et l’autre contient une image.</span><span class="sxs-lookup"><span data-stu-id="19d6d-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="19d6d-107">L’image est dans un dossier appelé données, qui sont un sous-dossier du dossier du projet de l’exemple.</span><span class="sxs-lookup"><span data-stu-id="19d6d-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="19d6d-108">Lorsqu’un utilisateur clique sur le <xref:System.Windows.Controls.Button> qui a l’image, l’arrière-plan et le texte de l’autre <xref:System.Windows.Controls.Button> modifier.</span><span class="sxs-lookup"><span data-stu-id="19d6d-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="19d6d-109">Cet exemple crée <xref:System.Windows.Controls.Button> contrôle à l’aide du balisage, mais utilise le code pour écrire la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestionnaires d’événements.</span><span class="sxs-lookup"><span data-stu-id="19d6d-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="19d6d-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19d6d-110">See also</span></span>
- [<span data-ttu-id="19d6d-111">Contrôles</span><span class="sxs-lookup"><span data-stu-id="19d6d-111">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)
- [<span data-ttu-id="19d6d-112">Bibliothèque de contrôles</span><span class="sxs-lookup"><span data-stu-id="19d6d-112">Control Library</span></span>](../../../../docs/framework/wpf/controls/control-library.md)

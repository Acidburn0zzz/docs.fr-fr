---
title: "Comment : configurer les marges de sélection et d'image de MenuStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: d85df6eb053105a00f3a8a936d0239f68b7030df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530353"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="2dbaa-102">Comment : configurer les marges de sélection et d'image de MenuStrip</span><span class="sxs-lookup"><span data-stu-id="2dbaa-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="2dbaa-103">Vous pouvez personnaliser un <xref:System.Windows.Forms.MenuStrip> en définissant les propriétés <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> et <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> dans différentes combinaisons.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2dbaa-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="2dbaa-104">Example</span></span>  
 <span data-ttu-id="2dbaa-105">L'exemple de code suivant montre comment définir et personnaliser les marges d'image et de sélection de <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="2dbaa-106">La procédure est identique pour <xref:System.Windows.Forms.ContextMenuStrip> et <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2dbaa-107">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="2dbaa-107">Compiling the Code</span></span>  
 <span data-ttu-id="2dbaa-108">Cet exemple nécessite :</span><span class="sxs-lookup"><span data-stu-id="2dbaa-108">This example requires:</span></span>  
  
-   <span data-ttu-id="2dbaa-109">des références aux assemblys System, System.Drawing et System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="2dbaa-110">Pour plus d’informations sur la création de cet exemple à partir de la ligne de commande pour Visual Basic ou Visual c#, consultez [génération à partir de la ligne de commande](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [de ligne de commande avec csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2dbaa-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2dbaa-111">Vous pouvez également générer cet exemple dans Visual Studio en collant le code dans un nouveau projet.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="2dbaa-112">Consultez également la page [Comment : compiler et exécuter un exemple complet de code Windows Forms à l’aide de Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2dbaa-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dbaa-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2dbaa-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [<span data-ttu-id="2dbaa-114">Contrôle ToolStrip</span><span class="sxs-lookup"><span data-stu-id="2dbaa-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="2dbaa-115">Comment : activer les marges de sélection et d’image dans les contrôles ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="2dbaa-115">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)

---
title: 'Comment : énumérer les polices installées'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 9f31880cbfb42c03122fc7d2730b9ca89db49226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524437"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="9e6fe-102">Comment : énumérer les polices installées</span><span class="sxs-lookup"><span data-stu-id="9e6fe-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="9e6fe-103">Le <xref:System.Drawing.Text.InstalledFontCollection> classe hérite de la <xref:System.Drawing.Text.FontCollection> classe de base abstraite.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="9e6fe-104">Vous pouvez utiliser un <xref:System.Drawing.Text.InstalledFontCollection> objet à énumérer les polices installées sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="9e6fe-105">Le <xref:System.Drawing.Text.FontCollection.Families%2A> propriété d’un <xref:System.Drawing.Text.InstalledFontCollection> objet est un tableau de <xref:System.Drawing.FontFamily> objets.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e6fe-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="9e6fe-106">Example</span></span>  
 <span data-ttu-id="9e6fe-107">L’exemple suivant répertorie les noms de toutes les familles de polices installées sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="9e6fe-108">Le code récupère le <xref:System.Drawing.FontFamily.Name%2A> propriété de chaque <xref:System.Drawing.FontFamily> objet dans le tableau retourné par la <xref:System.Drawing.Text.FontCollection.Families%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="9e6fe-109">Comme les noms de famille sont récupérés, ils sont concaténés pour former une virgule liste.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="9e6fe-110">Le <xref:System.Drawing.Graphics.DrawString%2A> méthode de la <xref:System.Drawing.Graphics> classe dessine la liste séparée par des virgules dans un rectangle.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="9e6fe-111">Si vous exécutez l’exemple de code, le résultat sera similaire à celui indiqué dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-111">If you run the example code, the output will be similar to that shown in the following illustration.</span></span>  
  
 <span data-ttu-id="9e6fe-112">![Polices installées](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span><span class="sxs-lookup"><span data-stu-id="9e6fe-112">![Installed Fonts](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e6fe-113">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="9e6fe-113">Compiling the Code</span></span>  
 <span data-ttu-id="9e6fe-114">L'exemple précédent est conçu pour une utilisation avec Windows Forms et nécessite <xref:System.Windows.Forms.PaintEventArgs> `e`, qui est un paramètre de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="9e6fe-115">En outre, vous devez importer le <xref:System.Drawing.Text> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="9e6fe-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6fe-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e6fe-116">See Also</span></span>  
 [<span data-ttu-id="9e6fe-117">Utilisation de polices et de texte</span><span class="sxs-lookup"><span data-stu-id="9e6fe-117">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)

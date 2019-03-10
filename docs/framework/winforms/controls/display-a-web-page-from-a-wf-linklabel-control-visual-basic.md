---
title: 'Procédure : Afficher une Page Web à partir d’un contrôle de LinkLabel Windows Forms (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 7e80dba9cd43385be016506ac2a7e887a68dedf2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705227"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a><span data-ttu-id="bf3ef-102">Procédure : Afficher une Page Web à partir d’un contrôle de LinkLabel Windows Forms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf3ef-102">How to: Display a Web Page from a Windows Forms LinkLabel Control (Visual Basic)</span></span>
<span data-ttu-id="bf3ef-103">Cet exemple affiche une page Web dans le navigateur par défaut lorsqu’un utilisateur clique sur un formulaire Windows <xref:System.Windows.Forms.LinkLabel> contrôle.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-103">This example displays a Web page in the default browser when a user clicks a Windows Forms <xref:System.Windows.Forms.LinkLabel> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf3ef-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="bf3ef-104">Example</span></span>  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bf3ef-105">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="bf3ef-105">Compiling the Code</span></span>  
 <span data-ttu-id="bf3ef-106">Cet exemple nécessite :</span><span class="sxs-lookup"><span data-stu-id="bf3ef-106">This example requires:</span></span>  
  
-   <span data-ttu-id="bf3ef-107">Un formulaire Windows nommé `Form1`.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-107">A Windows Form named `Form1`.</span></span>  
  
-   <span data-ttu-id="bf3ef-108">un contrôle <xref:System.Windows.Forms.LinkLabel> nommé `LinkLabel1` ;</span><span class="sxs-lookup"><span data-stu-id="bf3ef-108">A <xref:System.Windows.Forms.LinkLabel> control named `LinkLabel1`.</span></span>  
  
-   <span data-ttu-id="bf3ef-109">Une connexion Internet active.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-109">An active Internet connection.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bf3ef-110">Sécurité .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bf3ef-110">.NET Framework Security</span></span>  
 <span data-ttu-id="bf3ef-111">L’appel à la <xref:System.Diagnostics.Process.Start%2A> méthode requiert une confiance totale.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-111">The call to the <xref:System.Diagnostics.Process.Start%2A> method requires full trust.</span></span> <span data-ttu-id="bf3ef-112">Pour plus d'informations, consultez <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-112">For more information, see <xref:System.Security.SecurityException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3ef-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf3ef-113">See also</span></span>
- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="bf3ef-114">LinkLabel, contrôle</span><span class="sxs-lookup"><span data-stu-id="bf3ef-114">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)

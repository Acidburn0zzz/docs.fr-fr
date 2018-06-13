---
title: 'Comment : implémenter le mode virtuel avec le chargement de données juste-à-temps dans le contrôle DataGridView Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: 9e70596e212a51bc464c51f162aa1aff5e3aa0dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537250"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="75992-102">Comment : implémenter le mode virtuel avec le chargement de données juste-à-temps dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75992-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="75992-103">L'exemple de code suivant montre comment utiliser le mode virtuel dans le contrôle <xref:System.Windows.Forms.DataGridView> avec un cache de données qui charge des données à partir d'un serveur uniquement en cas de nécessité.</span><span class="sxs-lookup"><span data-stu-id="75992-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="75992-104">Cet exemple est décrit en détail dans [implémentation du Mode virtuel avec le chargement de données juste à temps dans le contrôle DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="75992-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75992-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="75992-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="75992-106">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="75992-106">Compiling the Code</span></span>  
 <span data-ttu-id="75992-107">Cet exemple nécessite :</span><span class="sxs-lookup"><span data-stu-id="75992-107">This example requires:</span></span>  
  
-   <span data-ttu-id="75992-108">des références aux assemblys System.Data, System.Xml et System.Windows.Forms ;</span><span class="sxs-lookup"><span data-stu-id="75992-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="75992-109">l'accès à un serveur sur lequel est installé l'exemple de base de données SQL Server Northwind.</span><span class="sxs-lookup"><span data-stu-id="75992-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
 <span data-ttu-id="75992-110">Pour plus d’informations sur la création de cet exemple à partir de la ligne de commande pour Visual Basic ou Visual c#, consultez [génération à partir de la ligne de commande](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [de ligne de commande avec csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="75992-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="75992-111">Vous pouvez également générer cet exemple dans Visual Studio en collant le code dans un nouveau projet.</span><span class="sxs-lookup"><span data-stu-id="75992-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="75992-112">Consultez également la page [Comment : compiler et exécuter un exemple complet de code Windows Forms à l’aide de Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="75992-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="75992-113">Sécurité .NET Framework</span><span class="sxs-lookup"><span data-stu-id="75992-113">.NET Framework Security</span></span>  
 <span data-ttu-id="75992-114">Le stockage d'informations sensibles (telles qu'un mot de passe) dans la chaîne de connexion peut affecter la sécurité de votre application.</span><span class="sxs-lookup"><span data-stu-id="75992-114">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="75992-115">L'utilisation de l'authentification Windows (également appelée sécurité intégrée) offre un moyen plus sûr de contrôler l'accès à une base de données.</span><span class="sxs-lookup"><span data-stu-id="75992-115">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="75992-116">Pour plus d’informations, consultez [Protection des informations de connexion](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="75992-116">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75992-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75992-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 [<span data-ttu-id="75992-118">Implémentation du mode virtuel avec le chargement immédiat des données dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75992-118">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [<span data-ttu-id="75992-119">Réglage des performances dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75992-119">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="75992-120">Mode virtuel dans le contrôle DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="75992-120">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)

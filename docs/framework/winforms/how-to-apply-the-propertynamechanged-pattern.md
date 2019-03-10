---
title: 'Procédure : Appliquer le modèle PropertyNameChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 889a7f5f7a84db378acaa88b717b6011f1a3dfdc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703476"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="e1b9c-102">Procédure : Appliquer le modèle PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="e1b9c-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="e1b9c-103">L’exemple de code suivant montre comment appliquer le *PropertyName*modèle a été modifié pour un contrôle personnalisé.</span><span class="sxs-lookup"><span data-stu-id="e1b9c-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="e1b9c-104">Appliquer ce modèle lorsque vous implémentez des contrôles personnalisés qui sont utilisés avec le moteur de liaison de données Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e1b9c-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1b9c-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="e1b9c-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1b9c-106">Compilation du code</span><span class="sxs-lookup"><span data-stu-id="e1b9c-106">Compiling the Code</span></span>  
 <span data-ttu-id="e1b9c-107">Pour compiler l’exemple de code précédent :</span><span class="sxs-lookup"><span data-stu-id="e1b9c-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="e1b9c-108">Collez le code dans un fichier de code vide.</span><span class="sxs-lookup"><span data-stu-id="e1b9c-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="e1b9c-109">Vous devez utiliser le contrôle personnalisé dans un formulaire Windows qui contient un `Main` (méthode).</span><span class="sxs-lookup"><span data-stu-id="e1b9c-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b9c-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e1b9c-110">See also</span></span>
- [<span data-ttu-id="e1b9c-111">Guide pratique pour Implémenter l’Interface INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="e1b9c-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="e1b9c-112">Notification de modifications dans la liaison de données Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e1b9c-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="e1b9c-113">Liaison de données Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e1b9c-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)

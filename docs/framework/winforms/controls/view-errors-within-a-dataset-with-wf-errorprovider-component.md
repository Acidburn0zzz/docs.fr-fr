---
title: "Comment : afficher des erreurs d'un groupe de données à l'aide du composant ErrorProvider Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: f00d874f2a4afcea3498a64fe946a93c83eb7b9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537084"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="80e60-102">Comment : afficher des erreurs d'un groupe de données à l'aide du composant ErrorProvider Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80e60-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="80e60-103">Vous pouvez utiliser Windows Forms <xref:System.Windows.Forms.ErrorProvider> composant pour afficher les erreurs de colonne dans un jeu de données ou une autre source de données.</span><span class="sxs-lookup"><span data-stu-id="80e60-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="80e60-104">Pour un <xref:System.Windows.Forms.ErrorProvider> composant pour afficher les erreurs de données sur un formulaire, il n’a pas à être directement associée à un contrôle.</span><span class="sxs-lookup"><span data-stu-id="80e60-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="80e60-105">Une fois qu’il est lié à une source de données, il peut afficher une icône d’erreur en regard de n’importe quel contrôle est lié à la même source de données.</span><span class="sxs-lookup"><span data-stu-id="80e60-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80e60-106">Si vous modifiez le fournisseur d’erreurs <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> et <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> propriétés au moment de l’exécution, vous devez utiliser le <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> méthode pour éviter les conflits.</span><span class="sxs-lookup"><span data-stu-id="80e60-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="80e60-107">Pour afficher les erreurs de données</span><span class="sxs-lookup"><span data-stu-id="80e60-107">To display data errors</span></span>  
  
1.  <span data-ttu-id="80e60-108">Lier le composant à une colonne spécifique dans une table de données.</span><span class="sxs-lookup"><span data-stu-id="80e60-108">Bind the component to a specific column within a data table.</span></span>  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  <span data-ttu-id="80e60-109">Définir le <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propriété au formulaire.</span><span class="sxs-lookup"><span data-stu-id="80e60-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  <span data-ttu-id="80e60-110">Définir la position de l’enregistrement actif à une ligne qui contient une erreur de colonne.</span><span class="sxs-lookup"><span data-stu-id="80e60-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="80e60-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80e60-111">See Also</span></span>  
 [<span data-ttu-id="80e60-112">Vue d’ensemble du composant ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="80e60-112">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="80e60-113">Guide pratique pour afficher des icônes d’erreur pour la validation de formulaire à l’aide du composant ErrorProvider Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80e60-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)

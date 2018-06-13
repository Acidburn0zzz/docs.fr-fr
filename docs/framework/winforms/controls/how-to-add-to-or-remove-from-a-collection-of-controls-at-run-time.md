---
title: 'Comment : ajouter des contrôles dans une collection au moment de l’exécution, ou comment les supprimer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: cd903558fdb0e01b5ba55e0007fc78315408fa13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525994"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="cb25f-102">Comment : ajouter des contrôles dans une collection au moment de l’exécution, ou comment les supprimer</span><span class="sxs-lookup"><span data-stu-id="cb25f-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="cb25f-103">Tâches courantes dans le développement d’applications sont Ajout de contrôles à et suppression de contrôles à partir de n’importe quel contrôle conteneur sur vos formulaires (tels que les <xref:System.Windows.Forms.Panel> ou <xref:System.Windows.Forms.GroupBox> contrôle, ou même le formulaire lui-même).</span><span class="sxs-lookup"><span data-stu-id="cb25f-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="cb25f-104">Au moment de la conception, vous pouvez faire glisser les contrôles directement vers un panneau ou une zone de groupe.</span><span class="sxs-lookup"><span data-stu-id="cb25f-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="cb25f-105">Au moment de l’exécution, ces contrôles gèrent une collection `Controls`, qui assure le suivi des contrôles qui y sont placés.</span><span class="sxs-lookup"><span data-stu-id="cb25f-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb25f-106">L’exemple de code suivant s’applique à n’importe quel contrôle qui gère une collection de contrôles qu’il contient.</span><span class="sxs-lookup"><span data-stu-id="cb25f-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="cb25f-107">Pour ajouter un contrôle à une collection par programme</span><span class="sxs-lookup"><span data-stu-id="cb25f-107">To add a control to a collection programmatically</span></span>  
  
1.  <span data-ttu-id="cb25f-108">Créez une instance du contrôle à ajouter.</span><span class="sxs-lookup"><span data-stu-id="cb25f-108">Create an instance of the control to be added.</span></span>  
  
2.  <span data-ttu-id="cb25f-109">Définissez les propriétés du nouveau contrôle.</span><span class="sxs-lookup"><span data-stu-id="cb25f-109">Set properties of the new control.</span></span>  
  
3.  <span data-ttu-id="cb25f-110">Ajoutez le contrôle à la collection `Controls` du contrôle parent.</span><span class="sxs-lookup"><span data-stu-id="cb25f-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="cb25f-111">L’exemple de code suivant montre comment créer une instance de la <xref:System.Windows.Forms.Button> contrôle.</span><span class="sxs-lookup"><span data-stu-id="cb25f-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="cb25f-112">Il nécessite un formulaire avec un <xref:System.Windows.Forms.Panel> contrôle et que la méthode de gestion d’événements pour le bouton en cours de création, `NewPanelButton_Click`, existe déjà.</span><span class="sxs-lookup"><span data-stu-id="cb25f-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="cb25f-113">Pour supprimer des contrôles d’une collection par programme</span><span class="sxs-lookup"><span data-stu-id="cb25f-113">To remove controls from a collection programmatically</span></span>  
  
1.  <span data-ttu-id="cb25f-114">Supprimez le gestionnaire d’événements de l’événement.</span><span class="sxs-lookup"><span data-stu-id="cb25f-114">Remove the event handler from the event.</span></span> <span data-ttu-id="cb25f-115">En Visual Basic, utilisez la [RemoveHandler, instruction](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) (mot clé) ; dans Visual c#, utilisez le [-=, opérateur (référence c#)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="cb25f-115">In Visual Basic, use the [RemoveHandler Statement](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) keyword; in Visual C#, use the [-= Operator (C# Reference)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span></span>  
  
2.  <span data-ttu-id="cb25f-116">Utilisez la méthode `Remove` pour supprimer le contrôle souhaité dans la collection `Controls` du panneau.</span><span class="sxs-lookup"><span data-stu-id="cb25f-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3.  <span data-ttu-id="cb25f-117">Appelez le <xref:System.Windows.Forms.Control.Dispose%2A> méthode pour libérer toutes les ressources utilisées par le contrôle.</span><span class="sxs-lookup"><span data-stu-id="cb25f-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cb25f-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb25f-118">See Also</span></span>  
 <xref:System.Windows.Forms.Panel>  
 [<span data-ttu-id="cb25f-119">Panel, contrôle</span><span class="sxs-lookup"><span data-stu-id="cb25f-119">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)

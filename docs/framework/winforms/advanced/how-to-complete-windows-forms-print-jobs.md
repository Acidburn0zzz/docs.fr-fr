---
title: "Comment : terminer des travaux d'impression Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 74a8e3721df72415437dd0c39b3298d67c19990b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521587"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Comment : terminer des travaux d'impression Windows Forms
Fréquemment, les traitements de texte et d’autres applications qui impliquent l’impression offrent la possibilité d’afficher un message aux utilisateurs qu’un travail d’impression est terminé. Vous pouvez fournir cette fonctionnalité dans vos Windows Forms en gérant la <xref:System.Drawing.Printing.PrintDocument.EndPrint> l’événement de la <xref:System.Drawing.Printing.PrintDocument> composant.  
  
 La procédure suivante requiert que vous avez créé une application Windows avec une <xref:System.Drawing.Printing.PrintDocument> composant, qui est le moyen standard de l’activation de l’impression à partir d’une application Windows. Pour plus d’informations sur l’impression à partir de Windows Forms à l’aide du <xref:System.Drawing.Printing.PrintDocument> composant, consultez [Comment : créer de travaux d’impression Windows Forms Standard](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Pour effectuer un travail d’impression  
  
1.  Définir le <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> propriété de la <xref:System.Drawing.Printing.PrintDocument> composant.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Écrivez du code pour gérer l’événement <xref:System.Drawing.Printing.PrintDocument.EndPrint>.  
  
     Dans l’exemple de code suivant, une boîte de message s’affiche, indiquant que le document a terminé l’impression.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     (Visual c# et [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) placez le code suivant dans le constructeur du formulaire pour inscrire le Gestionnaire d’événements.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Prise en charge de l’impression dans les Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)

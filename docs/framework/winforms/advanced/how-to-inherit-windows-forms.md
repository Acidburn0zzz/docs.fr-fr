---
title: 'Comment : hériter des Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 275ae52a36ed9766e2569bd6c8ecdea78ea56e0b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43537144"
---
# <a name="how-to-inherit-windows-forms"></a>Comment : hériter des Windows Forms
Créer des Windows Forms en héritant de formulaires de base est un moyen pratique de dupliquer vos efforts sans avoir à recréer entièrement un formulaire chaque fois que vous en avez besoin.  
  
 Pour plus d’informations sur l’héritage des formulaires au moment du design à l’aide de la boîte de dialogue **Sélecteur d’héritage** et sur la façon d’effectuer une distinction visuelle entre les niveaux de sécurité des contrôles hérités, consultez [Comment : hériter de formulaires à l’aide de la boîte de dialogue Sélecteur d’héritage](../../../../docs/framework/winforms/advanced/how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).  
  
 **Remarque** Pour hériter d’un formulaire, le fichier ou l’espace de noms contenant ce formulaire doit avoir été intégré dans un fichier exécutable ou une DLL. Pour générer le projet, choisissez **Générer** dans le menu **Générer**. De plus, une référence à l'espace de noms doit être ajoutée à la classe héritant du formulaire. Les boîtes de dialogue et les commandes de menu qui s'affichent peuvent être différentes de celles qui sont décrites dans l'aide, en fonction de vos paramètres actifs ou de l'édition utilisée. Pour modifier vos paramètres, choisissez **Importation et exportation de paramètres** dans le menu **Outils** . Pour plus d’informations, consultez [Personnaliser l’IDE Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-inherit-a-form-programmatically"></a>Pour hériter d'un formulaire par programmation  
  
1.  Dans votre classe, ajoutez une référence à l'espace de noms contenant le formulaire dont vous voulez hériter.  
  
2.  Dans la définition de classe, ajoutez une référence au formulaire à partir duquel hériter. Cette référence doit inclure l'espace de noms qui contient le formulaire, suivi d'un point, puis du nom du formulaire de base proprement dit.  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 Lors de l'héritage de formulaires, n'oubliez pas que des problèmes peuvent survenir car les gestionnaires d'événements peuvent être appelés deux fois (chaque événement étant géré par la classe de base et par la classe héritée). Pour plus d’informations sur la façon d’éviter ce problème, consultez [Dépannage des gestionnaires d’événements hérités dans Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Inherits (instruction)](~/docs/visual-basic/language-reference/statements/inherits-statement.md)  
 [Imports (instruction) (espace de noms et type .NET)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [using](~/docs/csharp/language-reference/keywords/using.md)  
 [Conséquences de la modification de l’aspect d’un formulaire de base](../../../../docs/framework/winforms/advanced/effects-of-modifying-base-form-appearance.md)  
 [Héritage visuel des Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)

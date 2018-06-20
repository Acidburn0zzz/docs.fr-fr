---
title: Polices internationales dans les Windows Forms et contrôles
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: b2738f174c9837a2ba83c1306f4617f39ce17de1
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208569"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Polices internationales dans les Windows Forms et contrôles

Dans les applications internationales, la méthode de sélection des polices recommandée est d’utiliser la police de substitution autant que possible. Police de substitution signifie que le système détermine le script le caractère appartient.

## <a name="using-font-fallback"></a>À l’aide de la police de substitution

Pour tirer parti de cette fonctionnalité, ne définissez pas le <xref:System.Drawing.Font> propriété pour votre formulaire ou tout autre élément. L’application utilisera automatiquement la police système par défaut, ce qui diffère d’une langue localisée du système d’exploitation vers un autre. Lorsque l’application s’exécute, le système fournit automatiquement la police correcte pour la culture sélectionnée dans le système d’exploitation.

Il existe une exception à la règle de ne pas définir la police, permettant de changer le style de police. Cela peut être important pour une application dans laquelle l’utilisateur clique sur un bouton pour afficher le texte dans une zone de texte en gras. Pour ce faire, vous écririez une fonction pour modifier le style de police de la zone de texte à afficher en gras, en fonction de quelle que soit la police du formulaire. Il est important d’appeler cette fonction à deux emplacements : dans du bouton <xref:System.Windows.Forms.Control.Click> Gestionnaire d’événements et dans le <xref:System.Windows.Forms.Control.FontChanged> Gestionnaire d’événements. Si la fonction est appelée uniquement dans le <xref:System.Windows.Forms.Control.Click> Gestionnaire d’événements et un autre fragment de code modifie la famille de polices de l’intégralité du formulaire, la zone de texte ne change pas avec le reste du formulaire.

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

Toutefois, lorsque vous localisez votre application, la police en gras peut afficher mal pour certaines langues. S’il s’agit d’un problème, vous souhaitez que les localisateurs doivent avoir la possibilité de basculer la police de gras au texte normal. Étant donné que les localisateurs ne sont généralement pas les développeurs et n’ont pas accès au code source, uniquement aux fichiers de ressources, cette option doit être définie dans les fichiers de ressources. Pour ce faire, vous devez définir le <xref:System.Drawing.Font.Bold%2A> propriété `true`. Ainsi, le paramètre de police qui est écrit dans les fichiers de ressources, où les localisateurs peuvent modifier. Vous écrivez ensuite du code après le `InitializeComponent` méthode pour rétablir la police quelle que soit la police du formulaire est, en utilisant le style de police spécifié dans le fichier de ressources.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>Voir aussi

[Globalisation des applications Windows Forms](globalizing-windows-forms.md)  
[Utilisation de polices et de texte](using-fonts-and-text.md)
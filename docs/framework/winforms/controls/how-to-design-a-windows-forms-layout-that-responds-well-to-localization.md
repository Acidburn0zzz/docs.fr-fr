---
title: 'Comment : créer une présentation Windows Forms qui répond bien à la localisation'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7f35a61c4ef8bbda544e36939fe4986a1017fe31
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Comment : créer une présentation Windows Forms qui répond bien à la localisation
La création de formulaires qui sont prêts à être localisés accélère considérablement le développement pour les marchés internationaux. Vous pouvez utiliser le contrôle <xref:System.Windows.Forms.TableLayoutPanel> pour implémenter des dispositions qui répondent correctement au redimensionnement des contrôles suite aux modifications de leurs valeurs de propriétés <xref:System.Windows.Forms.Control.Text%2A>.  
  
## <a name="example"></a>Exemple  
 Ce formulaire montre comment créer une disposition qui s'ajuste proportionnellement quand vous traduisez les valeurs de chaînes affichées dans d'autres langues. Ce processus de traduction est appelé *localisation*. Pour plus d’informations, consultez [Localisation](../../../../docs/standard/globalization-localization/localization.md).  
  
 Cette tâche est très bien prise en charge dans Visual Studio.  Consultez également [Procédure pas à pas : création d’une présentation qui ajuste la proportion pour la localisation](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [Comment : aligner et étirer un contrôle dans un contrôle TableLayoutPanel](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))  
  
2.  [Procédure pas à pas : organisation des contrôles dans les Windows Forms à l’aide d’un FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))  
  
3.  [Comment : étendre des lignes et des colonnes dans un contrôle TableLayoutPanel](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))  
  
4.  [Comment : modifier des colonnes et des lignes dans un contrôle TableLayoutPanel](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))  
  
5.  [Procédure pas à pas : exécution de tâches courantes à l’aide de balises actives dans les contrôles Windows Forms](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))  
  
6.  [Procédure pas à pas : organisation des contrôles dans les Windows Forms à l’aide d’un TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
7.  [Procédure pas à pas : disposition des contrôles Windows Forms avec les propriétés Padding, Margins et AutoSize](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))  
  
8.  [Comment : prendre en charge la localisation dans les Windows Forms à l’aide du redimensionnement automatique et du contrôle TableLayoutPanel](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))  
  
9. [Procédure pas à pas : création d’un Windows Form redimensionnable pour l’entrée de données](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Cet exemple nécessite :  
  
-   Références aux assemblys System, System.Data, System.Drawing et System.Windows.Forms.  
  
 Pour plus d’informations sur la création de cet exemple à partir de la ligne de commande pour Visual Basic ou Visual c#, consultez [génération à partir de la ligne de commande](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) ou [de ligne de commande avec csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Vous pouvez également générer cet exemple dans Visual Studio en collant le code dans un nouveau projet.  Consultez également la page [Comment : compiler et exécuter un exemple complet de code Windows Forms à l’aide de Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [Localisation](../../../../docs/standard/globalization-localization/localization.md)

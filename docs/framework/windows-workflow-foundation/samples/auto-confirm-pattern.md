---
title: Modèle de confirmation automatique
ms.date: 03/30/2017
ms.assetid: 668aec65-78d3-4636-9c7b-deed643a18f9
ms.openlocfilehash: b30703ffba3b721ac544ea6471ec47ce7f746d2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="auto-confirm-pattern"></a>Modèle de confirmation automatique
Cet exemple est composé de trois scénarios qui s'exécutent pour illustrer une activité `AutoConfirmScope` personnalisée. Le premier exemple présente l'exécution réussie d'une séquence de quatre activités compensables où la deuxième et la troisième sont imbriqués dans un `AutoConfirmScope`. Le deuxième exemple présente la même séquence avec une exception qui se produit après l'exécution du quatrième <xref:System.Activities.Statements.CompensableActivity>. Le troisième scénario présente la même séquence avec une exception qui se produit dans `AutoConfirmScope` une fois le deuxième <xref:System.Activities.Statements.CompensableActivity> terminé.  
  
 L'exemple illustre le modèle de confirmation automatique où toutes les activités compensables enfants sont confirmées une fois l'étendue terminée avec succès. Ce modèle définit la durée de vie de toutes les activités compensables enfants, lorsqu'elles ne peuvent plus être compensées ou confirmées.  
  
 L'étendue est composée d'un <xref:System.Activities.Statements.TryCatch> où <xref:System.Activities.Statements.TryCatch.Try%2A> est un <xref:System.Activities.Statements.CompensableActivity> interne. Le corps spécifié par l'utilisateur d'`AutoConfirmScope` est le corps du <xref:System.Activities.Statements.CompensableActivity> interne. Lorsque ce <xref:System.Activities.Statements.CompensableActivity> interne se termine, il produit un <xref:System.Activities.Statements.CompensationToken> comme argument de sortie. `AutoConfirmScope` utilise un <xref:System.Activities.Statements.TryCatch.Finally%2A> pour vérifier si le jeton a été produit, et si tel est le cas, il confirme ensuite le <xref:System.Activities.Statements.CompensableActivity> interne. Le <xref:System.Activities.Statements.CompensableActivity> interne appelle la compensation par défaut pour toutes les activités compensables qui peuvent exister dans son corps.  
  
 Le premier scénario illustre l'exécution réussie du workflow. Il montre que la deuxième et la troisième activités compensables sont déjà confirmées lorsque le workflow se termine et que la première et la quatrième sont confirmées. Cela produit un ordre de confirmation de trois, deux, quatre et un.  
  
 Le deuxième scénario présente une exception une fois les quatre activités compensables terminées. Étant donné que la deuxième et la troisième activités compensables sont déjà confirmées, elles ne sont pas affectées, mais les activités une et quatre sont compensées. Cela produit la confirmation de la troisième activité, la confirmation de la deuxième activité, la compensation de la quatrième activité et la compensation de la première activité.  
  
 Le dernier scénario présente l'échec de l'exécution de `AutoConfirmScope`. Dans ce scénario, une exception se produit une fois le deuxième <xref:System.Activities.Statements.CompensableActivity> terminé. Étant donné que la troisième et la quatrième activités compensables ne se sont pas exécutées, elles ne sont pas affectées. Étant donné que l'étendue ne s'est pas terminée avec succès, le deuxième <xref:System.Activities.Statements.CompensableActivity> n'est pas confirmé. Cela produit un ordre de compensation de deux, puis un.  
  
#### <a name="to-use-this-sample"></a>Pour utiliser cet exemple  
  
1.  À l'aide de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ouvrez le fichier solution AutoConfirmSample.sln.  
  
2.  Pour générer la solution, appuyez sur Ctrl+Maj+B.  
  
3.  Pour exécuter la solution, appuyez sur Ctrl+F5.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples Windows Workflow Foundation (WF) pour .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Compensation\AutoConfirm`
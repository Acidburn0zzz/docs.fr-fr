---
title: Advanced Policy
ms.date: 03/30/2017
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
ms.openlocfilehash: becdc28affd877239474d6f0f007a480297bccb8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672838"
---
# <a name="advanced-policy"></a>Advanced Policy
Cet exemple complète l'exemple de stratégie simple. Outre les règles de remise résidentielle et de remise d'entreprise traitées dans l'exemple de stratégie simple, plusieurs nouvelles règles ont été ajoutées.  
  
 Une règle de valeur élevée est ajoutée afin de proposer une remise plus importante pour les commandes à valeur élevée. Sa valeur de priorité est inférieure à celle des deux règles précédentes de sorte qu'elle remplace le champ de remise et reste prioritaire par rapport aux règles de remise résidentielle et d'entreprise.  
  
 Une règle de calcul du total est également ajoutée afin de calculer le montant total en fonction du niveau de remise. Elle indique comment faire référence à une méthode définie sur l'activité de workflow et comment utiliser des actions Else. Cette règle illustre également le comportement de chaînage puisqu'elle sera évaluée à chaque modification du champ de remise. En outre, l'attribution de méthode est illustrée avec la classe RuleWriteAttribute sur la méthode CalculateTotal. Les règles impliquées (ErrorTotalRule) doivent être réévaluées chaque fois que la méthode est exécutée.  
  
 La dernière règle ajoutée détecte les erreurs (dans le cas présent, Total inférieur à 0). Si cela se produit, l'exécution de la stratégie est interrompue.  
  
 Enfin, les appels `Console.Writeline` sont ajoutés en tant qu'actions à chaque règle afin d'apporter plus de visibilité à l'exécution de la règle, tout en montrant également qu'il est possible d'accéder aux méthodes statiques sur les types référencés. Vous pouvez également utiliser le traçage pour obtenir une meilleure visibilité des règles exécutées.  
  
 Les règles utilisées dans cet exemple sont les suivantes :  
  
 **ResidentialDiscountRule :**  
  
 IF OrderValue > 500 AND CustomerType = Residential  
  
 THEN Discount = 5%  
  
 **BusinessDiscountRule :**  
  
 IF OrderValue > 10000 AND CustomerType = Business  
  
 THEN Discount = 10%  
  
 **HighValueDiscountRule :**  
  
 IF OrderValue > 20000  
  
 THEN Discount = 15%  
  
 **TotalRule :**  
  
 IF Discount > 0  
  
 THEN CalculateTotal(OrderValue, Discount)  
  
 ELSE Total = OrderValue  
  
 **Impliquées ErrorTotalRule :**  
  
 IF Total \< 0  
  
 THEN Error = "Fired ErrorTotalRule"; Halt  
  
 L'évaluation et l'exécution des règles peuvent également être consultées par traçage et suivi.  
  
### <a name="to-build-the-sample"></a>Pour générer l'exemple  
  
1.  Ouvrez la solution dans [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Générez la solution en appuyant sur Ctrl+Maj+B.  
  
3.  Exécutez la solution sans débogage en appuyant sur Ctrl+F5.  
  
### <a name="to-run-the-sample"></a>Pour exécuter l'exemple  
  
-   Dans la fenêtre d'invite de commandes du Kit de développement logiciel (SDK), exécutez le fichier .exe dans le dossier AdvancedPolicy\bin\debug (ou le dossier AdvancedPolicy\bin pour la version Visual Basic de l'exemple), situé sous le dossier principal de l'exemple.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer :  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant :  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Stratégie simple](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)

---
title: InvokeMethod
ms.date: 03/30/2017
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
ms.openlocfilehash: 861e0cf160aec9814abcf8c27c37ce13a5d88b2a
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2018
ms.locfileid: "44778615"
---
# <a name="invokemethod"></a>InvokeMethod
Cet exemple présente les différentes façons d'utiliser l'activité <xref:System.Activities.Statements.InvokeMethod> pour appeler les méthodes d'une classe.  
  
 Une méthode appartient à une classe et représente un ensemble contenu d'opérations. L'activité <xref:System.Activities.Statements.InvokeMethod> vous permet d'appeler des méthodes sur des objets ou des types, de passer des paramètres et d'obtenir la valeur de retour. Les méthodes peuvent être appelées de façon synchrone ou asynchrone.  
  
## <a name="sample-details"></a>Détails de l'exemple  
 Cet exemple utilise l'activité <xref:System.Activities.Statements.InvokeMethod> pour effectuer les scénarios suivants :  
  
1.  Appeler une méthode d'instance sans paramètres.  
  
2.  Appeler une méthode d'instance avec deux paramètres (<xref:System.String> et <xref:System.Int32>).  
  
3.  Appeler une méthode d'instance avec deux paramètres (<xref:System.String> et <xref:System.Int32>) et un tableau de paramètres de type <xref:System.String>[].  
  
4.  Appeler une méthode d'instance avec deux paramètres de type <xref:System.Int32> et un résultat de type <xref:System.Int32>. Dans ce scénario, la valeur de résultat est liée à une variable et utilisée dans une autre activité. Elle est affichée dans la console à l'aide de l'activité <xref:System.Activities.Statements.WriteLine>.  
  
5.  Appeler une méthode statique avec deux paramètres de type <xref:System.String> et <xref:System.Int32>.  
  
6.  Appeler une méthode d'instance avec un paramètre générique de type <xref:System.String>.  
  
7.  Appeler une méthode statique avec deux paramètres génériques de type <xref:System.String> et <xref:System.Int32>.  
  
8.  Appeler une méthode d'instance qui a un paramètre passée par référence de type <xref:System.String>. Dans ce scénario, le paramètre de référence est lié à une variable (`outParam`) et utilisé dans une autre activité. Il est affiché sur la console à l'aide de l'activité <xref:System.Activities.Statements.WriteLine>.  
  
9. Appeler une méthode d'instance asynchrone.  
  
10. Appeler deux méthodes différentes sur la même instance d'un objet à l'aide de deux activités <xref:System.Activities.Statements.InvokeMethod>.  
  
11. Stocker une valeur dans une instance d'un objet.  
  
12. Récupérer une valeur à partir d'une instance d'un objet.  
  
## <a name="to-use-this-sample"></a>Pour utiliser cet exemple  
 Cet exemple est fourni dans deux versions. La première version de cet exemple illustre l’utilisation de <xref:System.Activities.Statements.InvokeMethod> via c# du code à l’aide du modèle de programmation Windows Workflow Foundation (WF) et se trouve sous le dossier CodedWorkflow\CS. La deuxième version, qui illustre l'utilisation de <xref:System.Activities.Statements.InvokeMethod> à l'aide de code XAML, se trouve dans le dossier DesignerWorkflow\CS.  
  
#### <a name="to-run-the-coded-workflow-sample"></a>Pour exécuter l'exemple de workflow encodé  
  
1.  À l'aide de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ouvrez le fichier solution InvokeMethodUsage.sln situé dans le dossier CodedWorkflow\CS.  
  
2.  Pour générer la solution, appuyez sur Ctrl+Maj+B.  
  
3.  Pour exécuter la solution, appuyez sur Ctrl+F5.  
  
#### <a name="to-run-the-designer-workflow-sample"></a>Pour exécuter l'exemple de concepteur de workflow  
  
1.  À l'aide de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ouvrez le fichier solution InvokeMethodUsage.sln situé dans le dossier DesignerWorkflow\CS.  
  
2.  Pour générer la solution, appuyez sur Ctrl+Maj+B.  
  
3.  Pour exécuter la solution, appuyez sur Ctrl+F5.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`
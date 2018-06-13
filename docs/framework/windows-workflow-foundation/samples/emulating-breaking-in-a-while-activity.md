---
title: Émulation de l'interruption dans une activité While
ms.date: 03/30/2017
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
ms.openlocfilehash: 37c64c2b8dc03d58f9c2802edef644fe4888e87d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514711"
---
# <a name="emulating-breaking-in-a-while-activity"></a>Émulation de l'interruption dans une activité While
Cet exemple montre comment interrompre le mécanisme d'exécution en boucle des activités suivantes : <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While> et <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 Cela est utile, car Windows Workflow Foundation (WF) n’inclut aucune activité pour interrompre l’exécution de ces boucles.  
  
## <a name="scenario"></a>Scénario  
 L'exemple recherche le premier fournisseur fiable dans une liste de fournisseurs (instances de la classe `Vendor`). Chaque fournisseur a un `ID`, un `Name` et une valeur de fiabilité numérique qui détermine à quel point le fournisseur est digne de confiance. L'exemple crée une activité personnalisée appelée `FindReliableVendor` qui reçoit deux paramètres d'entrée (une liste de fournisseurs et une valeur de fiabilité minimale) et retourne le premier fournisseur de la liste qui correspond aux critères fournis.  
  
## <a name="breaking-a-loop"></a>Interruption d'une boucle  
 Windows Workflow Foundation (WF) n’inclut pas une activité pour interrompre une boucle. L'exemple de code parvient à interrompre une boucle à l'aide d'une activité <xref:System.Activities.Statements.If> et de plusieurs variables. Dans l'exemple, l'activité <xref:System.Activities.Statements.While> est interrompue une fois qu'une valeur autre que `reliableVendor` a été affectée à la variable `null`.  
  
 L'exemple de code suivant montre comment l'exemple interrompt une boucle while.  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a>Pour utiliser cet exemple  
  
1.  À l'aide de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ouvrez le fichier solution EmulatingBreakInWhile.sln.  
  
2.  Pour générer la solution, appuyez sur Ctrl+Maj+B.  
  
3.  Pour exécuter la solution, appuyez sur Ctrl+F5.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples Windows Workflow Foundation (WF) pour .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`
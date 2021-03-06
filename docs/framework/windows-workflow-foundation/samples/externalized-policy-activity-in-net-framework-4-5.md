---
title: Activité de stratégie externalisée dans .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 622b0f14281d5b068700d9e4fe03485aa1a60fcb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338278"
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Activité de stratégie externalisée dans .NET Framework 4.5

Cet exemple montre comment l’activité ExternalizedPolicy4 permet l’exécution existant [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Windows Workflow Foundation (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> dans des objets [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Windows Workflow Foundation (WF 4.5) directement à l’aide du moteur de règles qui est fourni dans WF 3.5. À l'aide de cette activité, vous pouvez ouvrir et exécuter n'importe quel <xref:System.Workflow.Activities.Rules.RuleSet> WF 3.5 existant. Pour plus d’informations sur le moteur de règles WF 3.5 inclus dans le cadre de Windows Workflow Foundation, veuillez lire [Introduction au moteur de règles Windows Workflow Foundation](https://go.microsoft.com/fwlink/?LinkId=166079). Pour plus d’informations sur la migration de règles à [!INCLUDE[wf1](../../../../includes/wf1-md.md)] dans [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], veuillez lire les conseils de migration sur [conseils de Migration](../migration-guidance.md).

## <a name="projects-in-this-sample"></a>Projets dans cet exemple

|Nom du projet|Description|Fichiers principaux|
|-|-|-|
|ExternalizedPolicy4|Contient l'activité ExternalizedPolicy4 et son concepteur WF 4.5.|**ExternalizedPolicy4.cs**: définition d’activité.<br /><br /> **ExternalizedPolicy4Designer.xaml**: Concepteur personnalisé pour l’activité ExternalizedPolicy4. Il utilise l'éditeur de Règles (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>) du moteur de règles WF 3.5.|
|ImperativeCodeClientSample|Exemple d'application cliente qui configure et exécute un workflow à l'aide d'une application ExternalizedPolicy4 utilisant du code C# impératif (aucun concepteur utilisé).|**ApplyDiscount.rules**: Fichier avec [!INCLUDE[wf1](../../../../includes/wf1-md.md)] définitions de règles.<br /><br /> **Order.cs**: Type qui représente une commande client. Les règles sont appliquées aux objets de ce type.<br /><br /> **Program.cs** : Configure et exécute un workflow qui a une activité Policy4 pour appliquer les règles définies dans ApplyDiscount.rules aux instances d’objets Order.<br /><br /> App.config : Le fichier de configuration avec le chemin d’accès du fichier de règles.|
|DesignerClientSample|Exemple d'application cliente qui configure et exécute un workflow à l'aide d'une application ExternalPolicy4 dans le concepteur [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1.XAML**: Workflow séquentiel qui utilise une activité Policy4 pour effectuer des évaluations de la règle.<br /><br /> **Program.cs** : Exécute une instance du workflow définie dans Sequence1.xaml.|

## <a name="the-externalizedpolicy4-activity"></a>Activité ExternalizedPolicy4

L'activité ExternalizedPolicy4 est un <xref:System.Activities.NativeActivity> qui permet l'exécution d'objets <xref:System.Workflow.Activities.Rules.RuleSet> WF 3.5 dans des workflows WF 4.5. L'exemple suivant est une définition simplifiée du modèle d'objet public de l'activité.

```
public class ExternalizedPolicy4Activity<TResult>: CodeActivity
{
    public string RulesFilePath

    public string RuleSetName

    [RequiredArgument]
    public InArgument<T> TargetObject

    [RequiredArgument]
    public OutArgument<T> ResultObject

    public OutArgument<ValidationErrorCollection> ValidationErrors
}
```

|Propriété|Description|
|-|-|
|RuleSetFilePath|Chemin d’accès au fichier <xref:System.Workflow.Activities.Rules.RuleSet> de .NET Framework 3.5 à évaluer lorsque l’activité est exécutée.|
|RuleSetName|Nom du <xref:System.Workflow.Activities.Rules.RuleSet> à utiliser dans le fichier .rules.|
|TargetObject|Objet sur lequel les objets <xref:System.Workflow.Activities.Rules.Rule> de <xref:System.Workflow.Activities.Rules.RuleSet> sont évalués.|
|ResultObject|Objet qui en résulte une fois les règles appliquées (par exemple, les règles sont appliquées sur l’argument Input et le résultat est stocké dans l’argument Result).|
|ValidationError|Liste des erreurs de validation retournées par le moteur de règles WF 3.5 lors de la validation de <xref:System.Workflow.Activities.Rules.RuleSet> sur l’objet cible avant l’exécution.|

## <a name="externalizedpolicy4-activity-designer"></a>Concepteur de l'activité ExternalizedPolicy4

Le concepteur d'ExternalizedPolicy4 vous permet de configurer une activité pour utiliser un ensemble de règles (RuleSet) existant sans écrire de code. Définissez simplement le chemin d’accès de l’emplacement où se trouve le fichier .rules et spécifiez le nom du <xref:System.Workflow.Activities.Rules.RuleSet> que vous voulez utiliser. Il vous permet également de modifier <xref:System.Workflow.Activities.Rules.RuleSet>. Après avoir généré la solution, il se trouve dans la boîte à outils, dans la section Microsoft.Samples.Activities.Rules. Le concepteur vous permet de sélectionner un fichier .rules et un <xref:System.Workflow.Activities.Rules.RuleSet>. Lorsque le **modifier le RuleSet** bouton est activé, le WF 3.5 <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> s’affiche. Cette boîte de dialogue, qui est l'éditeur de règles WF 3.5 réhébergé, est utilisée pour afficher et modifier les règles que l'activité ExternalizedPolicy4 exécute.

## <a name="policy4-and-externalpolicy4"></a>Policy4 et ExternalPolicy4

L’activité de stratégie vous permet de créer et exécuter un ensemble de règles de .NET Framework 3.5 dans un flux de travail WF 4.5. <xref:System.Workflow.Activities.Rules.RuleSet> est sérialisé inline dans la définition XAML de l'activité Policy4. L'exemple ExternalizedPolicy4 montre comment utiliser un <xref:System.Workflow.Activities.Rules.RuleSet> externe existant (contenu dans un fichier .rules).

## <a name="use-this-sample"></a>Utilisez cet exemple

Aucune configuration particulière n'est requise pour exécuter cet exemple. Ouvrez la solution dans Visual Studio, puis appuyez sur **F5** pour exécuter l’application.

Cet exemple contient deux applications clientes : ImperativeCodeClientSample et DesignerClientSample. Le client ImperativeCodeClientSample montre comment configurer et exécuter l'activité ExternalizedPolicy4 à l'aide de code C# impératif. DesignerClientSample montre comment configurer et exécuter l'activité ExternalizedPolicy4 à l'aide du concepteur.

### <a name="run-the-imperativecodeclientsample-application"></a>Exécuter l’application ImperativeCodeClientSample

1. À l’aide de Visual Studio, ouvrez le *Policy4sample.sln* fichier solution.

2. Dans **l’Explorateur de solutions**, avec le bouton droit le **ImperativeCodeClientSample** de projet, puis sélectionnez **définir comme projet de démarrage**.

3. Pour exécuter le projet, appuyez sur **Ctrl**+**F5**.

### <a name="run-the-designerclientsample-application"></a>Exécutez l’application DesignerClientSample

1. À l’aide de Visual Studio, ouvrez le *Policy4sample.sln* fichier solution.

2. Dans **l’Explorateur de solutions**, avec le bouton droit le **DesignerClientSample** de projet, puis sélectionnez **définir comme projet de démarrage**.

3. Appuyez sur **Ctrl**+**MAJ**+**B** pour compiler le projet.

4. Appuyez sur **Ctrl**+**F5** pour exécuter le projet.

> [!IMPORTANT]
> Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples.
>
> Cet exemple se trouve dans le répertoire suivant :
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`

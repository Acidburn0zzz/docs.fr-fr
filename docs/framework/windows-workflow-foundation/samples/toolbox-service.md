---
title: Service de boîte à outils
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b21f10c763f3f82591f947eb4cc48cf90f4ac79
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406460"
---
# <a name="toolbox-service"></a><span data-ttu-id="5a897-102">Service de boîte à outils</span><span class="sxs-lookup"><span data-stu-id="5a897-102">Toolbox Service</span></span>
<span data-ttu-id="5a897-103">Cet exemple montre comment mettre à jour les activités de la boîte à outils [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] en fonction du contexte du workflow.</span><span class="sxs-lookup"><span data-stu-id="5a897-103">This sample demonstrates how to update the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] Toolbox activities based on the context of the workflow.</span></span> <span data-ttu-id="5a897-104">L'exemple contient un workflow qui modifie le contenu de la boîte à outils suivant qu'une activité personnalisée est sélectionnée ou non.</span><span class="sxs-lookup"><span data-stu-id="5a897-104">The sample contains a workflow that changes the toolbox contents based on whether a custom activity is selected.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="5a897-105">Discussion</span><span class="sxs-lookup"><span data-stu-id="5a897-105">Discussion</span></span>  
 <span data-ttu-id="5a897-106">Pendant la création de workflows, les clients veulent généralement que leur boîte à outils soit contextuelle.</span><span class="sxs-lookup"><span data-stu-id="5a897-106">During workflow authoring, customers generally want their Toolbox to be context sensitive.</span></span> <span data-ttu-id="5a897-107">Par exemple, l'utilisateur peut vouloir s'assurer que la boîte à outils affiche des activités supplémentaires lorsqu'une activité spécifique est ajoutée au workflow.</span><span class="sxs-lookup"><span data-stu-id="5a897-107">For example, the user may want to ensure that the Toolbox shows a few additional activities when a specific activity is added to the workflow.</span></span> <span data-ttu-id="5a897-108">Si les activités sont supprimées du workflow, la boîte à outils doit réagir de façon appropriée en fonction des spécifications du domaine.</span><span class="sxs-lookup"><span data-stu-id="5a897-108">If the activities are removed from the workflow, the toolbox should react appropriately based on the domain requirements.</span></span>  
  
 <span data-ttu-id="5a897-109">Dans un concepteur de workflow réhébergé, vous contrôlez le contrôle Toolbox et pouvez vous assurer que, suivant les modifications de modèle dans le workflow, l'hôte déclenche les modifications appropriées dans le contrôle Toolbox.</span><span class="sxs-lookup"><span data-stu-id="5a897-109">In a re-hosted workflow designer, you control the Toolbox control and can ensure that based on the Model changes in the workflow, the host triggers appropriate changes in the Toolbox control.</span></span> <span data-ttu-id="5a897-110">Toutefois, dans [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], la boîte à outils n'est pas contrôlée par l'utilisateur. Par conséquent, une interface est requise pour modifier son contenu.</span><span class="sxs-lookup"><span data-stu-id="5a897-110">However, in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], the toolbox is not controlled by the user and thus an interface is required to modify its contents.</span></span> <span data-ttu-id="5a897-111">`IActivityToolboxService` est cette interface.</span><span class="sxs-lookup"><span data-stu-id="5a897-111">`IActivityToolboxService` is that interface.</span></span>  
  
 <span data-ttu-id="5a897-112">L'API fournit les quatre méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5a897-112">The API provides the following four methods.</span></span>  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5a897-113">Pour configurer, générer et exécuter l'exemple</span><span class="sxs-lookup"><span data-stu-id="5a897-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5a897-114">À l'aide de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ouvrez le fichier solution WorkflowSimulator.sln.</span><span class="sxs-lookup"><span data-stu-id="5a897-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WorkflowSimulator.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5a897-115">Générez la solution en appuyant sur Ctrl+Maj+B.</span><span class="sxs-lookup"><span data-stu-id="5a897-115">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5a897-116">Ouvrez le fichier Workflow.xaml.</span><span class="sxs-lookup"><span data-stu-id="5a897-116">Open the Workflow.xaml file.</span></span>  
  
4.  <span data-ttu-id="5a897-117">Ajouter un **CustomActivity** en faisant glisser à partir de la boîte à outils.</span><span class="sxs-lookup"><span data-stu-id="5a897-117">Add a **CustomActivity** by dragging and dropping it from the toolbox.</span></span> <span data-ttu-id="5a897-118">Notez qu’une catégorie de boîte à outils supplémentaire appelée : **nouvelle catégorie WF** avec une activité supplémentaire **affecter**.</span><span class="sxs-lookup"><span data-stu-id="5a897-118">Notice that an additional Toolbox category called: **New WF Category** with an additional activity **Assign**.</span></span>  
  
5.  <span data-ttu-id="5a897-119">Présent, désélectionnez le **CustomActivity** en faisant glisser une autre activité dedans.</span><span class="sxs-lookup"><span data-stu-id="5a897-119">Now unselect the **CustomActivity** by dragging another activity into it.</span></span>  
  
6.  <span data-ttu-id="5a897-120">L’élément **affecter** dans la catégorie **nouvelle catégorie WF** sous boîte à outils est supprimé.</span><span class="sxs-lookup"><span data-stu-id="5a897-120">The item **Assign** in the category **New WF Category** under Toolbox is now removed.</span></span> <span data-ttu-id="5a897-121">De plus, étant donné qu'il ne reste aucun élément dans la catégorie, cette dernière est également supprimée.</span><span class="sxs-lookup"><span data-stu-id="5a897-121">Also, because there are no more items left in the category, the category is removed as well.</span></span>  
  
7.  <span data-ttu-id="5a897-122">Sélectionnez le **CustomActivity** à nouveau et la catégorie et **affecter** activité est rajoutée.</span><span class="sxs-lookup"><span data-stu-id="5a897-122">Select the **CustomActivity** again and the category and **Assign** activity is added back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5a897-123">Les exemples peuvent déjà être installés sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5a897-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5a897-124">Recherchez le répertoire (par défaut) suivant avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="5a897-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5a897-125">Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples.</span><span class="sxs-lookup"><span data-stu-id="5a897-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5a897-126">Cet exemple se trouve dans le répertoire suivant.</span><span class="sxs-lookup"><span data-stu-id="5a897-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`

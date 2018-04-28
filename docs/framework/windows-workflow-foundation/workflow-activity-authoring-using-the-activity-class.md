---
title: Création de l'activité de workflow à l'aide de la classe d'activité
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 517e646c8a84ed4374c01da974d952d4f50a4e22
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="71a2f-102">Création de l'activité de workflow à l'aide de la classe d'activité</span><span class="sxs-lookup"><span data-stu-id="71a2f-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="71a2f-103">La façon la plus simple de créer une activité à l’aide de Windows Workflow Foundation (WF) dans [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] consiste à créer une classe qui hérite de <xref:System.Activities.Activity> qui crée des fonctionnalités en assemblant personnalisé activités ou les activités à partir de la [intégrés Bibliothèque d’activités](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="71a2f-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="71a2f-104">Cette rubrique montre comment créer une activité qui écrit deux messages sur la console.</span><span class="sxs-lookup"><span data-stu-id="71a2f-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="71a2f-105">Pour créer une activité personnalisée à l'aide du concepteur d'activités</span><span class="sxs-lookup"><span data-stu-id="71a2f-105">To create a custom Activity using the activity designer</span></span>  
  
1.  <span data-ttu-id="71a2f-106">Ouvrez [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71a2f-106">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="71a2f-107">Sélectionnez Fichier, Nouveau, puis Projet.</span><span class="sxs-lookup"><span data-stu-id="71a2f-107">Select File, New, Project.</span></span> <span data-ttu-id="71a2f-108">Sélectionnez **Workflow 4.0** sous **Visual C#** dans les **Types de projets** , puis sélectionnez le **v2010** nœud.</span><span class="sxs-lookup"><span data-stu-id="71a2f-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="71a2f-109">Sélectionnez **bibliothèque d’activités** dans les **modèles** fenêtre.</span><span class="sxs-lookup"><span data-stu-id="71a2f-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="71a2f-110">Nommez le nouveau projet HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="71a2f-110">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="71a2f-111">Ouvrez la nouvelle activité.</span><span class="sxs-lookup"><span data-stu-id="71a2f-111">Open the new activity.</span></span>  <span data-ttu-id="71a2f-112">Faites glisser une activité <xref:System.Activities.Statements.Sequence> de la boîte à outils jusqu'à l'aire du concepteur.</span><span class="sxs-lookup"><span data-stu-id="71a2f-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>  
  
4.  <span data-ttu-id="71a2f-113">Faites glisser une activité <xref:System.Activities.Statements.WriteLine> dans l'activité <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="71a2f-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="71a2f-114">Entrez `"Hello World"` (avec les guillemets) dans le **texte** champ.</span><span class="sxs-lookup"><span data-stu-id="71a2f-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>  
  
5.  <span data-ttu-id="71a2f-115">Faites glisser une deuxième activité <xref:System.Activities.Statements.WriteLine> dans l'activité <xref:System.Activities.Statements.Sequence>, en dessous de la première.</span><span class="sxs-lookup"><span data-stu-id="71a2f-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="71a2f-116">Entrez `"Goodbye"` (avec les guillemets) dans le **texte** champ.</span><span class="sxs-lookup"><span data-stu-id="71a2f-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>

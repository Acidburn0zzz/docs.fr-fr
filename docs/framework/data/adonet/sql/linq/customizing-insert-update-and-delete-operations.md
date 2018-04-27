---
title: Personnalisation des opérations d'insertion, de mise à jour et de suppression
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 410385d1689a9fd15a1399411f601e407d590830
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="7b86c-102">Personnalisation des opérations d'insertion, de mise à jour et de suppression</span><span class="sxs-lookup"><span data-stu-id="7b86c-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="7b86c-103">Par défaut, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] génère du SQL dynamique pour implémenter les opérations d'insertion, de lecture, de mise à jour et de suppression.</span><span class="sxs-lookup"><span data-stu-id="7b86c-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="7b86c-104">Dans la pratique toutefois, vous personnalisez généralement votre application en fonction de vos besoins professionnels.</span><span class="sxs-lookup"><span data-stu-id="7b86c-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b86c-105">Si vous utilisez Visual Studio, vous pouvez utiliser la [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] pour personnaliser les insérer, mettre à jour et supprimer des actions.</span><span class="sxs-lookup"><span data-stu-id="7b86c-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="7b86c-106">Cette section de rubriques décrit les techniques que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fournit pour personnaliser les opérations d'insertion, de lecture, de mise à jour et de suppression dans votre application.</span><span class="sxs-lookup"><span data-stu-id="7b86c-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b86c-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7b86c-107">In This Section</span></span>  
 [<span data-ttu-id="7b86c-108">Personnalisation d’opérations : vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="7b86c-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="7b86c-109">Décrit les différentes techniques fournies par [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] pour personnaliser les opérations d'insertion, de lecture, de mise à jour et de suppression.</span><span class="sxs-lookup"><span data-stu-id="7b86c-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="7b86c-110">Opérations d’insertion, de mise à jour et de suppression</span><span class="sxs-lookup"><span data-stu-id="7b86c-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="7b86c-111">Décrit les processus par défaut de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] pour manipuler des données de base de données.</span><span class="sxs-lookup"><span data-stu-id="7b86c-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="7b86c-112">Responsabilités du développeur en matière de substitution du comportement par défaut</span><span class="sxs-lookup"><span data-stu-id="7b86c-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="7b86c-113">Décrit le rôle du développeur dans l'implémentation des spécifications non appliquées par [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b86c-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="7b86c-114">Ajout d’une logique métier à l’aide de méthodes partielles</span><span class="sxs-lookup"><span data-stu-id="7b86c-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="7b86c-115">Explique comment utiliser des méthodes partielles pour substituer des méthodes générées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="7b86c-115">Describes how to use partial methods to override autogenerated methods.</span></span>

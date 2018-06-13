---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510651"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="f27f8-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f27f8-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f27f8-103">Propriétés</span><span class="sxs-lookup"><span data-stu-id="f27f8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f27f8-104">ID</span><span class="sxs-lookup"><span data-stu-id="f27f8-104">ID</span></span>|<span data-ttu-id="f27f8-105">1018</span><span class="sxs-lookup"><span data-stu-id="f27f8-105">1018</span></span>|  
|<span data-ttu-id="f27f8-106">Mots clés</span><span class="sxs-lookup"><span data-stu-id="f27f8-106">Keywords</span></span>|<span data-ttu-id="f27f8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f27f8-107">WFRuntime</span></span>|  
|<span data-ttu-id="f27f8-108">Niveau</span><span class="sxs-lookup"><span data-stu-id="f27f8-108">Level</span></span>|<span data-ttu-id="f27f8-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="f27f8-109">Verbose</span></span>|  
|<span data-ttu-id="f27f8-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f27f8-110">Channel</span></span>|<span data-ttu-id="f27f8-111">Microsoft-Windows-Application Server-Applications/Débogage</span><span class="sxs-lookup"><span data-stu-id="f27f8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f27f8-112">Description</span><span class="sxs-lookup"><span data-stu-id="f27f8-112">Description</span></span>  
 <span data-ttu-id="f27f8-113">Indique qu'un CancelActivityWorkItem démarre l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f27f8-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f27f8-114">Message</span><span class="sxs-lookup"><span data-stu-id="f27f8-114">Message</span></span>  
 <span data-ttu-id="f27f8-115">Début de l'exécution d'un CancelActivityWorkItem pour l'activité « %1 », DisplayName : « %2 », InstanceId : « %3 ».</span><span class="sxs-lookup"><span data-stu-id="f27f8-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f27f8-116">Détails</span><span class="sxs-lookup"><span data-stu-id="f27f8-116">Details</span></span>  
  
|<span data-ttu-id="f27f8-117">Nom d'élément de données</span><span class="sxs-lookup"><span data-stu-id="f27f8-117">Data Item Name</span></span>|<span data-ttu-id="f27f8-118">Type d'élément de données</span><span class="sxs-lookup"><span data-stu-id="f27f8-118">Data Item Type</span></span>|<span data-ttu-id="f27f8-119">Description</span><span class="sxs-lookup"><span data-stu-id="f27f8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f27f8-120">Activité</span><span class="sxs-lookup"><span data-stu-id="f27f8-120">Activity</span></span>|<span data-ttu-id="f27f8-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f27f8-121">xs:string</span></span>|<span data-ttu-id="f27f8-122">Nom de type de l'activité.</span><span class="sxs-lookup"><span data-stu-id="f27f8-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f27f8-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f27f8-123">DisplayName</span></span>|<span data-ttu-id="f27f8-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f27f8-124">xs:string</span></span>|<span data-ttu-id="f27f8-125">Nom complet de l'activité.</span><span class="sxs-lookup"><span data-stu-id="f27f8-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f27f8-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f27f8-126">InstanceId</span></span>|<span data-ttu-id="f27f8-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f27f8-127">xs:string</span></span>|<span data-ttu-id="f27f8-128">ID d'instance de l'activité.</span><span class="sxs-lookup"><span data-stu-id="f27f8-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f27f8-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f27f8-129">AppDomain</span></span>|<span data-ttu-id="f27f8-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f27f8-130">xs:string</span></span>|<span data-ttu-id="f27f8-131">Chaîne retournée par AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f27f8-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

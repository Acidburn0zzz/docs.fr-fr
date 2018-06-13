---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512663"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="59678-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="59678-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="59678-103">Propriétés</span><span class="sxs-lookup"><span data-stu-id="59678-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59678-104">ID</span><span class="sxs-lookup"><span data-stu-id="59678-104">ID</span></span>|<span data-ttu-id="59678-105">1131</span><span class="sxs-lookup"><span data-stu-id="59678-105">1131</span></span>|  
|<span data-ttu-id="59678-106">Mots clés</span><span class="sxs-lookup"><span data-stu-id="59678-106">Keywords</span></span>|<span data-ttu-id="59678-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="59678-107">WFRuntime</span></span>|  
|<span data-ttu-id="59678-108">Niveau</span><span class="sxs-lookup"><span data-stu-id="59678-108">Level</span></span>|<span data-ttu-id="59678-109">Information</span><span class="sxs-lookup"><span data-stu-id="59678-109">Information</span></span>|  
|<span data-ttu-id="59678-110">Canal</span><span class="sxs-lookup"><span data-stu-id="59678-110">Channel</span></span>|<span data-ttu-id="59678-111">Microsoft-Windows-Application Server-Applications/Débogage</span><span class="sxs-lookup"><span data-stu-id="59678-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="59678-112">Description</span><span class="sxs-lookup"><span data-stu-id="59678-112">Description</span></span>  
 <span data-ttu-id="59678-113">Pendant l'étape CacheMetadata, l'activité InvokeMethod indique qu'elle utilise le modèle asynchrone lors de l'appel de la méthode.</span><span class="sxs-lookup"><span data-stu-id="59678-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="59678-114">Message</span><span class="sxs-lookup"><span data-stu-id="59678-114">Message</span></span>  
 <span data-ttu-id="59678-115">InvokeMethod « %1 » - la méthode utilise un modèle asynchrone de « %2 » et « %3 ».</span><span class="sxs-lookup"><span data-stu-id="59678-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="59678-116">Détails</span><span class="sxs-lookup"><span data-stu-id="59678-116">Details</span></span>  
  
|<span data-ttu-id="59678-117">Nom d'élément de données</span><span class="sxs-lookup"><span data-stu-id="59678-117">Data Item Name</span></span>|<span data-ttu-id="59678-118">Type d'élément de données</span><span class="sxs-lookup"><span data-stu-id="59678-118">Data Item Type</span></span>|<span data-ttu-id="59678-119">Description</span><span class="sxs-lookup"><span data-stu-id="59678-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="59678-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="59678-120">InvokeMethod</span></span>|<span data-ttu-id="59678-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="59678-121">xs:string</span></span>|<span data-ttu-id="59678-122">Nom complet de l'activité InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="59678-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="59678-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="59678-123">BeginMethod</span></span>|<span data-ttu-id="59678-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="59678-124">xs:string</span></span>|<span data-ttu-id="59678-125">Nom de la méthode Begin.</span><span class="sxs-lookup"><span data-stu-id="59678-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="59678-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="59678-126">EndMethod</span></span>|<span data-ttu-id="59678-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="59678-127">xs:string</span></span>|<span data-ttu-id="59678-128">Nom de la méthode End.</span><span class="sxs-lookup"><span data-stu-id="59678-128">The name of the end method.</span></span>|  
|<span data-ttu-id="59678-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="59678-129">AppDomain</span></span>|<span data-ttu-id="59678-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="59678-130">xs:string</span></span>|<span data-ttu-id="59678-131">Chaîne retournée par AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="59678-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

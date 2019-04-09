---
title: Événements ETW du CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb7520518497b244be8be3751ca8a3063a02717a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135861"
---
# <a name="clr-etw-events"></a><span data-ttu-id="302fa-102">Événements ETW du CLR</span><span class="sxs-lookup"><span data-stu-id="302fa-102">CLR ETW Events</span></span>
<span data-ttu-id="302fa-103">Les rubriques de cette section décrivent le suivi d’événements pour les événements Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="302fa-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="302fa-104">Chaque événement est associé à un mot clé et à un niveau, qui sont décrits dans la rubrique [Niveaux et mots clés ETW du CLR](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="302fa-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="302fa-105">Le CLR a deux fournisseurs pour les événements :</span><span class="sxs-lookup"><span data-stu-id="302fa-105">The CLR has two providers for the events:</span></span>  
  
-   <span data-ttu-id="302fa-106">Le fournisseur de runtime, qui déclenche des événements en fonction des mots clés (catégories d’événements) activés.</span><span class="sxs-lookup"><span data-stu-id="302fa-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="302fa-107">Le GUID du fournisseur de runtime du CLR est e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="302fa-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
-   <span data-ttu-id="302fa-108">Le fournisseur d’arrêt, qui est réservé à des usages spécifiques.</span><span class="sxs-lookup"><span data-stu-id="302fa-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="302fa-109">Le GUID du fournisseur d’arrêt du CLR est a669021c-c450-4609-a035-5af59af4df18.</span><span class="sxs-lookup"><span data-stu-id="302fa-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="302fa-110">Pour plus d’informations sur les fournisseurs, consultez [Fournisseurs ETW du CLR](../../../docs/framework/performance/clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="302fa-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="302fa-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="302fa-111">In This Section</span></span>  
 [<span data-ttu-id="302fa-112">Événements d’information du runtime</span><span class="sxs-lookup"><span data-stu-id="302fa-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="302fa-113">Capture des informations sur l’exécution, notamment la référence, le numéro de version, le mode d’activation du runtime, les paramètres de ligne de commande avec lesquels il a été démarré, le GUID (le cas échéant) et d’autres informations pertinentes.</span><span class="sxs-lookup"><span data-stu-id="302fa-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="302fa-114">Événement d’exception Thrown_V1</span><span class="sxs-lookup"><span data-stu-id="302fa-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="302fa-115">Capture des informations sur les exceptions levées.</span><span class="sxs-lookup"><span data-stu-id="302fa-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="302fa-116">Événements de contention</span><span class="sxs-lookup"><span data-stu-id="302fa-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="302fa-117">Capture des informations sur les conflits de verrous du moniteur ou de verrous natifs utilisés par le runtime.</span><span class="sxs-lookup"><span data-stu-id="302fa-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="302fa-118">Événements de pool de threads</span><span class="sxs-lookup"><span data-stu-id="302fa-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="302fa-119">Capture des informations sur les pools de threads de travail et les pools de threads d’E/S.</span><span class="sxs-lookup"><span data-stu-id="302fa-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="302fa-120">Événements de chargeur</span><span class="sxs-lookup"><span data-stu-id="302fa-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="302fa-121">Capture des informations sur le chargement et le déchargement des domaines d’application, des assemblys et des modules.</span><span class="sxs-lookup"><span data-stu-id="302fa-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="302fa-122">Événements de méthode</span><span class="sxs-lookup"><span data-stu-id="302fa-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="302fa-123">Capture des informations sur les méthodes CLR pour la résolution des symboles.</span><span class="sxs-lookup"><span data-stu-id="302fa-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="302fa-124">Événements de garbage collection</span><span class="sxs-lookup"><span data-stu-id="302fa-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="302fa-125">Capture des informations relatives au garbage collection, pour vous aider lors du diagnostic et du débogage.</span><span class="sxs-lookup"><span data-stu-id="302fa-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="302fa-126">Événements de traçage JIT</span><span class="sxs-lookup"><span data-stu-id="302fa-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="302fa-127">Capture des informations sur l’incorporation (inlining) juste à temps (JIT) et les appels tail JIT.</span><span class="sxs-lookup"><span data-stu-id="302fa-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="302fa-128">Événements d’interopérabilité</span><span class="sxs-lookup"><span data-stu-id="302fa-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="302fa-129">Capture des informations sur la mise en cache et la génération du stub MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="302fa-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="302fa-130">Événements ARM</span><span class="sxs-lookup"><span data-stu-id="302fa-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="302fa-131">Capture des informations de diagnostic détaillées sur l’état d’un domaine d’application.</span><span class="sxs-lookup"><span data-stu-id="302fa-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="302fa-132">Événements de sécurité</span><span class="sxs-lookup"><span data-stu-id="302fa-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="302fa-133">Capture des informations sur la vérification de nom fort et la vérification Authenticode.</span><span class="sxs-lookup"><span data-stu-id="302fa-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="302fa-134">Événement de pile</span><span class="sxs-lookup"><span data-stu-id="302fa-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="302fa-135">Capture des informations utilisées avec d’autres événements pour générer des traces de pile après le déclenchement d’un événement.</span><span class="sxs-lookup"><span data-stu-id="302fa-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302fa-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="302fa-136">See also</span></span>

- [<span data-ttu-id="302fa-137">Améliorer le débogage et l’optimisation des performances avec ETW</span><span class="sxs-lookup"><span data-stu-id="302fa-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://go.microsoft.com/fwlink/?LinkId=179696)
- [<span data-ttu-id="302fa-138">Blog des performances de Windows</span><span class="sxs-lookup"><span data-stu-id="302fa-138">Windows Performance Blog</span></span>](https://go.microsoft.com/fwlink/?LinkId=179509)
- [<span data-ttu-id="302fa-139">Contrôle de l'enregistrement .NET Framework</span><span class="sxs-lookup"><span data-stu-id="302fa-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)
- [<span data-ttu-id="302fa-140">Fournisseurs ETW du CLR</span><span class="sxs-lookup"><span data-stu-id="302fa-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)
- [<span data-ttu-id="302fa-141">Niveaux et mots clés ETW du CLR</span><span class="sxs-lookup"><span data-stu-id="302fa-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="302fa-142">Événements ETW dans le Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="302fa-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)

---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 572e458f08c4717207667db9940296c4a957199a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225493"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="f408c-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="f408c-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="f408c-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="f408c-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f408c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f408c-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f408c-105">Méthodes</span><span class="sxs-lookup"><span data-stu-id="f408c-105">Methods</span></span>  
 <span data-ttu-id="f408c-106">La classe ServiceThrottlingBehavior ne définit pas de méthode.</span><span class="sxs-lookup"><span data-stu-id="f408c-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f408c-107">Properties</span><span class="sxs-lookup"><span data-stu-id="f408c-107">Properties</span></span>  
 <span data-ttu-id="f408c-108">La classe ServiceThrottlingBehavior a les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="f408c-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="f408c-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="f408c-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="f408c-110">Type de données : sint32</span><span class="sxs-lookup"><span data-stu-id="f408c-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f408c-111">Type d’accès : Propriétés en lecture seule</span><span class="sxs-lookup"><span data-stu-id="f408c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f408c-112">Nombre maximal de messages en cours de traitement actif sur tous les objets de répartiteur dans un ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="f408c-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="f408c-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="f408c-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="f408c-114">Type de données : sint32</span><span class="sxs-lookup"><span data-stu-id="f408c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f408c-115">Type d’accès : Propriétés en lecture seule</span><span class="sxs-lookup"><span data-stu-id="f408c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f408c-116">Nombre maximal d'objets de service simultanément exécutables.</span><span class="sxs-lookup"><span data-stu-id="f408c-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="f408c-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="f408c-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="f408c-118">Type de données : sint32</span><span class="sxs-lookup"><span data-stu-id="f408c-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f408c-119">Type d’accès : Propriétés en lecture seule</span><span class="sxs-lookup"><span data-stu-id="f408c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f408c-120">Nombre maximal de sessions qu'un hôte peut accepter à la fois.</span><span class="sxs-lookup"><span data-stu-id="f408c-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f408c-121">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="f408c-121">Requirements</span></span>  
  
|<span data-ttu-id="f408c-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f408c-122">MOF</span></span>|<span data-ttu-id="f408c-123">Déclaré dans Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f408c-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f408c-124">Espace de noms</span><span class="sxs-lookup"><span data-stu-id="f408c-124">Namespace</span></span>|<span data-ttu-id="f408c-125">Défini dans root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f408c-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f408c-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f408c-126">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>

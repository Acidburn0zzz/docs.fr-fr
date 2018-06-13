---
title: Nombre d'appels ayant échoué par seconde
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 19f09b2a2132cab56da5dec49bdc8d5f5e4c8b8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474452"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="b4215-102">Nombre d'appels ayant échoué par seconde</span><span class="sxs-lookup"><span data-stu-id="b4215-102">Calls Failed Per Second</span></span>
<span data-ttu-id="b4215-103">Nom du compteur : appels ayant échoué par seconde</span><span class="sxs-lookup"><span data-stu-id="b4215-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4215-104">Description</span><span class="sxs-lookup"><span data-stu-id="b4215-104">Description</span></span>  
 <span data-ttu-id="b4215-105">Nombre d'appels à cette opération avec des exceptions non prises en charge par seconde.</span><span class="sxs-lookup"><span data-stu-id="b4215-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="b4215-106">Ce compteur est de type de compteur de performances [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dont la valeur est calculée à l’aide de la formule suivante.</span><span class="sxs-lookup"><span data-stu-id="b4215-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b4215-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b4215-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="b4215-108">Ce compteur est incrémenté à chaque exception non prise en charge dans cette opération.</span><span class="sxs-lookup"><span data-stu-id="b4215-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4215-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4215-109">See Also</span></span>  
 [<span data-ttu-id="b4215-110">Spécification et gestion des erreurs dans les contrats et les services</span><span class="sxs-lookup"><span data-stu-id="b4215-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)

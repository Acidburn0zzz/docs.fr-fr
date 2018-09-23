---
title: Appels de sécurité non autorisés par seconde
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4970c6f6552163114b33a34ae87c6ed56b5e13
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703458"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="f8b0c-102">Appels de sécurité non autorisés par seconde</span><span class="sxs-lookup"><span data-stu-id="f8b0c-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="f8b0c-103">Nom du compteur : Appels de sécurité non autorisés par seconde.</span><span class="sxs-lookup"><span data-stu-id="f8b0c-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f8b0c-104">Description</span><span class="sxs-lookup"><span data-stu-id="f8b0c-104">Description</span></span>  
 <span data-ttu-id="f8b0c-105">Nombre d'appels dont l'autorisation a échoué lors de cette opération en une seconde.</span><span class="sxs-lookup"><span data-stu-id="f8b0c-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="f8b0c-106">Ce compteur est incrémenté lorsque la méthode <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> retourne la valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="f8b0c-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="f8b0c-107">Il indique que le message entrant provient d’un utilisateur valide et qu’il est correctement protégé, mais que l’utilisateur n’est pas autorisé à exécuter des tâches spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f8b0c-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="f8b0c-108">Ce compteur est de type de compteur de performances [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dont la valeur est calculée à l’aide de la formule suivante.</span><span class="sxs-lookup"><span data-stu-id="f8b0c-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f8b0c-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f8b0c-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>

---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: a7f353b00796c845f5686ca2926bbe7effe09e3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33480582"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="f9670-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="f9670-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="f9670-103">Le module PeerMaintainer exécute une opération spécifique (informations détaillées dans le corps du message de suivi).</span><span class="sxs-lookup"><span data-stu-id="f9670-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="f9670-104">Description</span><span class="sxs-lookup"><span data-stu-id="f9670-104">Description</span></span>  
 <span data-ttu-id="f9670-105">Ce suivi se produit pendant différentes opérations PeerMaintainer.</span><span class="sxs-lookup"><span data-stu-id="f9670-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="f9670-106">PeerMaintainer est un composant interne de PeerNode.</span><span class="sxs-lookup"><span data-stu-id="f9670-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="f9670-107">Chaque minute, ou tous les 32 messages reçus, il envoie un message LinkUtility à ses voisins contenant les statistiques relatives au nombre de messages échangés et utiles (autres que des doublons, non falsifiés).</span><span class="sxs-lookup"><span data-stu-id="f9670-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="f9670-108">Cela aide à déterminer l'utilité d'une liaison avec un voisin particulier.</span><span class="sxs-lookup"><span data-stu-id="f9670-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="f9670-109">Environ toutes les cinq minutes, Peer Maintainer vérifie l'état des connexions avec les voisins.</span><span class="sxs-lookup"><span data-stu-id="f9670-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="f9670-110">Si le nombre de ces connexions est supérieur à la valeur idéale, Peer Maintainer supprime les connexions les moins utiles.</span><span class="sxs-lookup"><span data-stu-id="f9670-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="f9670-111">Si le nombre de connexions n'est pas suffisant, l'application en acquiert de nouvelles.</span><span class="sxs-lookup"><span data-stu-id="f9670-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9670-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9670-112">See Also</span></span>  
 [<span data-ttu-id="f9670-113">Suivi</span><span class="sxs-lookup"><span data-stu-id="f9670-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f9670-114">Utilisation du suivi pour résoudre les problèmes posés par votre application</span><span class="sxs-lookup"><span data-stu-id="f9670-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f9670-115">Administration et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f9670-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)

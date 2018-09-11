---
title: Nombre d’échecs de validation de la sécurité et d’authentification par seconde
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4836a5076401de2f7c3112b298cdadc0e0307962
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261835"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="cf2a1-102">Nombre d’échecs de validation de la sécurité et d’authentification par seconde</span><span class="sxs-lookup"><span data-stu-id="cf2a1-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="cf2a1-103">Nom du compteur : nombre d’échecs de la validation de la sécurité et de l’authentification par seconde.</span><span class="sxs-lookup"><span data-stu-id="cf2a1-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cf2a1-104">Description</span><span class="sxs-lookup"><span data-stu-id="cf2a1-104">Description</span></span>  
 <span data-ttu-id="cf2a1-105">Ce compteur est incrémenté chaque fois qu'un message est rejeté en raison d'un problème de sécurité non couvert par le compteur « Appels de sécurité non autorisés ».</span><span class="sxs-lookup"><span data-stu-id="cf2a1-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="cf2a1-106">Ces problèmes sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="cf2a1-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="cf2a1-107">Impossibilité de lire le jeton client depuis le message.</span><span class="sxs-lookup"><span data-stu-id="cf2a1-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="cf2a1-108">Échec de l'authentification du jeton client (par exemple, mot de passe incorrect).</span><span class="sxs-lookup"><span data-stu-id="cf2a1-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="cf2a1-109">Échec de la vérification de signature (par exemple, falsification du message).</span><span class="sxs-lookup"><span data-stu-id="cf2a1-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="cf2a1-110">Le message est un doublon d'un message précédent, ce qui peut se produire lors d'une attaque par relecture.</span><span class="sxs-lookup"><span data-stu-id="cf2a1-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="cf2a1-111">Impossibilité de déchiffrer le message.</span><span class="sxs-lookup"><span data-stu-id="cf2a1-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="cf2a1-112">Absence de certains éléments requis dans le message (par exemple, horodatage ou bloc des données chiffrées manquant).</span><span class="sxs-lookup"><span data-stu-id="cf2a1-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="cf2a1-113">Erreurs lors de la négociation TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="cf2a1-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="cf2a1-114">Ce compteur est de type de compteur de performances [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dont la valeur est calculée à l’aide de la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="cf2a1-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="cf2a1-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="cf2a1-115">(N1-N0)/((D1-D0)/F)</span></span>

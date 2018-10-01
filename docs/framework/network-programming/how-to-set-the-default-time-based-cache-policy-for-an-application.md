---
title: 'Comment : définir la stratégie de cache à durée définie par défaut pour une application'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1e08026f8d1ec8b39f7ef3c2c34efad9e51b8fe9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2018
ms.locfileid: "47235700"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="97b70-102">Comment : définir la stratégie de cache à durée définie par défaut pour une application</span><span class="sxs-lookup"><span data-stu-id="97b70-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="97b70-103">Avec la stratégie de cache basée sur la durée par défaut, le comportement de cache d’une application est déterminé par les en-têtes envoyés avec la ressource en cache et par le comportement du cache défini dans les sections 13 et 14 du document RFC 2616, disponible à l’adresse [http://www.ietf.org](http://www.ietf.org/). Ce comportement de cache convient à la plupart des applications.</span><span class="sxs-lookup"><span data-stu-id="97b70-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/). This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="97b70-104">Pour utiliser automatiquement la stratégie par défaut pour une application</span><span class="sxs-lookup"><span data-stu-id="97b70-104">To set the default automatic policy for an application</span></span>  
  
1.  <span data-ttu-id="97b70-105">Créez une stratégie basée sur la durée par défaut.</span><span class="sxs-lookup"><span data-stu-id="97b70-105">Create a default time-based policy object.</span></span>  
  
2.  <span data-ttu-id="97b70-106">Définissez cette stratégie comme stratégie par défaut pour le domaine d’application.</span><span class="sxs-lookup"><span data-stu-id="97b70-106">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97b70-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="97b70-107">Example</span></span>  
 <span data-ttu-id="97b70-108">Les deux exemples de cette section créent des stratégies identiques.</span><span class="sxs-lookup"><span data-stu-id="97b70-108">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="97b70-109">L’exemple suivant crée une stratégie basée sur la durée par défaut et la définit comme stratégie par défaut pour le domaine d’application.</span><span class="sxs-lookup"><span data-stu-id="97b70-109">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 <span data-ttu-id="97b70-110">Vous pouvez également créer une stratégie de cache basée sur la durée par défaut à l’aide la classe <xref:System.Net.Cache.RequestCachePolicy>, comme indiqué dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="97b70-110">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="97b70-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97b70-111">See Also</span></span>  
 [<span data-ttu-id="97b70-112">Gestion du cache pour les applications réseau</span><span class="sxs-lookup"><span data-stu-id="97b70-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="97b70-113">Stratégie de cache</span><span class="sxs-lookup"><span data-stu-id="97b70-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="97b70-114">Stratégies de cache basées sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="97b70-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="97b70-115">Stratégies de cache basées sur la durée</span><span class="sxs-lookup"><span data-stu-id="97b70-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="97b70-116">\<requestCaching>, élément (paramètres réseau)</span><span class="sxs-lookup"><span data-stu-id="97b70-116">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)

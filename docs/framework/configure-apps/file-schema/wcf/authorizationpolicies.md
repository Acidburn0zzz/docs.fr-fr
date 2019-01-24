---
title: '&lt;authorizationPolicies&gt;'
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 7648c221a61efb99b4dc486f9b4d121439632c63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519552"
---
# <a name="ltauthorizationpoliciesgt"></a><span data-ttu-id="33ff4-102">&lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="33ff4-102">&lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="33ff4-103">Cette section de configuration contient une collection des types de stratégie d’autorisation, qui peuvent être ajoutés à l’aide du mot clé `add`.</span><span class="sxs-lookup"><span data-stu-id="33ff4-103">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="33ff4-104">Chaque stratégie d'autorisation contient un attribut `policyType` requis unique qui est une chaîne.</span><span class="sxs-lookup"><span data-stu-id="33ff4-104">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="33ff4-105">L'attribut spécifie une stratégie d'autorisation, qui active la transformation d'un jeu de revendications d'entrée dans un autre jeu de revendications.</span><span class="sxs-lookup"><span data-stu-id="33ff4-105">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="33ff4-106">Le contrôle d'accès peut être accordé ou refusé en fonction de cette opération.</span><span class="sxs-lookup"><span data-stu-id="33ff4-106">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="33ff4-107">Pour plus d’informations sur le fonctionne d’une stratégie d’autorisation, consultez <xref:System.IdentityModel.Policy.IAuthorizationPolicy> et [stratégie d’autorisation](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="33ff4-107">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ff4-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33ff4-108">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="33ff4-109">Autorisation de l’accès aux opérations de service</span><span class="sxs-lookup"><span data-stu-id="33ff4-109">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="33ff4-110">Guide pratique pour Créer un gestionnaire d’autorisation personnalisé pour un Service</span><span class="sxs-lookup"><span data-stu-id="33ff4-110">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="33ff4-111">\<add></span><span class="sxs-lookup"><span data-stu-id="33ff4-111">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="33ff4-112">Stratégie d’autorisation</span><span class="sxs-lookup"><span data-stu-id="33ff4-112">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

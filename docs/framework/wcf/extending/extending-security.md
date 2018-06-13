---
title: Extension de la sécurité
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94aefe80674c5b4ec6fcce6a41d9b68e093f4262
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809399"
---
# <a name="extending-security"></a><span data-ttu-id="67352-102">Extension de la sécurité</span><span class="sxs-lookup"><span data-stu-id="67352-102">Extending Security</span></span>
<span data-ttu-id="67352-103">Pour prendre en compte les nouveaux types de revendications et jetons personnalisés, vous pouvez étendre l’infrastructure de sécurité de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="67352-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="67352-104">Les rubriques de cette section vous montrent comment procéder.</span><span class="sxs-lookup"><span data-stu-id="67352-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67352-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="67352-105">In This Section</span></span>  
 [<span data-ttu-id="67352-106">Architecture de sécurité</span><span class="sxs-lookup"><span data-stu-id="67352-106">Security Architecture</span></span>](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="67352-107">Décrit l’architecture du système de sécurité WCF.</span><span class="sxs-lookup"><span data-stu-id="67352-107">Walks through the architecture of the WCF security system.</span></span>  
  
 [<span data-ttu-id="67352-108">Informations d’identification personnalisées et validation d’informations d’identification</span><span class="sxs-lookup"><span data-stu-id="67352-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="67352-109">Explique comment le modèle d'identité est utilisé lors de la validation d'informations d'identification personnalisées.</span><span class="sxs-lookup"><span data-stu-id="67352-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="67352-110">Jetons personnalisés</span><span class="sxs-lookup"><span data-stu-id="67352-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="67352-111">Les jetons émis par un service de jeton de sécurité sont en général des jetons SAML.</span><span class="sxs-lookup"><span data-stu-id="67352-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="67352-112">Cette rubrique explique comment créer un type de jeton personnalisé.</span><span class="sxs-lookup"><span data-stu-id="67352-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="67352-113">Autorisation personnalisée</span><span class="sxs-lookup"><span data-stu-id="67352-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="67352-114">Explique comment implémenter une autorisation personnalisée.</span><span class="sxs-lookup"><span data-stu-id="67352-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="67352-115">Substitution de l’identité d’un service pour l’authentification</span><span class="sxs-lookup"><span data-stu-id="67352-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="67352-116">Décrit comment remplacer l'identité d'un service pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="67352-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="67352-117">Guide pratique pour créer un vérificateur d’identité du client personnalisé</span><span class="sxs-lookup"><span data-stu-id="67352-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="67352-118">Montre comment valider une identité de point de terminaison personnalisée.</span><span class="sxs-lookup"><span data-stu-id="67352-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="67352-119">Guide pratique pour utiliser des certificats X.509 distincts pour les signatures et le chiffrement</span><span class="sxs-lookup"><span data-stu-id="67352-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="67352-120">Les messages sont généralement signés et chiffrés à l'aide d'un certificat unique.</span><span class="sxs-lookup"><span data-stu-id="67352-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="67352-121">Cette rubrique explique comment deux certificats peuvent être utilisés, s'ils sont requis.</span><span class="sxs-lookup"><span data-stu-id="67352-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="67352-122">Guide pratique pour remplacer le fournisseur de services de chiffrement par la clé privée d’un certificat X.509</span><span class="sxs-lookup"><span data-stu-id="67352-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="67352-123">Explique comment modifier le fournisseur de services de chiffrement utilisé pour fournir la clé privée d’un certificat X.509 et comment intégrer le fournisseur dans le cadre de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="67352-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="67352-124">Référence</span><span class="sxs-lookup"><span data-stu-id="67352-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="67352-125">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="67352-125">Related Sections</span></span>  
 [<span data-ttu-id="67352-126">Sécurité</span><span class="sxs-lookup"><span data-stu-id="67352-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="67352-127">Programmation WCF de base</span><span class="sxs-lookup"><span data-stu-id="67352-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="67352-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67352-128">See Also</span></span>  
 [<span data-ttu-id="67352-129">Vue d’ensemble de la sécurité</span><span class="sxs-lookup"><span data-stu-id="67352-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)

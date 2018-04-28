---
title: "Comment : créer un contrat Windows Communication Foundation à l'aide d'une classe"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e1a66dd00592e24fd505cb1956b04d2856bf96a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="3cf65-102">Comment : créer un contrat Windows Communication Foundation à l'aide d'une classe</span><span class="sxs-lookup"><span data-stu-id="3cf65-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="3cf65-103">La méthode préconisée pour créer un contrat [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] consiste à utiliser une interface.</span><span class="sxs-lookup"><span data-stu-id="3cf65-103">The preferred way of creating a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="3cf65-104">Pour plus d’informations, consultez [Comment : définir un contrat de Service](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="3cf65-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="3cf65-105">Une autre solution, présentée dans cette rubrique, consiste à créer une classe, à appliquer l'attribut <xref:System.ServiceModel.ServiceContractAttribute> directement sur celle-ci, puis l'attribut <xref:System.ServiceModel.OperationContractAttribute> sur chacune des méthodes de la classe qui font partie du contrat.</span><span class="sxs-lookup"><span data-stu-id="3cf65-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3cf65-106">`[ServiceContract]` et `[ServiceContractAttribute]` produisent le même résultat.</span><span class="sxs-lookup"><span data-stu-id="3cf65-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="3cf65-107">La même chose est vraie pour `[OperationContract]` et `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="3cf65-107">The same thing it true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="3cf65-108">Dans chaque cas le précédent est abrégé pour le dernier.</span><span class="sxs-lookup"><span data-stu-id="3cf65-108">In each case the former is shorthand for the latter.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="3cf65-109"> contrats de service, consultez [concevoir des contrats de Service](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="3cf65-109"> service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="3cf65-110">Création d'un contrat Windows Communication Foundation à l'aide d'une classe</span><span class="sxs-lookup"><span data-stu-id="3cf65-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="3cf65-111">Créer une nouvelle classe à l’aide de Visual Basic, c# ou tout autre langage common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3cf65-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="3cf65-112">Appliquez la classe <xref:System.ServiceModel.ServiceContractAttribute> à la classe.</span><span class="sxs-lookup"><span data-stu-id="3cf65-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="3cf65-113">Créez des méthodes dans la classe.</span><span class="sxs-lookup"><span data-stu-id="3cf65-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="3cf65-114">Appliquez la classe <xref:System.ServiceModel.OperationContractAttribute> à chaque méthode qui doit être exposée dans le cadre du contrat public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cf65-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cf65-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="3cf65-115">Example</span></span>  
 <span data-ttu-id="3cf65-116">L'exemple de code suivant présente une classe qui définit un contrat de service.</span><span class="sxs-lookup"><span data-stu-id="3cf65-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="3cf65-117">Les méthodes auxquelles la classe <xref:System.ServiceModel.OperationContractAttribute> est appliquée utilisent un modèle de message demande-réponse par défaut.</span><span class="sxs-lookup"><span data-stu-id="3cf65-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="3cf65-118"> Ce modèle de message, consultez [Comment : créer un contrat demande-réponse](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="3cf65-118"> this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="3cf65-119">Vous pouvez également créer et utiliser d’autres modèles de message en définissant les propriétés de l’attribut.</span><span class="sxs-lookup"><span data-stu-id="3cf65-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="3cf65-120">Pour plus d’exemples, consultez [Comment : créer un contrat unidirectionnel](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) et [Comment : créer un contrat Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="3cf65-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf65-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3cf65-121">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>

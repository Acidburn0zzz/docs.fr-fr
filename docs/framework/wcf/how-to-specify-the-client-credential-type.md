---
title: "Comment : spécifier le type d'informations d'identification du client"
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
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 50455770f0e94df5994d0a7ecbe2bf13bc43cf38
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="2f83b-102">Comment : spécifier le type d'informations d'identification du client</span><span class="sxs-lookup"><span data-stu-id="2f83b-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="2f83b-103">Après avoir défini un mode de sécurité (transport ou message), vous avez pouvez définir le type d'informations d'identification du client.</span><span class="sxs-lookup"><span data-stu-id="2f83b-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="2f83b-104">Cette propriété spécifie le type d'informations d'identification que le client doit fournir au service dans le cadre de l'authentification.</span><span class="sxs-lookup"><span data-stu-id="2f83b-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="2f83b-105">Pour plus d’informations sur la définition du mode de sécurité (étape nécessaire avant de définir le type d’informations d’identification du client), consultez [Comment : définir le Mode de sécurité](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="2f83b-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="2f83b-106">Pour définir le type d'informations d'identification du client dans le code</span><span class="sxs-lookup"><span data-stu-id="2f83b-106">To set the client credential type in code</span></span>  
  
1.  <span data-ttu-id="2f83b-107">Créez une instance de la liaison que le service utilisera.</span><span class="sxs-lookup"><span data-stu-id="2f83b-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="2f83b-108">Cet exemple utilise la liaison <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="2f83b-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2.  <span data-ttu-id="2f83b-109">Affectez à la propriété <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> une valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="2f83b-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="2f83b-110">Cet exemple utilise le mode de message.</span><span class="sxs-lookup"><span data-stu-id="2f83b-110">This example uses the Message mode.</span></span>  
  
3.  <span data-ttu-id="2f83b-111">Affectez à la propriété <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> une valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="2f83b-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="2f83b-112">Dans notre exemple, la propriété est définie de sorte à utiliser l'authentification Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="2f83b-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="2f83b-113">Pour définir le type d'informations d'identification du client dans la configuration</span><span class="sxs-lookup"><span data-stu-id="2f83b-113">To set the client credential type in configuration</span></span>  
  
1.  <span data-ttu-id="2f83b-114">Ajouter un [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) élément au fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="2f83b-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2.  <span data-ttu-id="2f83b-115">Comme un élément enfant, ajoutez un [ \<liaisons >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) élément.</span><span class="sxs-lookup"><span data-stu-id="2f83b-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3.  <span data-ttu-id="2f83b-116">Ajoutez une liaison appropriée.</span><span class="sxs-lookup"><span data-stu-id="2f83b-116">Add an appropriate binding.</span></span> <span data-ttu-id="2f83b-117">Cet exemple utilise le [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) élément.</span><span class="sxs-lookup"><span data-stu-id="2f83b-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4.  <span data-ttu-id="2f83b-118">Ajouter un [ \<liaison >](../../../docs/framework/misc/binding.md) et affectez le `name` attribut une valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="2f83b-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="2f83b-119">Cet exemple utilise le nom « SecureBinding ».</span><span class="sxs-lookup"><span data-stu-id="2f83b-119">This example uses the name "SecureBinding".</span></span>  
  
5.  <span data-ttu-id="2f83b-120">Ajoutez une liaison `<security>`.</span><span class="sxs-lookup"><span data-stu-id="2f83b-120">Add a `<security>` binding.</span></span> <span data-ttu-id="2f83b-121">Affectez la valeur appropriée à l'attribut `mode`.</span><span class="sxs-lookup"><span data-stu-id="2f83b-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="2f83b-122">Cet exemple lui affecte la valeur `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="2f83b-122">This example sets it to `"Message"`.</span></span>  
  
6.  <span data-ttu-id="2f83b-123">Ajoutez un élément `<message>` ou un élément `<transport>` comme requis par le mode de sécurité.</span><span class="sxs-lookup"><span data-stu-id="2f83b-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="2f83b-124">Affectez la valeur appropriée à l'attribut `clientCredentialType`.</span><span class="sxs-lookup"><span data-stu-id="2f83b-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="2f83b-125">Cet exemple utilise `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="2f83b-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2f83b-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f83b-126">See Also</span></span>  
 [<span data-ttu-id="2f83b-127">Sécurisation de services</span><span class="sxs-lookup"><span data-stu-id="2f83b-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="2f83b-128">Guide pratique pour définir le mode de sécurité</span><span class="sxs-lookup"><span data-stu-id="2f83b-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)

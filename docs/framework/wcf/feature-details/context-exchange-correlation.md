---
title: Corrélation d'échange de contexte
ms.date: 03/30/2017
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
ms.openlocfilehash: d9de111fa08b4a398bba52bc903ea1fec8c7f298
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483695"
---
# <a name="context-exchange-correlation"></a>Corrélation d'échange de contexte
Corrélation de contexte est basée sur le mécanisme d’échange de contexte décrit dans le [.NET Context Exchange Protocol Specification](https://go.microsoft.com/fwlink/?LinkId=166059). La corrélation de contexte utilise un en-tête ou un cookie de contexte bien connu pour lier les messages à l'instance correcte. Pour utiliser la corrélation de contexte, une liaison basée sur le contexte, telle que <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> ou <xref:System.ServiceModel.NetTcpContextBinding>, doit être utilisée sur le point de terminaison fourni à l'objet <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Cette rubrique explique comment utiliser la corrélation de contexte avec des activités de messagerie dans un service de workflow.  
  
## <a name="using-context-correlation"></a>Utilisation de la corrélation de contexte  
 La corrélation de contexte est utilisée lorsqu’un client doit faire des appels répétés dans un service de workflow et que le service est hébergé en utilisant l’une des liaisons de contexte. Ce type de corrélation est initialisé par une <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> paire dans le service de workflow. Le contexte est renvoyé au client avec la réponse, puis le client joint ce contexte dans les appels ultérieurs au service.  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a>Configuration de la corrélation de contexte dans un service de workflow  
 La corrélation de contexte est initialisée à l'aide d'un objet <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>, associé à l'activité <xref:System.ServiceModel.Activities.SendReply> qui répond au message entrant initial. Dans l'exemple suivant, l'activité <xref:System.ServiceModel.Activities.SendReply> est configurée pour initialiser une corrélation de contexte.  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  Dans cet exemple, deux types de correlation sont en fait utilisés : la corrélation de contexte et la corrélation demande-réponse. La corrélation de contexte est utilisée pour que les appels des clients soient acheminés à l'instance correcte. La corrélation demande-réponse est utilisée à la fois par les activités <xref:System.ServiceModel.Activities.Receive> et <xref:System.ServiceModel.Activities.SendReply> pour implémenter l'opération bidirectionnelle modelée par ces activités. Dans cet exemple, uniquement la corrélation de contexte est explicitement configurée et le <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> paire est à l’aide de la corrélation demande-réponse par défaut qui est fournie par le caractère implicite <xref:System.ServiceModel.Activities.CorrelationHandle> gestion de <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Lorsque vous utilisez le **ReceiveAndSendReply** modèle d’activité dans le Concepteur de workflow, demande-réponse corrélation est explicitement configuré. Pour plus d’informations sur la corrélation demande-réponse et la gestion de handle de corrélation implicite, consultez [demande-réponse](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) et [vue d’ensemble de corrélations](../../../../docs/framework/wcf/feature-details/correlation-overview.md). Pour plus d’informations sur la **ReceiveAndSendReply** modèle d’activité, consultez [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).  
  
 Les activités <xref:System.ServiceModel.Activities.Receive> ultérieures dans le service de workflow peuvent référencer le <xref:System.ServiceModel.Activities.CorrelationHandle> initialisé par l'activité <xref:System.ServiceModel.Activities.SendReply> dans l'exemple précédent.  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 Le point de terminaison est ensuite configuré sur le <xref:System.ServiceModel.Activities.WorkflowServiceHost> pour utiliser une liaison basée sur le contexte, telle que <xref:System.ServiceModel.BasicHttpContextBinding>.  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a>Configuration de la corrélation de contexte dans un client workflow  
 Lorsque le client est un autre workflow, la corrélation de contexte doit être également configurée sur le client. Sur le flux de travail client, le <xref:System.ServiceModel.Activities.ReceiveReply> de la <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> paire qui effectue l’appel initial au service de workflow doit être configuré avec un <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 Une fois la corrélation initialisée, les activités <xref:System.ServiceModel.Activities.Send> ultérieures peuvent utiliser le <xref:System.ServiceModel.Activities.CorrelationHandle> pour appeler les méthodes sur la même instance du service.  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 Notez que dans ces exemples, la corrélation de contexte a été configurée de manière explicite. Si le workflow client n'est pas également hébergé dans un <xref:System.ServiceModel.Activities.WorkflowServiceHost>, la corrélation doit être configurée de manière explicite, sauf si les activités sont contenues dans une activité <xref:System.ServiceModel.Activities.CorrelationScope>. Pour plus d’informations sur la corrélation de contexte, consultez le [NetContextExchangeCorrelation](https://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) exemple.  
  
 Si le client qui appelle le service de workflow n'est pas un workflow, il peut toujours répéter ses appels, à condition de retransmettre de manière explicite le contexte retourné par le premier appel au service de workflow. Les proxys générés en ajoutant une référence de service dans [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] stockent et transmettent ce contexte par défaut.

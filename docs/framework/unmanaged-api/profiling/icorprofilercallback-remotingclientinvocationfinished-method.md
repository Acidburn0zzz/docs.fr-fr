---
title: ICorProfilerCallback::RemotingClientInvocationFinished, méthode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec45b73b496efdbe6328985b5f77f731d8a78cc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>ICorProfilerCallback::RemotingClientInvocationFinished, méthode
Notifie le profileur qu’un appel de la communication à distance s’est exécutée entièrement sur le client.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Notes  
 Si l’appel de la communication à distance était synchrone, il s’est également exécutée entièrement sur le serveur. Si l’appel de la communication à distance était asynchrone, une réponse peut encore être attendue lorsque l’appel est géré. Si une réponse est attendue, elle se produit comme un appel à [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) et un appel supplémentaire à `RemotingClientInvocationFinished` pour indiquer le traitement secondaire requis d’un appel asynchrone.  
  
 Chacune des paires de rappels suivantes se produit sur le même thread :  
  
-   `RemotingClientInvocationStarted` et [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
-   [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) et [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
-   [ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) et [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 Vous devez être conscient des problèmes suivants avec les rappels de la communication à distance :  
  
-   Exécution d’une fonction de la communication à distance n’est pas reflétée par l’API de profileur, afin de notifications pour les fonctions qui sont appelées à partir du client et exécutées sur le serveur ne sont pas reçues correctement. L’appel réel se produit via un objet proxy ; pour le profileur, il apparaît que certaines fonctions sont compilées juste- mais jamais utilisé.  
  
-   Le profileur ne reçoit pas de notifications exactes pour les événements de la communication à distance asynchrone.  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorProf.idl, CorProf.h  
  
 **Bibliothèque :** CorGuids.lib  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [ICorProfilerCallback, interface](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)

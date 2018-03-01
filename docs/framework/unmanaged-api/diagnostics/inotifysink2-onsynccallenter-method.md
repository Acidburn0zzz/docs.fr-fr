---
title: "INotifySink2::OnSyncCallEnter, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 102a4a24b82c87bed00895dc723b7fca02c20bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="0f21c-102">INotifySink2::OnSyncCallEnter, méthode</span><span class="sxs-lookup"><span data-stu-id="0f21c-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="0f21c-103">Est appelé lors de la saisie d’un appel.</span><span class="sxs-lookup"><span data-stu-id="0f21c-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f21c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0f21c-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f21c-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="0f21c-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="0f21c-106">[in] ID de l’appel en cours de saisie.</span><span class="sxs-lookup"><span data-stu-id="0f21c-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="0f21c-107">Consultez [call_id, Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="0f21c-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="0f21c-108">[in] Mémoire tampon des appels.</span><span class="sxs-lookup"><span data-stu-id="0f21c-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="0f21c-109">[in] Taille de la mémoire tampon de l’appel, en octets.</span><span class="sxs-lookup"><span data-stu-id="0f21c-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f21c-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="0f21c-110">Return Value</span></span>  
 <span data-ttu-id="0f21c-111">S_OK si la méthode réussit.</span><span class="sxs-lookup"><span data-stu-id="0f21c-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f21c-112">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="0f21c-112">Requirements</span></span>  
 <span data-ttu-id="0f21c-113">**En-tête :** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0f21c-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f21c-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f21c-114">See Also</span></span>  
 [<span data-ttu-id="0f21c-115">INotifySink2, interface</span><span class="sxs-lookup"><span data-stu-id="0f21c-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="0f21c-116">INotifySource2, interface</span><span class="sxs-lookup"><span data-stu-id="0f21c-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="0f21c-117">INotifyConnection2, interface</span><span class="sxs-lookup"><span data-stu-id="0f21c-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)

---
title: INotifySink2::OnSyncCallExit, méthode
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fe2ebecdacd3b848d5de7eecca4753a89a58f35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432477"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="a7275-102">INotifySink2::OnSyncCallExit, méthode</span><span class="sxs-lookup"><span data-stu-id="a7275-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="a7275-103">Est appelé lors de la sortie d’un appel.</span><span class="sxs-lookup"><span data-stu-id="a7275-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7275-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a7275-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7275-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a7275-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="a7275-106">[in] ID de l’appel en cours s’est arrêté.</span><span class="sxs-lookup"><span data-stu-id="a7275-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="a7275-107">Consultez [call_id, Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="a7275-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="a7275-108">[out] Mémoire tampon des appels.</span><span class="sxs-lookup"><span data-stu-id="a7275-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="a7275-109">[out] Taille de la mémoire tampon de l’appel, en octets.</span><span class="sxs-lookup"><span data-stu-id="a7275-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7275-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="a7275-110">Return Value</span></span>  
 <span data-ttu-id="a7275-111">S_OK si la méthode réussit.</span><span class="sxs-lookup"><span data-stu-id="a7275-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7275-112">Spécifications</span><span class="sxs-lookup"><span data-stu-id="a7275-112">Requirements</span></span>  
 <span data-ttu-id="a7275-113">**En-tête :** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="a7275-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7275-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7275-114">See Also</span></span>  
 [<span data-ttu-id="a7275-115">INotifySink2, interface</span><span class="sxs-lookup"><span data-stu-id="a7275-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="a7275-116">INotifySource2, interface</span><span class="sxs-lookup"><span data-stu-id="a7275-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="a7275-117">INotifyConnection2, interface</span><span class="sxs-lookup"><span data-stu-id="a7275-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)

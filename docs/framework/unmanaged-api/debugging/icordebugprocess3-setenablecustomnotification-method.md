---
title: ICorDebugProcess3::SetEnableCustomNotification, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a84061cff7cc5dbdeba1e0e66396e04a8f345cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423154"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="02141-102">ICorDebugProcess3::SetEnableCustomNotification, méthode</span><span class="sxs-lookup"><span data-stu-id="02141-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="02141-103">Active ou désactive les notifications de débogueur personnalisées du type spécifié.</span><span class="sxs-lookup"><span data-stu-id="02141-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02141-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="02141-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02141-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="02141-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="02141-106">[in] Type qui spécifie les notifications de débogueur personnalisées.</span><span class="sxs-lookup"><span data-stu-id="02141-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="02141-107">[in] `true` pour activer les notifications de débogueur personnalisées ; `false` pour désactiver les notifications.</span><span class="sxs-lookup"><span data-stu-id="02141-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="02141-108">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="02141-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02141-109">Notes</span><span class="sxs-lookup"><span data-stu-id="02141-109">Remarks</span></span>  
 <span data-ttu-id="02141-110">Lorsque `fEnable` a la valeur `true`, les appels à la <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> déclencheur de la méthode un [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) rappel.</span><span class="sxs-lookup"><span data-stu-id="02141-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="02141-111">Les notifications sont désactivées par défaut. Par conséquent, le débogueur doit spécifier tous les types de notification qu’il connaît et souhaite gérer.</span><span class="sxs-lookup"><span data-stu-id="02141-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="02141-112">Étant donné que la [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) classe est délimitée par le domaine d’application, le débogueur doit appeler `SetEnableCustomNotification` pour chaque domaine d’application dans le processus s’il souhaite recevoir la notification de l’ensemble du processus.</span><span class="sxs-lookup"><span data-stu-id="02141-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="02141-113">En commençant par le [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], la seule notification prise en charge est une notification de dépendance inter-threads.</span><span class="sxs-lookup"><span data-stu-id="02141-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02141-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="02141-114">Requirements</span></span>  
 <span data-ttu-id="02141-115">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02141-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02141-116">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02141-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02141-117">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02141-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02141-118">**Versions du .NET framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02141-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02141-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02141-119">See Also</span></span>  
 [<span data-ttu-id="02141-120">ICorDebugProcess3, interface</span><span class="sxs-lookup"><span data-stu-id="02141-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [<span data-ttu-id="02141-121">Interfaces de débogage</span><span class="sxs-lookup"><span data-stu-id="02141-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="02141-122">Débogage</span><span class="sxs-lookup"><span data-stu-id="02141-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

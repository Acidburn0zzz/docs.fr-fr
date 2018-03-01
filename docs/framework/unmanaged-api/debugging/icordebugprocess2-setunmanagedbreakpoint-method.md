---
title: "ICorDebugProcess2::SetUnmanagedBreakpoint, méthode"
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
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 825917d48aaab5d9d5ce482fa600ca02efa158ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="8a3a7-102">ICorDebugProcess2::SetUnmanagedBreakpoint, méthode</span><span class="sxs-lookup"><span data-stu-id="8a3a7-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="8a3a7-103">Définit un point d’arrêt non managé à l’offset d’image native spécifié.</span><span class="sxs-lookup"><span data-stu-id="8a3a7-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3a7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8a3a7-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a3a7-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8a3a7-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="8a3a7-106">[in] A `CORDB_ADDRESS` objet qui spécifie le décalage de l’image native.</span><span class="sxs-lookup"><span data-stu-id="8a3a7-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="8a3a7-107">[in] La taille, en octets, de le `buffer` tableau.</span><span class="sxs-lookup"><span data-stu-id="8a3a7-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="8a3a7-108">[out] Tableau qui contient le code d’opération qui est remplacé par le point d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="8a3a7-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="8a3a7-109">[out] Un pointeur vers le nombre d’octets retournés dans le `buffer` tableau.</span><span class="sxs-lookup"><span data-stu-id="8a3a7-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a3a7-110">Notes</span><span class="sxs-lookup"><span data-stu-id="8a3a7-110">Remarks</span></span>  
 <span data-ttu-id="8a3a7-111">Si le décalage de l’image native est dans le common language runtime (CLR), le point d’arrêt sera ignoré.</span><span class="sxs-lookup"><span data-stu-id="8a3a7-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="8a3a7-112">Ainsi, le CLR afin d’éviter la distribution d’un point d’arrêt hors-bande, lorsque le point d’arrêt est défini par le débogueur.</span><span class="sxs-lookup"><span data-stu-id="8a3a7-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3a7-113">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="8a3a7-113">Requirements</span></span>  
 <span data-ttu-id="8a3a7-114">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a3a7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3a7-115">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a3a7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a3a7-116">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a3a7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a3a7-117">**Versions du .NET framework :**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3a7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

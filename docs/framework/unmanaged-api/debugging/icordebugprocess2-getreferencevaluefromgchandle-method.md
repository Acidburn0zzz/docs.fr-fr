---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle, méthode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60624a5f6323399d06bda4e0280de8fbe861bd9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419583"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="95d31-102">ICorDebugProcess2::GetReferenceValueFromGCHandle, méthode</span><span class="sxs-lookup"><span data-stu-id="95d31-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="95d31-103">Obtient un pointeur de référence à l’objet managé spécifié qui a un garbage collection à gérer.</span><span class="sxs-lookup"><span data-stu-id="95d31-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95d31-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="95d31-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95d31-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="95d31-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="95d31-106">[in] Pointeur vers un objet managé qui a un handle de garbage collection.</span><span class="sxs-lookup"><span data-stu-id="95d31-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="95d31-107">Cette valeur est un <xref:System.IntPtr> de l’objet et peuvent être récupérés à partir de la <xref:System.Runtime.InteropServices.GCHandle> pour l’objet managé.</span><span class="sxs-lookup"><span data-stu-id="95d31-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="95d31-108">[out] Pointeur vers l’adresse d’un objet ICorDebugReferenceValue qui représente une référence à l’objet managé spécifié.</span><span class="sxs-lookup"><span data-stu-id="95d31-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95d31-109">Notes</span><span class="sxs-lookup"><span data-stu-id="95d31-109">Remarks</span></span>  
 <span data-ttu-id="95d31-110">Ne confondez pas la valeur de référence retournée avec une valeur de référence de garbage collection.</span><span class="sxs-lookup"><span data-stu-id="95d31-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="95d31-111">La référence retournée se comporte comme une référence normale.</span><span class="sxs-lookup"><span data-stu-id="95d31-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="95d31-112">Il est désactivé lors de l’exécution de code se poursuit après un point d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="95d31-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="95d31-113">La durée de vie de l’objet cible n’est pas affectée par la durée de vie de la valeur de référence.</span><span class="sxs-lookup"><span data-stu-id="95d31-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95d31-114">Le `GetReferenceValueFromGCHandle` méthode ne valide pas le handle.</span><span class="sxs-lookup"><span data-stu-id="95d31-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="95d31-115">Par conséquent, le `GetReferenceValueFromGCHandle` méthode peut potentiellement endommager le débogueur et le code en cours de débogage si un handle non valide est passé.</span><span class="sxs-lookup"><span data-stu-id="95d31-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95d31-116">Spécifications</span><span class="sxs-lookup"><span data-stu-id="95d31-116">Requirements</span></span>  
 <span data-ttu-id="95d31-117">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95d31-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95d31-118">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95d31-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95d31-119">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95d31-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95d31-120">**Versions du .NET framework :** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95d31-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

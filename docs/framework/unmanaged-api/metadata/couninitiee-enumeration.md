---
title: "COUNINITIEE, énumération"
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
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 808320a2034011793429f1805edea82a52add23d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="5ba58-102">COUNINITIEE, énumération</span><span class="sxs-lookup"><span data-stu-id="5ba58-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="5ba58-103">Spécifie les constantes utilisées par [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) lors de l’initialisation du common language runtime.</span><span class="sxs-lookup"><span data-stu-id="5ba58-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ba58-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5ba58-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="5ba58-105">Membres</span><span class="sxs-lookup"><span data-stu-id="5ba58-105">Members</span></span>  
  
|<span data-ttu-id="5ba58-106">Membre</span><span class="sxs-lookup"><span data-stu-id="5ba58-106">Member</span></span>|<span data-ttu-id="5ba58-107">Description</span><span class="sxs-lookup"><span data-stu-id="5ba58-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="5ba58-108">Indique le mode de désinitialisation par défaut.</span><span class="sxs-lookup"><span data-stu-id="5ba58-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="5ba58-109">Indique le mode de désinitialisation pour décharger un assembly.</span><span class="sxs-lookup"><span data-stu-id="5ba58-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ba58-110">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="5ba58-110">Requirements</span></span>  
 <span data-ttu-id="5ba58-111">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ba58-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ba58-112">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ba58-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ba58-113">**Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ba58-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ba58-114">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ba58-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba58-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ba58-115">See Also</span></span>  
 [<span data-ttu-id="5ba58-116">Énumérations de métadonnées</span><span class="sxs-lookup"><span data-stu-id="5ba58-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

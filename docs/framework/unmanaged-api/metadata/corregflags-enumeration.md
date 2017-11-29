---
title: "CorRegFlags, énumération"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRegFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRegFlags
helpviewer_keywords: CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8118de9f4fc6a4f2820b88685b9b87c498328b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="67a6a-102">CorRegFlags, énumération</span><span class="sxs-lookup"><span data-stu-id="67a6a-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="67a6a-103">Fournit des valeurs d’indicateur utilisées pour l’inscription lors de l’installation d’un module ou une image composite.</span><span class="sxs-lookup"><span data-stu-id="67a6a-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a6a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="67a6a-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="67a6a-105">Membres</span><span class="sxs-lookup"><span data-stu-id="67a6a-105">Members</span></span>  
  
|<span data-ttu-id="67a6a-106">Membre</span><span class="sxs-lookup"><span data-stu-id="67a6a-106">Member</span></span>|<span data-ttu-id="67a6a-107">Description</span><span class="sxs-lookup"><span data-stu-id="67a6a-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="67a6a-108">Spécifie que les fichiers ne doivent pas être copiées dans la destination.</span><span class="sxs-lookup"><span data-stu-id="67a6a-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="67a6a-109">Spécifie que le module ou composite est une configuration.</span><span class="sxs-lookup"><span data-stu-id="67a6a-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="67a6a-110">Spécifie que le module ou composite a des références de classe.</span><span class="sxs-lookup"><span data-stu-id="67a6a-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67a6a-111">Spécifications</span><span class="sxs-lookup"><span data-stu-id="67a6a-111">Requirements</span></span>  
 <span data-ttu-id="67a6a-112">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67a6a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67a6a-113">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67a6a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67a6a-114">**Bibliothèque :** inclus en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67a6a-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67a6a-115">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67a6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a6a-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67a6a-116">See Also</span></span>  
 [<span data-ttu-id="67a6a-117">Énumérations de métadonnées</span><span class="sxs-lookup"><span data-stu-id="67a6a-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

---
title: CorLocalRefPreservation, énumération
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee808ba403a513b897134420b45ebe8cd3537571
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442243"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="2e7db-102">CorLocalRefPreservation, énumération</span><span class="sxs-lookup"><span data-stu-id="2e7db-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="2e7db-103">Contient des valeurs d'indicateur pour le traitement des références locales.</span><span class="sxs-lookup"><span data-stu-id="2e7db-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e7db-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2e7db-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="2e7db-105">Membres</span><span class="sxs-lookup"><span data-stu-id="2e7db-105">Members</span></span>  
  
|<span data-ttu-id="2e7db-106">Membre</span><span class="sxs-lookup"><span data-stu-id="2e7db-106">Member</span></span>|<span data-ttu-id="2e7db-107">Description</span><span class="sxs-lookup"><span data-stu-id="2e7db-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="2e7db-108">Ne conserver aucune référence locale.</span><span class="sxs-lookup"><span data-stu-id="2e7db-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="2e7db-109">Conserver les références de type local.</span><span class="sxs-lookup"><span data-stu-id="2e7db-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="2e7db-110">Conserver les références de membre locale.</span><span class="sxs-lookup"><span data-stu-id="2e7db-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e7db-111">Spécifications</span><span class="sxs-lookup"><span data-stu-id="2e7db-111">Requirements</span></span>  
 <span data-ttu-id="2e7db-112">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e7db-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e7db-113">**En-tête :** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2e7db-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2e7db-114">**Versions du .NET framework :** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e7db-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7db-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e7db-115">See Also</span></span>  
 [<span data-ttu-id="2e7db-116">Énumérations de métadonnées</span><span class="sxs-lookup"><span data-stu-id="2e7db-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

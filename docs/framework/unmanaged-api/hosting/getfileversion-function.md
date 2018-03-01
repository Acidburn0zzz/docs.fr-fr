---
title: GetFileVersion, fonction
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
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 43e7a1326cad1b831a88c7fc3877679b4c096709
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="getfileversion-function"></a><span data-ttu-id="23744-102">GetFileVersion, fonction</span><span class="sxs-lookup"><span data-stu-id="23744-102">GetFileVersion Function</span></span>
<span data-ttu-id="23744-103">Obtient les informations de version common language runtime (CLR) du fichier spécifié, à l’aide de la mémoire tampon spécifiée.</span><span class="sxs-lookup"><span data-stu-id="23744-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="23744-104">Cette fonction est déconseillée dans le [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23744-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23744-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="23744-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23744-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="23744-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="23744-107">[in] Le chemin d’accès du fichier doit être examinée.</span><span class="sxs-lookup"><span data-stu-id="23744-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="23744-108">[dans, out] La mémoire tampon allouée pour les informations de version qui sont retournées.</span><span class="sxs-lookup"><span data-stu-id="23744-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="23744-109">[in] La taille, en caractères larges, de `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="23744-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="23744-110">[out] La taille, en octets, de retourné `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="23744-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23744-111">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="23744-111">Requirements</span></span>  
 <span data-ttu-id="23744-112">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23744-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23744-113">**En-tête :** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23744-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23744-114">**Versions du .NET framework :**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23744-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23744-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23744-115">See Also</span></span>  
 [<span data-ttu-id="23744-116">Fonctions d’hébergement CLR dépréciées</span><span class="sxs-lookup"><span data-stu-id="23744-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

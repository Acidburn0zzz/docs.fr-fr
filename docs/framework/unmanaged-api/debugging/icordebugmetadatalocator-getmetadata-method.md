---
title: ICorDebugMetaDataLocator::GetMetaData, méthode
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4883ee56c7dd027f053dd072d7c8613f606ff2be
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/10/2018
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="a8ea9-102">ICorDebugMetaDataLocator::GetMetaData, méthode</span><span class="sxs-lookup"><span data-stu-id="a8ea9-102">ICorDebugMetaDataLocator::GetMetaData Method</span></span>
<span data-ttu-id="a8ea9-103">Indique au débogueur de retourner le chemin d’accès complet à un module dont les métadonnées sont nécessaires pour effectuer une opération demandée par le débogueur.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-103">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8ea9-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a8ea9-104">Syntax</span></span>  
  
```  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8ea9-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a8ea9-105">Parameters</span></span>  
 `wszImagePath`  
 <span data-ttu-id="a8ea9-106">[in] Chaîne terminée par le caractère null qui représente le chemin d’accès complet au fichier.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-106">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="a8ea9-107">Si le chemin d’accès complet n’est pas disponible, le nom et l’extension du fichier (*nom de fichier*. *extension*).</span><span class="sxs-lookup"><span data-stu-id="a8ea9-107">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="a8ea9-108">[in] Horodatage des en-têtes de fichier PE de l'image.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-108">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="a8ea9-109">Ce paramètre peut potentiellement être utilisé pour un serveur de symboles ([SymSrv](http://msdn.microsoft.com/library/cc266470.aspx)) recherche.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-109">This parameter can potentially be used for a symbol server ([SymSrv](http://msdn.microsoft.com/library/cc266470.aspx)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="a8ea9-110">[in] Taille d'image dans les en-têtes de fichier PE.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-110">[in] The image size from PE file headers.</span></span> <span data-ttu-id="a8ea9-111">Ce paramètre peut potentiellement être utilisé pour une recherche SymSrv.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-111">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="a8ea9-112">[in] Nombre de caractères dans `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-112">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="a8ea9-113">[out] Nombre de `WCHAR` écrits dans `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-113">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="a8ea9-114">Si la méthode retourne E_NOT_SUFFICIENT_BUFFER, contient le nombre de `WCHAR` nécessaires pour stocker le chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-114">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="a8ea9-115">[out] Pointeur vers une mémoire tampon dans laquelle le débogueur copie le chemin d’accès complet du fichier contenant les métadonnées demandées.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-115">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="a8ea9-116">Le `ofReadOnly` indicateur à partir de la [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) énumération est utilisée pour demander l’accès en lecture seule aux métadonnées dans ce fichier.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-116">The `ofReadOnly` flag from the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8ea9-117">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="a8ea9-117">Return Value</span></span>  
 <span data-ttu-id="a8ea9-118">Cette méthode retourne les HRESULT spécifiques suivants ainsi que les erreurs HRESULT indiquant l'échec de la méthode.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-118">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="a8ea9-119">Tous les autres HRESULT d'échec indiquent que le fichier n'est pas récupérable.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-119">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="a8ea9-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8ea9-120">HRESULT</span></span>|<span data-ttu-id="a8ea9-121">Description</span><span class="sxs-lookup"><span data-stu-id="a8ea9-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8ea9-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8ea9-122">S_OK</span></span>|<span data-ttu-id="a8ea9-123">La commande s'est correctement terminée.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-123">The method completed successfully.</span></span> <span data-ttu-id="a8ea9-124">`wszPathBuffer` contient le chemin d'accès complet au fichier et se termine par le caractère null.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-124">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="a8ea9-125">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a8ea9-125">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a8ea9-126">La taille actuelle de `wszPathBuffer` n'est pas suffisante pour contenir le chemin d'accès complet.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-126">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="a8ea9-127">Dans ce cas, `pcchPathBuffer` contient le nombre nécessaire de `WCHAR`, y compris le caractère null de fin, et la méthode `GetMetaData` est appelée une deuxième fois avec la taille de mémoire tampon demandée.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-127">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8ea9-128">Notes</span><span class="sxs-lookup"><span data-stu-id="a8ea9-128">Remarks</span></span>  
 <span data-ttu-id="a8ea9-129">Si `wszImagePath` contient le chemin d'accès complet d'un module dans un dump, il spécifie le chemin d'accès de l'ordinateur sur lequel le dump a été collecté.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-129">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="a8ea9-130">Le fichier n’existe peut-être pas à cet emplacement ou un fichier incorrect portant le même nom peut être stocké dans le chemin d’accès.</span><span class="sxs-lookup"><span data-stu-id="a8ea9-130">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8ea9-131">Spécifications</span><span class="sxs-lookup"><span data-stu-id="a8ea9-131">Requirements</span></span>  
 <span data-ttu-id="a8ea9-132">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8ea9-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ea9-133">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8ea9-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8ea9-134">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8ea9-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8ea9-135">**Versions du .NET framework :** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ea9-135">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ea9-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8ea9-136">See Also</span></span>  
 [<span data-ttu-id="a8ea9-137">ICorDebugThread4, interface</span><span class="sxs-lookup"><span data-stu-id="a8ea9-137">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="a8ea9-138">Interfaces de débogage</span><span class="sxs-lookup"><span data-stu-id="a8ea9-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a8ea9-139">Débogage</span><span class="sxs-lookup"><span data-stu-id="a8ea9-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

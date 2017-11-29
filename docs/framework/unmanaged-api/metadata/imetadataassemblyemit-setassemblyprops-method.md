---
title: "IMetaDataAssemblyEmit::SetAssemblyProps, méthode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2c9336855d706a9861d4e832e5f0234cdf04db7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="dbe7c-102">IMetaDataAssemblyEmit::SetAssemblyProps, méthode</span><span class="sxs-lookup"><span data-stu-id="dbe7c-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="dbe7c-103">Modifie la structure de métadonnées `Assembly` spécifiée.</span><span class="sxs-lookup"><span data-stu-id="dbe7c-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe7c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="dbe7c-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbe7c-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="dbe7c-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="dbe7c-106">[in] Le jeton de métadonnées qui spécifie le `Assembly` structure de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="dbe7c-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="dbe7c-107">[in] Pointeur vers la clé publique de l’éditeur de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="dbe7c-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="dbe7c-108">[in] La taille en octets de `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="dbe7c-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="dbe7c-109">[in] Identificateur de l’algorithme de hachage utilisé pour hacher les fichiers d’assembly.</span><span class="sxs-lookup"><span data-stu-id="dbe7c-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="dbe7c-110">[in] Nom de l’assembly du texte explicite.</span><span class="sxs-lookup"><span data-stu-id="dbe7c-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="dbe7c-111">[in] Pointeur vers le ASSEMBLYMETADATA qui contient des informations de version, la plateforme et paramètres régionaux de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="dbe7c-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="dbe7c-112">[in] Une combinaison d’opérations de [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) valeurs qui spécifient différents attributs de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="dbe7c-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbe7c-113">Remarques</span><span class="sxs-lookup"><span data-stu-id="dbe7c-113">Remarks</span></span>  
 <span data-ttu-id="dbe7c-114">Pour créer un `Assembly` structure des métadonnées, utilisez le [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) (méthode).</span><span class="sxs-lookup"><span data-stu-id="dbe7c-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe7c-115">Spécifications</span><span class="sxs-lookup"><span data-stu-id="dbe7c-115">Requirements</span></span>  
 <span data-ttu-id="dbe7c-116">**Plateforme :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbe7c-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe7c-117">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dbe7c-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dbe7c-118">**Bibliothèque :** utilisé en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dbe7c-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dbe7c-119">**Versions du .NET framework :**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe7c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe7c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbe7c-120">See Also</span></span>  
 [<span data-ttu-id="dbe7c-121">IMetaDataAssemblyEmit (Interface)</span><span class="sxs-lookup"><span data-stu-id="dbe7c-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)

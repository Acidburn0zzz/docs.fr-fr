---
title: IMetaDataTables::GetColumn, méthode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 850a97240e0a6450b4dec759a8786e0df5bffac8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448958"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="cfa03-102">IMetaDataTables::GetColumn, méthode</span><span class="sxs-lookup"><span data-stu-id="cfa03-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="cfa03-103">Obtient un pointeur vers la valeur contenue dans la cellule de la colonne spécifiée et la ligne dans la table donnée.</span><span class="sxs-lookup"><span data-stu-id="cfa03-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfa03-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cfa03-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cfa03-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="cfa03-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="cfa03-106">[in] L’index de la table.</span><span class="sxs-lookup"><span data-stu-id="cfa03-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="cfa03-107">[in] L’index de la colonne dans la table.</span><span class="sxs-lookup"><span data-stu-id="cfa03-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="cfa03-108">[in] L’index de la ligne dans la table.</span><span class="sxs-lookup"><span data-stu-id="cfa03-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="cfa03-109">[out] Pointeur vers la valeur dans la cellule.</span><span class="sxs-lookup"><span data-stu-id="cfa03-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfa03-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="cfa03-110">Requirements</span></span>  
 <span data-ttu-id="cfa03-111">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfa03-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfa03-112">**En-tête :** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cfa03-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cfa03-113">**Bibliothèque :** utilisé en tant que ressource dans MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cfa03-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cfa03-114">**Versions du .NET framework** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfa03-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfa03-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfa03-115">See Also</span></span>  
 [<span data-ttu-id="cfa03-116">IMetaDataTables, interface</span><span class="sxs-lookup"><span data-stu-id="cfa03-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="cfa03-117">IMetaDataTables2, interface</span><span class="sxs-lookup"><span data-stu-id="cfa03-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

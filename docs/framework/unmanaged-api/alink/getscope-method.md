---
title: GetScope Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetScope
api_location: alink.dll
api_type: COM
f1_keywords: GetScope
helpviewer_keywords: GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b3ebcb90142cc70a2d246d2e9ea6c42babe83b18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="getscope-method1"></a><span data-ttu-id="293d7-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="293d7-102">GetScope Method1</span></span>
<span data-ttu-id="293d7-103">Obtient une portée d’importation.</span><span class="sxs-lookup"><span data-stu-id="293d7-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="293d7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="293d7-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="293d7-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="293d7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="293d7-106">ID unique de l’assembly dans lequel importer.</span><span class="sxs-lookup"><span data-stu-id="293d7-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="293d7-107">ID unique du fichier à importer à partir de.</span><span class="sxs-lookup"><span data-stu-id="293d7-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="293d7-108">Portée de base zéro à importer.</span><span class="sxs-lookup"><span data-stu-id="293d7-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="293d7-109">Reçoit [IMetaDataImport (Interface)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface pour l’étendue.</span><span class="sxs-lookup"><span data-stu-id="293d7-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="293d7-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="293d7-110">Return Value</span></span>  
 <span data-ttu-id="293d7-111">Retourne S_OK si la méthode réussit.</span><span class="sxs-lookup"><span data-stu-id="293d7-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="293d7-112">Spécifications</span><span class="sxs-lookup"><span data-stu-id="293d7-112">Requirements</span></span>  
 <span data-ttu-id="293d7-113">Requiert alink.h</span><span class="sxs-lookup"><span data-stu-id="293d7-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="293d7-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="293d7-114">See Also</span></span>  
 [<span data-ttu-id="293d7-115">Interface IALink</span><span class="sxs-lookup"><span data-stu-id="293d7-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="293d7-116">IALink2 (Interface)</span><span class="sxs-lookup"><span data-stu-id="293d7-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="293d7-117">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="293d7-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

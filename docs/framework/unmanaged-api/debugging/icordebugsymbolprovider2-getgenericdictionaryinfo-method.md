---
title: Méthode ICorDebugSymbolProvider2::GetGenericDictionaryInfo
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c69be53a429e2f40741cc1e4c20fef3b7363654
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422973"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="82544-102">Méthode ICorDebugSymbolProvider2::GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="82544-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>
<span data-ttu-id="82544-103">Récupère un mappage de dictionnaire générique.</span><span class="sxs-lookup"><span data-stu-id="82544-103">Retrieves a generic dictionary map.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82544-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="82544-104">Syntax</span></span>  
  
```  
HRESULT GetGenericDictionaryInfo(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82544-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="82544-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="82544-106">[out] Un pointeur vers l’adresse d’un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) contenant le mappage de dictionnaire générique.</span><span class="sxs-lookup"><span data-stu-id="82544-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="82544-107">Pour plus d'informations, consultez la section Notes.</span><span class="sxs-lookup"><span data-stu-id="82544-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82544-108">Notes</span><span class="sxs-lookup"><span data-stu-id="82544-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82544-109">Cette méthode est uniquement disponible avec .NET Native.</span><span class="sxs-lookup"><span data-stu-id="82544-109">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="82544-110">Le mappage se compose de deux sections de niveau supérieur :</span><span class="sxs-lookup"><span data-stu-id="82544-110">The map consists of two top-level sections:</span></span>  
  
-   <span data-ttu-id="82544-111">A [répertoire](#Directory) contenant les adresses virtuelles relatives (RVA) de tous les dictionnaires inclus dans ce mappage.</span><span class="sxs-lookup"><span data-stu-id="82544-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>  
  
-   <span data-ttu-id="82544-112">Aligné sur un octet [tas](#Heap) qui contient des informations d’instanciation d’objet.</span><span class="sxs-lookup"><span data-stu-id="82544-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="82544-113">Il commence immédiatement après la dernière entrée du répertoire.</span><span class="sxs-lookup"><span data-stu-id="82544-113">It starts immediately after the last directory entry.</span></span>  
  
<a name="Directory"></a>   
## <a name="the-directory"></a><span data-ttu-id="82544-114">Répertoire</span><span class="sxs-lookup"><span data-stu-id="82544-114">The Directory</span></span>  
 <span data-ttu-id="82544-115">Chaque entrée du répertoire fait référence à un offset dans le tas, c'est-à-dire un offset par rapport au début du tas.</span><span class="sxs-lookup"><span data-stu-id="82544-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="82544-116">La valeur d'entrées individuelles n'est pas nécessairement unique : il est possible que plusieurs entrées de répertoire pointent vers le même offset dans le tas.</span><span class="sxs-lookup"><span data-stu-id="82544-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>  
  
 <span data-ttu-id="82544-117">La structure de la partie répertoire du mappage de dictionnaire générique est la suivante :</span><span class="sxs-lookup"><span data-stu-id="82544-117">The directory portion of the generic dictionary map has the following structure:</span></span>  
  
-   <span data-ttu-id="82544-118">Les 4 premiers octets contiennent le nombre d'entrées de dictionnaire (c'est-à-dire le nombre d'adresses virtuelles relatives dans le dictionnaire).</span><span class="sxs-lookup"><span data-stu-id="82544-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="82544-119">Nous appelons cette valeur en tant que *N*. Si le bit de poids fort est défini, les entrées sont triées par ordre croissant des adresses virtuelles relatives.</span><span class="sxs-lookup"><span data-stu-id="82544-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>  
  
-   <span data-ttu-id="82544-120">Le *N* suivent des entrées de répertoire.</span><span class="sxs-lookup"><span data-stu-id="82544-120">The *N* directory entries follow.</span></span> <span data-ttu-id="82544-121">Chaque entrée se compose de 8 octets dans deux segments de 4 octets :</span><span class="sxs-lookup"><span data-stu-id="82544-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>  
  
    -   <span data-ttu-id="82544-122">Octets 0-3 : adresse RVA (adresse virtuelle relative du dictionnaire)</span><span class="sxs-lookup"><span data-stu-id="82544-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>  
  
    -   <span data-ttu-id="82544-123">Octets 4-7 : offset (offset par rapport au début du tas)</span><span class="sxs-lookup"><span data-stu-id="82544-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>  
  
<a name="Heap"></a>   
## <a name="the-heap"></a><span data-ttu-id="82544-124">Tas</span><span class="sxs-lookup"><span data-stu-id="82544-124">The Heap</span></span>  
 <span data-ttu-id="82544-125">La taille du tas peut être calculée par un lecteur de flux en soustrayant la longueur du flux de la taille du répertoire + 4.</span><span class="sxs-lookup"><span data-stu-id="82544-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="82544-126">En d'autres termes :</span><span class="sxs-lookup"><span data-stu-id="82544-126">In other words:</span></span>  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 <span data-ttu-id="82544-127">où la taille du répertoire est `N * 8`.</span><span class="sxs-lookup"><span data-stu-id="82544-127">where the directory size is `N * 8`.</span></span>  
  
 <span data-ttu-id="82544-128">Le format de chaque élément d'informations d'instanciation sur le tas est le suivant :</span><span class="sxs-lookup"><span data-stu-id="82544-128">The format for each instantiation information item on the heap is:</span></span>  
  
-   <span data-ttu-id="82544-129">La longueur de cet élément d'informations d'instanciation en octets au format de métadonnées ECMA compressé.</span><span class="sxs-lookup"><span data-stu-id="82544-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="82544-130">La valeur exclut ces informations de longueur.</span><span class="sxs-lookup"><span data-stu-id="82544-130">The value excludes this length information.</span></span>  
  
-   <span data-ttu-id="82544-131">Le nombre de types d’instanciation générique, ou *T*, au format de métadonnées ECMA compressé.</span><span class="sxs-lookup"><span data-stu-id="82544-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>  
  
-   <span data-ttu-id="82544-132">*T* types, chacun représenté au format de signature de type ECMA.</span><span class="sxs-lookup"><span data-stu-id="82544-132">*T* types, each represented in ECMA type signature format.</span></span>  
  
 <span data-ttu-id="82544-133">L'inclusion de la longueur de chaque élément de tas permet d'effectuer un tri simple de la section répertoire sans affecter le tas.</span><span class="sxs-lookup"><span data-stu-id="82544-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82544-134">Spécifications</span><span class="sxs-lookup"><span data-stu-id="82544-134">Requirements</span></span>  
 <span data-ttu-id="82544-135">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82544-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82544-136">**En-tête :** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82544-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82544-137">**Bibliothèque :** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82544-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82544-138">**Versions du .NET framework :** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82544-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82544-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82544-139">See Also</span></span>  
 [<span data-ttu-id="82544-140">ICorDebugSymbolProvider2, interface</span><span class="sxs-lookup"><span data-stu-id="82544-140">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [<span data-ttu-id="82544-141">Interfaces de débogage</span><span class="sxs-lookup"><span data-stu-id="82544-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

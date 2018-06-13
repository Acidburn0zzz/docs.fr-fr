---
title: GetObjectText (fonction) (référence des API non managées)
description: La fonction GetObjectText retourne un rendu de texte d’un objet dans la syntaxe MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2f0e766a3a310bdb58f7cbffd8d49404eb5e0b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459637"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="419d3-103">GetObjectText (fonction)</span><span class="sxs-lookup"><span data-stu-id="419d3-103">GetObjectText function</span></span>
<span data-ttu-id="419d3-104">Retourne un rendu de texte de l’objet dans la syntaxe de Format MOF (Managed Object).</span><span class="sxs-lookup"><span data-stu-id="419d3-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="419d3-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="419d3-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="419d3-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="419d3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="419d3-107">[in] Ce paramètre est inutilisé.</span><span class="sxs-lookup"><span data-stu-id="419d3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="419d3-108">[in] Un pointeur vers un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span><span class="sxs-lookup"><span data-stu-id="419d3-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="419d3-109">[in] Normalement, 0.</span><span class="sxs-lookup"><span data-stu-id="419d3-109">[in] Normally 0.</span></span> <span data-ttu-id="419d3-110">Si `WBEM_FLAG_NO_FLAVORS` (ou 0 x 1) est spécifié, les qualificateurs sont incluses sans informations de propagation ou la version.</span><span class="sxs-lookup"><span data-stu-id="419d3-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="419d3-111">[out] Un pointeur vers un `null` sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="419d3-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="419d3-112">Moment du retour, qui vient d’être alloué `BSTR` qui contient un rendu de la syntaxe MOF de l’objet.</span><span class="sxs-lookup"><span data-stu-id="419d3-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="419d3-113">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="419d3-113">Return value</span></span>

<span data-ttu-id="419d3-114">Les valeurs suivantes est retournées par cette fonction sont définies dans le *WbemCli.h* fichier d’en-tête, ou vous pouvez les définir en tant que constantes dans votre code :</span><span class="sxs-lookup"><span data-stu-id="419d3-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="419d3-115">Constante</span><span class="sxs-lookup"><span data-stu-id="419d3-115">Constant</span></span>  |<span data-ttu-id="419d3-116">Value</span><span class="sxs-lookup"><span data-stu-id="419d3-116">Value</span></span>  |<span data-ttu-id="419d3-117">Description</span><span class="sxs-lookup"><span data-stu-id="419d3-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="419d3-118">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="419d3-118">0x80041001</span></span> | <span data-ttu-id="419d3-119">Il a été un échec général.</span><span class="sxs-lookup"><span data-stu-id="419d3-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="419d3-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="419d3-120">0x80041008</span></span> | <span data-ttu-id="419d3-121">Un paramètre n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="419d3-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="419d3-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="419d3-122">0x80041006</span></span> | <span data-ttu-id="419d3-123">Pas assez de mémoire est disponible pour terminer l’opération.</span><span class="sxs-lookup"><span data-stu-id="419d3-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="419d3-124">0</span><span class="sxs-lookup"><span data-stu-id="419d3-124">0</span></span> | <span data-ttu-id="419d3-125">L’appel de fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="419d3-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="419d3-126">Notes</span><span class="sxs-lookup"><span data-stu-id="419d3-126">Remarks</span></span>

<span data-ttu-id="419d3-127">Cette fonction encapsule un appel à la [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) (méthode).</span><span class="sxs-lookup"><span data-stu-id="419d3-127">This function wraps a call to the [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="419d3-128">Le texte de la structure MOF retourné ne contient pas toutes les informations sur l’objet, mais suffisamment d’informations pour le compilateur MOF être en mesure de recréer l’objet d’origine.</span><span class="sxs-lookup"><span data-stu-id="419d3-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="419d3-129">Par exemple, aucun qualificateurs propagés ou les propriétés de la classe parent ne sont incluses.</span><span class="sxs-lookup"><span data-stu-id="419d3-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="419d3-130">L’algorithme suivant est utilisé pour reconstruire le texte des paramètres d’une méthode :</span><span class="sxs-lookup"><span data-stu-id="419d3-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="419d3-131">Les paramètres sont resequenced dans l’ordre de leurs valeurs d’identificateur.</span><span class="sxs-lookup"><span data-stu-id="419d3-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="419d3-132">Les paramètres sont spécifiés en tant que `[in]` et `[out]` sont combinés en un seul paramètre.</span><span class="sxs-lookup"><span data-stu-id="419d3-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="419d3-133">`pstrObjectText` doit être un pointeur vers un `null` lorsque la fonction est appelée ; il ne doit pas pointer vers une chaîne qui est valide avant l’appel de méthode, car le pointeur n’est pas être libéré.</span><span class="sxs-lookup"><span data-stu-id="419d3-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="419d3-134">Spécifications</span><span class="sxs-lookup"><span data-stu-id="419d3-134">Requirements</span></span>  
<span data-ttu-id="419d3-135">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="419d3-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="419d3-136">**En-tête :** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="419d3-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="419d3-137">**Versions du .NET framework :** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="419d3-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419d3-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="419d3-138">See also</span></span>  
[<span data-ttu-id="419d3-139">WMI et les compteurs de Performance (référence des API non managées)</span><span class="sxs-lookup"><span data-stu-id="419d3-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

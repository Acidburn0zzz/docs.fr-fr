---
title: CompareTo (fonction) (référence des API non managées)
description: La fonction CompareTo compare un objet à un autre objet WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4431da90842f4f96a0f09a2f28dc473d956ee3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460406"
---
# <a name="compareto-function"></a><span data-ttu-id="b56b5-103">CompareTo (fonction)</span><span class="sxs-lookup"><span data-stu-id="b56b5-103">CompareTo function</span></span>
<span data-ttu-id="b56b5-104">Compare un objet à un autre objet de gestion de Windows.</span><span class="sxs-lookup"><span data-stu-id="b56b5-104">Compares an object to another Windows management object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b56b5-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b56b5-105">Syntax</span></span>  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a><span data-ttu-id="b56b5-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b56b5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b56b5-107">[in] Ce paramètre est inutilisé.</span><span class="sxs-lookup"><span data-stu-id="b56b5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b56b5-108">[in] Un pointeur vers un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span><span class="sxs-lookup"><span data-stu-id="b56b5-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`flags`  
<span data-ttu-id="b56b5-109">[in] Combinaison de bits des indicateurs qui spécifient les caractéristiques de l’objet à prendre en compte pour la comparaison.</span><span class="sxs-lookup"><span data-stu-id="b56b5-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="b56b5-110">Consultez le [notes](#remarks) section pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b56b5-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`  

<span data-ttu-id="b56b5-111">[in] L’objet de comparaison.</span><span class="sxs-lookup"><span data-stu-id="b56b5-111">[in] The object for comparison.</span></span> <span data-ttu-id="b56b5-112">`pcompareTo` doit être un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance ; elle ne peut pas être `null`.</span><span class="sxs-lookup"><span data-stu-id="b56b5-112">`pcompareTo` must be a valid [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b56b5-113">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="b56b5-113">Return value</span></span>

<span data-ttu-id="b56b5-114">Les valeurs suivantes est retournées par cette fonction sont définies dans le *WbemCli.h* fichier d’en-tête, ou vous pouvez les définir en tant que constantes dans votre code :</span><span class="sxs-lookup"><span data-stu-id="b56b5-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b56b5-115">Constante</span><span class="sxs-lookup"><span data-stu-id="b56b5-115">Constant</span></span>  |<span data-ttu-id="b56b5-116">Value</span><span class="sxs-lookup"><span data-stu-id="b56b5-116">Value</span></span>  |<span data-ttu-id="b56b5-117">Description</span><span class="sxs-lookup"><span data-stu-id="b56b5-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="b56b5-118">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="b56b5-118">0x80041001</span></span> | <span data-ttu-id="b56b5-119">Une erreur non spécifiée s’est produite.</span><span class="sxs-lookup"><span data-stu-id="b56b5-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b56b5-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="b56b5-120">0x80041008</span></span> | <span data-ttu-id="b56b5-121">Un paramètre n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="b56b5-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="b56b5-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="b56b5-122">0x8004101d</span></span> | <span data-ttu-id="b56b5-123">Un deuxième appel à `BeginEnumeration` a été effectuée sans appel intermédiaire à [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b56b5-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b56b5-124">0</span><span class="sxs-lookup"><span data-stu-id="b56b5-124">0</span></span> | <span data-ttu-id="b56b5-125">L’appel de fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="b56b5-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="b56b5-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="b56b5-126">0x40003</span></span> | <span data-ttu-id="b56b5-127">Les objets sont différents.</span><span class="sxs-lookup"><span data-stu-id="b56b5-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="b56b5-128">0</span><span class="sxs-lookup"><span data-stu-id="b56b5-128">0</span></span> | <span data-ttu-id="b56b5-129">Les objets sont identiques selon les indicateurs de comparaison.</span><span class="sxs-lookup"><span data-stu-id="b56b5-129">The objects are the same based on the comparison flags.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b56b5-130">Notes</span><span class="sxs-lookup"><span data-stu-id="b56b5-130">Remarks</span></span>

<span data-ttu-id="b56b5-131">Cette fonction encapsule un appel à la [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) (méthode).</span><span class="sxs-lookup"><span data-stu-id="b56b5-131">This function wraps a call to the [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b56b5-132">Les indicateurs qui peuvent être passés en tant que le `lEnumFlags` argument sont définies dans le *WbemCli.h* fichier d’en-tête, ou vous pouvez les définir en tant que constantes dans votre code.</span><span class="sxs-lookup"><span data-stu-id="b56b5-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="b56b5-133">Vous pouvez spécifier les caractéristiques individuelles impliquées dans la comparaison en spécifiant une combinaison au niveau du bit des indicateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="b56b5-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="b56b5-134">Constante</span><span class="sxs-lookup"><span data-stu-id="b56b5-134">Constant</span></span>  |<span data-ttu-id="b56b5-135">Value</span><span class="sxs-lookup"><span data-stu-id="b56b5-135">Value</span></span>  |<span data-ttu-id="b56b5-136">Description</span><span class="sxs-lookup"><span data-stu-id="b56b5-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="b56b5-137">2</span><span class="sxs-lookup"><span data-stu-id="b56b5-137">2</span></span> | <span data-ttu-id="b56b5-138">Ignorer la source (le serveur et l’espace de noms que dont elles proviennent).</span><span class="sxs-lookup"><span data-stu-id="b56b5-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="b56b5-139">1</span><span class="sxs-lookup"><span data-stu-id="b56b5-139">1</span></span> | <span data-ttu-id="b56b5-140">Ignorer tous les qualificateurs (y compris **clé** et **dynamique**)</span><span class="sxs-lookup"><span data-stu-id="b56b5-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="b56b5-141">4</span><span class="sxs-lookup"><span data-stu-id="b56b5-141">4</span></span> | <span data-ttu-id="b56b5-142">Ignorer les valeurs par défaut des propriétés.</span><span class="sxs-lookup"><span data-stu-id="b56b5-142">Ignore default values of properties.</span></span> <span data-ttu-id="b56b5-143">Cet indicateur s’applique uniquement à la comparaison des classes.</span><span class="sxs-lookup"><span data-stu-id="b56b5-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="b56b5-144">0 x 20</span><span class="sxs-lookup"><span data-stu-id="b56b5-144">0x20</span></span> | <span data-ttu-id="b56b5-145">Ignorer les versions de qualificateur.</span><span class="sxs-lookup"><span data-stu-id="b56b5-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="b56b5-146">Cet indicateur toujours qualificateurs en tenant compte, mais ignore les distinctions de version tels que les règles de propagation et remplace les restrictions.</span><span class="sxs-lookup"><span data-stu-id="b56b5-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="b56b5-147">0x10</span><span class="sxs-lookup"><span data-stu-id="b56b5-147">0x10</span></span> | <span data-ttu-id="b56b5-148">Ignorer la casse lors de la comparaison des valeurs de chaîne.</span><span class="sxs-lookup"><span data-stu-id="b56b5-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="b56b5-149">Cela s’applique à la fois pour les chaînes et valeurs de qualificateur.</span><span class="sxs-lookup"><span data-stu-id="b56b5-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="b56b5-150">La comparaison des noms de propriété et le qualificateur est toujours la casse, même si cet indicateur est défini.</span><span class="sxs-lookup"><span data-stu-id="b56b5-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="b56b5-151">0 x 8</span><span class="sxs-lookup"><span data-stu-id="b56b5-151">0x8</span></span> | <span data-ttu-id="b56b5-152">Supposons que les objets comparés sont des instances de la même classe.</span><span class="sxs-lookup"><span data-stu-id="b56b5-152">Assume that the objects being compared are instanes of the same class.</span></span> <span data-ttu-id="b56b5-153">Par conséquent, cet indicateur compare uniquement des informations relatives aux instances.</span><span class="sxs-lookup"><span data-stu-id="b56b5-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="b56b5-154">Utilisez cette indicateurs pour optimiser les performances.</span><span class="sxs-lookup"><span data-stu-id="b56b5-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="b56b5-155">Si les objets ne sont pas de la même classe, les résultats sont indéfinis.</span><span class="sxs-lookup"><span data-stu-id="b56b5-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="b56b5-156">Ou vous pouvez spécifier un seul indicateur composite comme suit :</span><span class="sxs-lookup"><span data-stu-id="b56b5-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="b56b5-157">Constante</span><span class="sxs-lookup"><span data-stu-id="b56b5-157">Constant</span></span>  |<span data-ttu-id="b56b5-158">Value</span><span class="sxs-lookup"><span data-stu-id="b56b5-158">Value</span></span>  |<span data-ttu-id="b56b5-159">Description</span><span class="sxs-lookup"><span data-stu-id="b56b5-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="b56b5-160">0</span><span class="sxs-lookup"><span data-stu-id="b56b5-160">0</span></span> | <span data-ttu-id="b56b5-161">Prendre en compte toutes les fonctionnalités dans la comparaison.</span><span class="sxs-lookup"><span data-stu-id="b56b5-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="b56b5-162">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b56b5-162">Requirements</span></span>  
 <span data-ttu-id="b56b5-163">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b56b5-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b56b5-164">**En-tête :** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b56b5-164">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b56b5-165">**Versions du .NET framework :** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b56b5-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b56b5-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b56b5-166">See also</span></span>  
[<span data-ttu-id="b56b5-167">WMI et les compteurs de Performance (référence des API non managées)</span><span class="sxs-lookup"><span data-stu-id="b56b5-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

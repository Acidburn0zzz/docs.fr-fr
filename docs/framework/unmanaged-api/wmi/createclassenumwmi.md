---
title: CreateClassEnumWmi (fonction) (référence des API non managées)
description: La fonction CreateClassEnumWmi retourne un énumérateur pour toutes les classes qui répondent aux critères spécifiés.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f84902586a2b940d52eb6365a141af61af802dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461452"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="ed6f6-103">CreateClassEnumWmi (fonction)</span><span class="sxs-lookup"><span data-stu-id="ed6f6-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="ed6f6-104">Retourne un énumérateur pour toutes les classes qui répondent aux critères de sélection spécifiés.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ed6f6-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ed6f6-105">Syntax</span></span>  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a><span data-ttu-id="ed6f6-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ed6f6-106">Parameters</span></span>

`strSuperclass`    
<span data-ttu-id="ed6f6-107">[in] Si ce n’est pas `null` ou vide, spécifie le nom d’une classe parente ; l’énumérateur retourne uniquement les sous-classes de cette classe.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="ed6f6-108">S’il s’agit `null` ou vide et `lFlags` WBEM_FLAG_SHALLOW, renvoie les classes de niveau supérieur uniquement (classes sans classe parent).</span><span class="sxs-lookup"><span data-stu-id="ed6f6-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="ed6f6-109">S’il s’agit `null` ou vide et `lFlags` est `WBEM_FLAG_DEEP`, retourne toutes les classes dans l’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`   
<span data-ttu-id="ed6f6-110">[in] Une combinaison d’indicateurs qui affectent le comportement de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="ed6f6-111">Les valeurs suivantes sont définies dans le *WbemCli.h* fichier d’en-tête, ou vous pouvez les définir en tant que constantes dans votre code :</span><span class="sxs-lookup"><span data-stu-id="ed6f6-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="ed6f6-112">Constante</span><span class="sxs-lookup"><span data-stu-id="ed6f6-112">Constant</span></span>  |<span data-ttu-id="ed6f6-113">Value</span><span class="sxs-lookup"><span data-stu-id="ed6f6-113">Value</span></span>  |<span data-ttu-id="ed6f6-114">Description</span><span class="sxs-lookup"><span data-stu-id="ed6f6-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="ed6f6-115">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="ed6f6-115">0x20000</span></span> | <span data-ttu-id="ed6f6-116">Si l’ensemble, la fonction récupère les qualificateurs stockées dans l’espace de noms localisé des paramètres régionaux de la connexion actuelle.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="ed6f6-117">Si ce n’est pas le cas, ensemble, la fonction récupère uniquement les qualificateurs stockées dans l’espace de noms immédiate.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="ed6f6-118">0</span><span class="sxs-lookup"><span data-stu-id="ed6f6-118">0</span></span> | <span data-ttu-id="ed6f6-119">L’énumération inclut toutes les sous-classes dans la hiérarchie, mais pas à cette classe.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="ed6f6-120">1</span><span class="sxs-lookup"><span data-stu-id="ed6f6-120">1</span></span> | <span data-ttu-id="ed6f6-121">L’énumération inclut uniquement les instances de cette classe pures et exclut toutes les instances de sous-classes qui fournissent des propriétés non trouvées dans cette classe.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="ed6f6-122">0x10</span><span class="sxs-lookup"><span data-stu-id="ed6f6-122">0x10</span></span> | <span data-ttu-id="ed6f6-123">L’indicateur provoque un appel semi-synchrone.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="ed6f6-124">0 x 20</span><span class="sxs-lookup"><span data-stu-id="ed6f6-124">0x20</span></span> | <span data-ttu-id="ed6f6-125">La fonction retourne un énumérateur de type avant uniquement.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="ed6f6-126">En règle générale, les énumérateurs avant uniquement sont plus rapides et utilisent moins de mémoire que les énumérateurs classiques, mais ils ne permettent pas d’appels à [Clone](clone.md).</span><span class="sxs-lookup"><span data-stu-id="ed6f6-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="ed6f6-127">0</span><span class="sxs-lookup"><span data-stu-id="ed6f6-127">0</span></span> | <span data-ttu-id="ed6f6-128">WMI conserve les pointeurs vers les objets dans l’enumration jusqu'à ce qu’elles sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-128">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="ed6f6-129">Les indicateurs recommandées sont `WBEM_FLAG_RETURN_IMMEDIATELY` et `WBEM_FLAG_FORWARD_ONLY` pour de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="ed6f6-130">[in] En règle générale, cette valeur est `null`.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="ed6f6-131">Dans le cas contraire, il est un pointeur vers un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance qui peut être utilisé par le fournisseur qui fournit les classes demandées.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-131">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="ed6f6-132">[out] Reçoit le pointeur vers l’énumérateur.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="ed6f6-133">[in] Le niveau d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-133">[in] The authorization level.</span></span>

<span data-ttu-id="ed6f6-134">`impLevel` [in] Le niveau d’emprunt d’identité.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-134">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="ed6f6-135">[in] Un pointeur vers un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objet qui représente l’espace de noms actuel.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-135">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="ed6f6-136">[in] Le nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-136">[in] The user name.</span></span> <span data-ttu-id="ed6f6-137">Consultez le [ConnectServerWmi](connectserverwmi.md) (fonction) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="ed6f6-138">[in] Le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-138">[in] The password.</span></span> <span data-ttu-id="ed6f6-139">Consultez le [ConnectServerWmi](connectserverwmi.md) (fonction) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="ed6f6-140">[in] Le nom de domaine de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-140">[in] The domain name of the user.</span></span> <span data-ttu-id="ed6f6-141">Consultez le [ConnectServerWmi](connectserverwmi.md) (fonction) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="ed6f6-142">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="ed6f6-142">Return value</span></span>

<span data-ttu-id="ed6f6-143">Les valeurs suivantes est retournées par cette fonction sont définies dans le *WbemCli.h* fichier d’en-tête, ou vous pouvez les définir en tant que constantes dans votre code :</span><span class="sxs-lookup"><span data-stu-id="ed6f6-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ed6f6-144">Constante</span><span class="sxs-lookup"><span data-stu-id="ed6f6-144">Constant</span></span>  |<span data-ttu-id="ed6f6-145">Value</span><span class="sxs-lookup"><span data-stu-id="ed6f6-145">Value</span></span>  |<span data-ttu-id="ed6f6-146">Description</span><span class="sxs-lookup"><span data-stu-id="ed6f6-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="ed6f6-147">0 x 80041003</span><span class="sxs-lookup"><span data-stu-id="ed6f6-147">0x80041003</span></span> | <span data-ttu-id="ed6f6-148">L’utilisateur ne dispose pas d’autorisation d’afficher un ou plusieurs des classes de la fonction peut retourner.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="ed6f6-149">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="ed6f6-149">0x80041001</span></span> | <span data-ttu-id="ed6f6-150">Une erreur non spécifiée s’est produite.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="ed6f6-151">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="ed6f6-151">0x80041010</span></span> | <span data-ttu-id="ed6f6-152">`strSuperClass` n’existe pas.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ed6f6-153">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="ed6f6-153">0x80041008</span></span> | <span data-ttu-id="ed6f6-154">Un paramètre n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ed6f6-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ed6f6-155">0x80041006</span></span> | <span data-ttu-id="ed6f6-156">Pas assez de mémoire est disponible pour terminer l’opération.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="ed6f6-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="ed6f6-157">0x80041033</span></span> | <span data-ttu-id="ed6f6-158">WMI s’est probablement arrêté, puis redémarrez.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="ed6f6-159">Appelez [ConnectServerWmi](connectserverwmi.md) à nouveau.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ed6f6-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ed6f6-160">0x80041015</span></span> | <span data-ttu-id="ed6f6-161">Le lien de remote procedure call (RPC) entre les processus en cours et WMI a échoué.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ed6f6-162">0</span><span class="sxs-lookup"><span data-stu-id="ed6f6-162">0</span></span> | <span data-ttu-id="ed6f6-163">L’appel de fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="ed6f6-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ed6f6-164">Notes</span><span class="sxs-lookup"><span data-stu-id="ed6f6-164">Remarks</span></span>

<span data-ttu-id="ed6f6-165">Cette fonction encapsule un appel à la [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) (méthode).</span><span class="sxs-lookup"><span data-stu-id="ed6f6-165">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="ed6f6-166">Si l’appel de fonction échoue, vous pouvez obtenir des informations d’erreur supplémentaires en appelant le [GetErrorInfo](geterrorinfo.md) (fonction).</span><span class="sxs-lookup"><span data-stu-id="ed6f6-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="ed6f6-167">Spécifications</span><span class="sxs-lookup"><span data-stu-id="ed6f6-167">Requirements</span></span>  
 <span data-ttu-id="ed6f6-168">**Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed6f6-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed6f6-169">**En-tête :** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ed6f6-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ed6f6-170">**Versions du .NET framework :** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ed6f6-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6f6-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed6f6-171">See also</span></span>  
[<span data-ttu-id="ed6f6-172">WMI et les compteurs de Performance (référence des API non managées)</span><span class="sxs-lookup"><span data-stu-id="ed6f6-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)

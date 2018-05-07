---
title: CorTypeAttr, énumération
ms.date: 03/30/2017
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f71e59eb13321517de61315d3ba06b96c5458f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="cortypeattr-enumeration"></a>CorTypeAttr, énumération
Contient des valeurs qui indiquent les métadonnées de type.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a>Membres  
  
|Membre|Description|  
|------------|-----------------|  
|`tdVisibilityMask`|Utilisé pour les informations de visibilité de type.|  
|`tdNotPublic`|Spécifie que le type n’est pas dans la portée publique.|  
|`tdPublic`|Spécifie que le type est dans la portée publique.|  
|`tdNestedPublic`|Spécifie que le type est imbriqué avec une visibilité publique.|  
|`tdNestedPrivate`|Spécifie que le type est imbriqué avec une visibilité privée.|  
|`tdNestedFamily`|Spécifie que le type est imbriqué avec une visibilité de niveau famille.|  
|`tdNestedAssembly`|Spécifie que le type est imbriqué avec une visibilité d’assembly.|  
|`tdNestedFamANDAssem`|Spécifie que le type est imbriqué avec une visibilité family et assembly.|  
|`tdNestedFamORAssem`|Spécifie que le type est imbriqué avec une visibilité family ou assembly.|  
|`tdLayoutMask`|Obtient les informations de disposition pour le type.|  
|`tdAutoLayout`|Spécifie que les champs de ce type sont placés automatiquement.|  
|`tdSequentialLayout`|Spécifie que les champs de ce type sont placés séquentiellement.|  
|`tdExplicitLayout`|Spécifie la que disposition de ce champ est fournie explicitement.|  
|`tdClassSemanticsMask`|Obtient des informations de sémantiques sur le type.|  
|`tdClass`|Spécifie que le type est une classe.|  
|`tdInterface`|Spécifie que le type est une interface.|  
|`tdAbstract`|Spécifie que le type est abstrait.|  
|`tdSealed`|Spécifie que le type ne peut pas être étendu.|  
|`tdSpecialName`|Spécifie que le nom de classe est spécial. Son nom décrit comment.|  
|`tdImport`|Spécifie que le type est importé.|  
|`tdSerializable`|Spécifie que le type est sérialisable.|  
|`tdWindowsRuntime`|Spécifie que ce type est un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.|  
|`tdStringFormatMask`|Obtient des informations sur comment les chaînes sont encodées et mis en forme.|  
|`tdAnsiClass`|Spécifie que ce type interprète LPTSTR comme ANSI.|  
|`tdUnicodeClass`|Spécifie que ce type interprète LPTSTR au format Unicode.|  
|`tdAutoClass`|Spécifie que ce type interprète LPTSTR automatiquement.|  
|`tdCustomFormatClass`|Spécifie que le type a un encodage non standard, comme spécifié par `CustomFormatMask`.|  
|`tdCustomFormatMask`|Utilisez ce masque pour obtenir des informations de codage non standard pour une interopérabilité native. La signification des valeurs de ces deux bits n’est pas spécifiée.|  
|`tdBeforeFieldInit`|Spécifie que le type doit être initialisé avant la première tentative d’accès à un champ statique.|  
|`tdForwarder`|Spécifie que le type est exporté et un redirecteur de type.|  
|`tdReservedMask`|Cet indicateur et les indicateurs ci-après sont utilisées en interne par le common language runtime.|  
|`tdRTSpecialName`|Spécifie que le common language runtime doit vérifier l’encodage de nom.|  
|`tdHasSecurity`|Spécifie que le type est associée.|  
  
## <a name="requirements"></a>Spécifications  
 **Plateformes :** consultez [requise](../../../../docs/framework/get-started/system-requirements.md).  
  
 **En-tête :** CorHdr.h  
  
 **Versions du .NET framework :** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations de métadonnées](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

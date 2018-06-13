---
title: GUID_ManagedName, attribut
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bae50f695de81856d4fddcb2af3d1188d896642
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430009"
---
# <a name="guidmanagedname-attribute"></a>GUID_ManagedName, attribut
Définit un attribut d’interface personnalisé qui spécifie le nom de l’espace de noms managé pour une bibliothèque de composant object model (COM).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a>Paramètres  
 `value`  
 Le nom de l’espace de noms managé pour la bibliothèque.  
  
## <a name="definition"></a>Définition  
 `GUID_ManagedName` est défini dans Cor.h comme suit :  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Notes  
 Un attribut d’interface personnalisé définit les métadonnées pour un objet dans la bibliothèque de types.  
  
 Utilisez <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> ou <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> pour récupérer le nom managé de l’attribut.  
  
 Pour plus d’informations, consultez [des attributs d’Interface](/cpp/windows/interface-attributes) dans Visual C++ documentation de référence.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre une définition de bibliothèque à l’aide de la `GUID_ManagedName` attribut.  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** Cor.h

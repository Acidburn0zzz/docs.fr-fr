---
title: ISymUnmanagedReader2, interface
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2
helpviewer_keywords: ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b23e166249659b94d454070c01c003495d1018a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader2-interface"></a>ISymUnmanagedReader2, interface
Représente un lecteur de symboles qui fournit l’accès aux documents, des méthodes et des variables dans un magasin de symboles. Cette interface étend la [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.  
  
## <a name="methods"></a>Méthodes  
  
|Méthode|Description|  
|------------|-----------------|  
|[GetMethodByVersionPreRemap (méthode)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|Obtenir une méthode de lecteur de symboles, étant donné un jeton de méthode et un numéro de version modifier et continuer.|  
|[GetMethodsInDocument (méthode)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|Obtient chaque méthode qui a des informations de ligne dans le document fourni.|  
|[GetSymAttributePreRemap (méthode)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|Obtient un attribut personnalisé en fonction de son nom.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces du magasin de symboles de Diagnostics](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedReader (Interface)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

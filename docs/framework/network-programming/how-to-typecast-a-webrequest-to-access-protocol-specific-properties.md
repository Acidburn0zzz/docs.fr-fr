---
title: 'Comment : convertir une classe WebRequest pour accéder à des propriétés spécifiques au protocole'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b4cde78ead9bdb8becf0f12497f4b37ad5a73bb3
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2018
ms.locfileid: "47421524"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="1fd34-102">Comment : convertir une classe WebRequest pour accéder à des propriétés spécifiques au protocole</span><span class="sxs-lookup"><span data-stu-id="1fd34-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="1fd34-103">Cet exemple montre comment effectuer un cast du type d’une classe WebRequest pour accéder à des propriétés spécifiques au protocole.</span><span class="sxs-lookup"><span data-stu-id="1fd34-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fd34-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="1fd34-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fd34-105">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fd34-105">See Also</span></span>  
 [<span data-ttu-id="1fd34-106">Programmation de protocoles enfichables</span><span class="sxs-lookup"><span data-stu-id="1fd34-106">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)

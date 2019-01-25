---
title: Assistant Débogage managé marshaling
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37351dadf941e3512249dd8a9f433b63065ae1fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626886"
---
# <a name="marshaling-mda"></a>Assistant Débogage managé marshaling
L’Assistant Débogage managé (MDA) `marshaling` est activé quand le CLR définit des informations de marshaling pour un paramètre de méthode ou un champ de structure. Ce MDA ne fonctionne pas pour les assemblys compilés juste-à-temps (JIT).  
  
## <a name="effect-on-the-runtime"></a>Effet sur le runtime  
 Cet Assistant Débogage managé n'a aucun effet sur le CLR.  
  
## <a name="output"></a>Sortie  
 Le MDA affiche le type du paramètre ou du champ dans les contextes managés et non managés ainsi que la structure ou la méthode qui contient ce type.  Voici un exemple de sortie pour un champ :  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a>Configuration  
 La configuration du MDA vous permet de filtrer les informations de marshaling signalées en fonction des noms de champs ou de méthodes impliqués.  L'exemple suivant illustre l'utilisation des éléments `methodFilter`, `fieldFilter` et `match` pour spécifier des filtres.  L'utilisation d'un astérisque (*) avec l'attribut `name` permet de spécifier tous les noms.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostic d’erreurs avec les Assistants Débogage managé](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshaling d'interopérabilité](../../../docs/framework/interop/interop-marshaling.md)

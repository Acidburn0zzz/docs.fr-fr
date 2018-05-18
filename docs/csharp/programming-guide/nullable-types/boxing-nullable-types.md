---
title: Boxing des types Nullable (Guide de programmation C#)
ms.date: 07/20/2015
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
ms.openlocfilehash: e2c7602bf45f1861d3a32a73824e9fedf0a4d29d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="boxing-nullable-types-c-programming-guide"></a>Boxing des types Nullable (Guide de programmation C#)
Les objets basés sur des types Nullable sont boxed uniquement si l’objet n’est pas Null. Si <xref:System.Nullable%601.HasValue%2A> a la valeur `false`, la référence d’objet est affectée à `null` au lieu du boxing. Exemple :  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 Si l’objet n’est pas null (si <xref:System.Nullable%601.HasValue%2A> a la valeur `true`), le boxing s’applique uniquement au type sous-jacent sur lequel repose l’objet Nullable. Le boxing d’un type de valeur Nullable non null convertit le type de valeur lui-même, et non pas le <xref:System.Nullable%601?displayProperty=nameWithType> qui encapsule le type de valeur. Exemple :  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 Les deux objets boxed sont identiques à ceux créés par le boxing des types non Nullable. Comme les types boxed non Nullable, ils peuvent être unboxed en types Nullable, comme dans l’exemple suivant :  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a>Notes  
 Le comportement de types Nullable quand ils sont boxed présente deux avantages :  
  
1.  Les objets Nullable et leur équivalent boxed peuvent être testés pour chercher des valeurs Null :  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  Les types Nullable boxed prennent en charge pleinement les fonctionnalités du type sous-jacent :  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Types Nullable](../../../csharp/programming-guide/nullable-types/index.md)  
 [Comment : identifier un type Nullable](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
